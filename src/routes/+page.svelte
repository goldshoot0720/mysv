<script>
	import Buy10000 from "./buy10000.svelte";
	import Buy370000 from "./buy370000.svelte";
	import BuySoftwareHistory from "./buySoftwareHistory.svelte";
	import AnimeOPED from "./animeOPED.svelte";
	import WeartherWeek from "./weartherWeek.svelte";
	let showBuy10000 = false;
	let showBuy370000 = false;
	let showBuySoftwareHistory = false;
	let showAnimeOPED = false;
	let showWeartherWeek = false;
</script>
距離紅鸞星動:2025-06-15，倒數{Math.abs(Math.floor((new Date()-new Date("2025-06-15"))/1000/3600/24))}天
<br/>
距離考試通知書:2025-06-19，倒數{Math.abs(Math.floor((new Date()-new Date("2025-06-19"))/1000/3600/24))}天
<br/>
The future I see，倒數{Math.abs(Math.floor((new Date()-new Date("2025-07-05"))/1000/3600/24))}天
<br/>
WORLD ORDER - LET'S START WW3，三普，倒數{Math.abs(Math.ceil((new Date()-new Date("2029-09-15"))/1000/3600/24/365.25))}年
<br/>
<button class="hover:text-blue-500" onclick={() => { showBuy10000 = !showBuy10000; }}>Buy10000</button>
<br/>
<button class="hover:text-blue-500" onclick={() => { showBuy370000 = !showBuy370000; }}>Buy370000</button>
<br/>
<button class="hover:text-blue-500" onclick={() => { showBuySoftwareHistory = !showBuySoftwareHistory; }}>BuySoftwareHistory</button>
<br/>
<button class="hover:text-blue-500" onclick={() => { showAnimeOPED = !showAnimeOPED; }}>2025 TVアニメ OP ED</button>
<br/>
<button class="hover:text-blue-500" onclick={() => { showWeartherWeek = !showWeartherWeek; }}>中壢區一週天氣預報</button>
<br/>
{#if showBuy10000}
<Buy10000 />
{/if}
{#if showBuy370000}
<Buy370000 />
{/if}
{#if showBuySoftwareHistory}
<BuySoftwareHistory/>
{/if}
{#if showAnimeOPED}
<AnimeOPED/>
{/if}
{#if showWeartherWeek}
<WeartherWeek/>
{/if}
