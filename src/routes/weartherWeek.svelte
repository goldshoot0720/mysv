<script>
  import { onMount } from 'svelte';

  let weatherData = [];
  let loading = true;
  let error = '';

  const fetchWeather = async () => {
    try {
      const res = await fetch(
        'https://opendata.cwa.gov.tw/api/v1/rest/datastore/F-D0047-007?Authorization=CWA-1BFF165C-0D75-4FAF-B72B-34B7D6C82CCC&limit=5&offset=0&ElementName=%E5%A4%A9%E6%B0%A3%E7%8F%BE%E8%B1%A1'
      );
      const json = await res.json();

      // 打印 API 回傳的資料，查看結構
      console.log(json);

      const locations = json.records.Locations;

      if (!locations || locations.length === 0) {
        throw new Error('找不到 Locations');
      }

      const locationData = locations[0].Location.find(l => l.LocationName === '中壢區');
      if (!locationData) {
        throw new Error('找不到中壢區資料');
      }

      const weatherElement = locationData.WeatherElement;

      const wxElement = weatherElement.find((el) => el.ElementName === '天氣現象');
      if (!wxElement || !wxElement.Time) {
        throw new Error('找不到天氣現象資料');
      }

      const timePeriods = wxElement.Time;

      // 從API提取天氣資料
      weatherData = timePeriods.map((t, i) => ({
        startTime: formatDate(t.StartTime),
        endTime: formatDate(t.EndTime),
        weather: wxElement.Time[i]?.ElementValue[0]?.value ?? '—', // 這裡是天氣現象
      }));
    } catch (e) {
      error = '資料取得失敗：' + e.message;
      console.error(e);
    } finally {
      loading = false;
    }
  };

  const formatDate = (dateStr) => {
    const date = new Date(dateStr);
    return date.toLocaleString(); // 你可以根據需要自定義格式
  };

  onMount(fetchWeather);
</script>

{#if loading}
  <p>載入天氣資料中...</p>
{:else if error}
  <p class="text-red-600">{error}</p>
{:else}
  <table class="border border-gray-300 w-full text-sm">
      <thead class="bg-gray-200">
          <tr>
              <th class="p-2">時間</th>
              <th class="p-2">天氣現象</th>
          </tr>
      </thead>
      <tbody>
          {#each weatherData as item}
              <tr class="border-t border-gray-300">
                  <td class="p-2">{item.startTime} ~ {item.endTime}</td>
                  <td class="p-2">{item.weather}</td>
              </tr>
          {/each}
      </tbody>
  </table>
{/if}
