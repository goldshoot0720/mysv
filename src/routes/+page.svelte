<script>
	import Buy10000 from "./buy10000.svelte";
	import Buy370000 from "./buy370000.svelte";
	import BuySoftwareHistory from "./buySoftwareHistory.svelte";
	import AnimeOPED from "./animeOPED.svelte";
	import WeartherWeek from "./weartherWeek.svelte";
	import { Zap } from 'lucide-svelte';
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
The future I see，{Math.abs(Math.floor((new Date()-new Date("2025-07-05"))/1000/3600/24))}天，考試因故延期至十月，榜示因故延期至明年一月十四日
<br/>
<button class="flex items-center gap-1 hover:text-blue-500" onclick={() => { showBuy10000 = !showBuy10000; }}><Zap />Buy10000</button>
<button class="flex items-center gap-1 hover:text-blue-500" onclick={() => { showBuy370000 = !showBuy370000; }}><Zap />Buy370000</button>
<button class="flex items-center gap-1 hover:text-blue-500" onclick={() => { showBuySoftwareHistory = !showBuySoftwareHistory; }}><Zap />BuySoftwareHistory</button>
<button class="flex items-center gap-1 hover:text-blue-500" onclick={() => { showAnimeOPED = !showAnimeOPED; }}><Zap />2021~2025 TVアニメ OP ED</button>
<button class="flex items-center gap-1 hover:text-blue-500" onclick={() => { showWeartherWeek = !showWeartherWeek; }}><Zap />中壢區一週天氣預報</button>
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
