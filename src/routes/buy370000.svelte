<script>
	let buyList = [
		{
			name: 'Apple 蘋果iMac 24 吋 4.5K Retina 顯示器 M4 晶片配備 10核心CPU 10核心GPU 與 16核心 16GB 記憶體 512GB SSD',
			src: 'https://img.pchome.com.tw/cs/items/DYAJEUA900I160J/001001_1730694344.jpg',
			link: 'https://24h.pchome.com.tw/prod/DYAJEU-A900I160J',
			price: 54777
		},
		{
			name: 'MSI 微星 PRO AP242P 14M-619TW-SP1 24型(i5-14400/16G/512G SSD/W11)特仕版',
			src: 'https://img.pchome.com.tw/cs/items/DSAAFTA900H48JK/000001_1708683237.jpg',
			link: 'https://24h.pchome.com.tw/prod/DSAAFT-A900H48JK',
			price: 24400
		},
		{
			name: 'https://24h.pchome.com.tw/prod/DRAG08-1900I4Q2G',
			src: 'https://img.pchome.com.tw/cs/items/DRAG081900I4Q2G/000001_1733224367.jpg',
			link: 'https://24h.pchome.com.tw/prod/DRAG08-1900I4Q2G',
			price: 9999
		},
		{
			name: 'WD 威騰[2入組]【紅標Plus】4TB 3.5吋 NAS硬碟(WD40EFPX)',
			src: 'https://img.pchome.com.tw/cs/items/DRAB461900GYLH8/000001_1727716823.jpg',
			link: 'https://24h.pchome.com.tw/prod/DRAB46-1900GYLH8',
			price: 6950
		},
		{
			name: 'ACER 宏碁Nitro N50-650系列-i5處理器/16G記憶體/512G SSD/RTX4060顯卡/Win11家用版電腦(UD.E3GTA.00K)',
			src: 'https://img.pchome.com.tw/cs/items/DSAAJNA900GMGY9/l000003_1742354236.jpg',
			link: 'https://24h.pchome.com.tw/prod/DSAAJN-A900GMGY9',
			price: 29900
		},
		{
			name: 'TP-LinkArcher TBE400UH Wi-Fi 7 BE6500 三頻 USB3.0 高增益無線網卡(WiFi 7無線網路卡)',
			src: 'https://img.pchome.com.tw/cs/items/DRAN5O1900IIM1J/l000003_1743502984.jpg',
			link: 'https://24h.pchome.com.tw/prod/DRAN5O-1900IIM1J',
			price: 1999
		},
		{
			name: 'TP-LinkWiFi 7 BE3600 雙頻 高CP 無線網路 路由器 分享器(支援AI筆電/EasyMesh/VPN/Archer BE220)',
			src: 'https://img.pchome.com.tw/cs/items/DRAN09A900IK1F1/000001_1744651174.jpg',
			link: 'https://24h.pchome.com.tw/prod/DRAN09-A900IK1F1',
			price: 1999
		},
		{
			name: 'Apple 蘋果MacBook Air 13 M4 晶片配備 10 核心 CPU、10 核心 GPU、16 核心神經網路引擎 16GB 記憶體 512GB SSD',
			src: 'https://img.pchome.com.tw/cs/items/DYAJFGA900IF4IV/000001_1741767441.jpg',
			link: 'https://24h.pchome.com.tw/prod/DYAJFG-A900IF4IV',
			price: 41900
		},
		{
			name: 'Apple 蘋果Mac mini Apple M4 晶片配備 10 核心 CPU、10 核心 GPU、16 核心 16GB記憶體 512GB SSD',
			src: 'https://img.pchome.com.tw/cs/items/DYAJFDA900I1EWG/000001_1730446566.jpg',
			link: 'https://24h.pchome.com.tw/prod/DYAJFD-A900I1EWG',
			price: 26093
		},
		{
			name: 'ACER 宏碁Aspire Lite 16吋Ultra 5 AI 輕薄長效筆電 (Ultra 5 115U/16G/512G/WIN11/AL16-53P-57B8)',
			src: 'https://img.pchome.com.tw/cs/items/DHAEILA900I9GSD/000001_1745283992.jpg',
			link: 'https://24h.pchome.com.tw/prod/DHAEIL-A900I9GSD',
			price: 19700
		},
		{
			name: 'Apple 蘋果含 Touch ID 和數字鍵盤的巧控鍵盤，適用於配備 Apple 晶片的 Mac 機型 - 中文 (注音) - 白色按鍵',
			src: 'https://img.pchome.com.tw/cs/items/DYAJBVA900I1EKD/000001_1730442696.jpg',
			link: 'https://24h.pchome.com.tw/prod/DYAJBV-A900I1EKD',
			price: 5025
		},
		{
			name: 'ACER 宏碁Swift 14吋AI輕薄筆電 藍 (Ultra 5 226V/16GB/512G PCIe/W11/OLED/SF14-51-5174)',
			src: 'https://img.pchome.com.tw/cs/items/DYAWAA1900I6CIP/000001_1746036683.jpg',
			link: 'https://24h.pchome.com.tw/prod/DYAWAA-1900I6CIP',
			price: 8999
		},
		{
			name: 'MOTOROLA 摩托羅拉razr 40 5G (8G/256G) 6.9吋智慧型摺疊機-豆腐白 ',
			src: 'https://im1.book.com.tw/image/getImage?i=https://www.books.com.tw/img/001/097/49/0010974918.jpg&v=655f2a30k&w=348&h=348',
			link: 'https://www.buys.com.tw/products/0010974918?sloc=main',
			price: 675
		},
		{
			name: 'Apple 蘋果iPhone 16 Plus (128G)',
			src: 'https://img.pchome.com.tw/cs/items/DYAJLZ1900HXG0I/000001_1736323708.jpg',
			link: 'https://24h.pchome.com.tw/prod/DYAJLZ-1900HXG0I',
			price: 31500
		},
		{
			name: 'Apple 蘋果iPhone 16e (128G)',
			src: 'https://img.pchome.com.tw/cs/items/DYAJ8L1900IDJG6/000001_1744009004.jpg',
			link: 'https://24h.pchome.com.tw/prod/DYAJ8L-1900IDJG6',
			price: 20900
		},
		{
			name: 'Samsung 三星 Galaxy S25 (12G/256G)',
			src: 'https://cs-a.ecimg.tw/items/DYALI8A900IHX1V/yt000001_1742969863.jpg',
			link: 'https://24h.pchome.com.tw/prod/DYALI8-A900IHX1V',
			price: 25100
		},
		{
			name: 'Xiaomi 小米Pad 7 Pro 12GB/512GB',
			src: 'https://img.pchome.com.tw/cs/items/DYAMG1A900IEQ2J/000001_1740987342.jpg',
			link: 'https://24h.pchome.com.tw/prod/DYAMG1-A900IEQ2J',
			price: 15999
		},
		{
			name: 'ASRock華擎 DeskMini B760【準系統】LGA1700/No-OS/迷你主機/原價屋【活動贈】',
			src: 'https://down-tw.img.susercontent.com/file/tw-11134207-7r98q-lm48lvv70sd56e@resize_w900_nl.webp',
			link: 'https://shopee.tw/ASRock%E8%8F%AF%E6%93%8E-DeskMini-B760%E3%80%90%E6%BA%96%E7%B3%BB%E7%B5%B1%E3%80%91LGA1700-No-OS-%E8%BF%B7%E4%BD%A0%E4%B8%BB%E6%A9%9F-%E5%8E%9F%E5%83%B9%E5%B1%8B%E3%80%90%E6%B4%BB%E5%8B%95%E8%B4%88%E3%80%91-i.54133273.16698991689',
			price: 25230
		}
		,
		{
			name: 'Samsung 三星Galaxy A36 5G (8G/256G)',
			src: 'https://img.pchome.com.tw/cs/items/DYALR11900IPDFU/000001_1746155084.jpg',
			link: 'https://24h.pchome.com.tw/category/DYAL06C?sortParm=prc&sortOrder=dc',
			price: 14990
		}
		,
		{
			name: 'Nintendo Switch 2｜任天堂',
			src: 'https://www.nintendo.com/tw/hardware/switch2/assets/img/scene1/welcome-feature-product-batch.png',
			link: 'https://www.nintendo.com/tw/hardware/switch2/?nt_redirect_referrer=https://www.google.com/',
			price: 14380
		}
		,
		{
			name: 'ASUS 華碩Dual GeForce RTX 4060 EVO OC 8GB 顯示卡',
			src: 'https://img.pchome.com.tw/cs/items/DRADKYA900IL80J/000001_1746168819.jpg',
			link: 'https://24h.pchome.com.tw/prod/DRADKY-A900IL80J',
			price: 10490
		}
		,
		{
			name: 'Microsoft 微軟Windows 11 專業中文版 完整盒裝版 *3',
			src: 'https://img.pchome.com.tw/cs/items/DCAO6PA900ERJGH/000001_1684375625.jpg',
			link: 'https://24h.pchome.com.tw/prod/DCAO6P-A900ERJGH',
			price: 6990*3
		}
		,
		{
			name: 'Microsoft 微軟Office 2024 中小企業版盒裝',
			src: 'https://img.pchome.com.tw/cs/items/DSAEQ1A900HZCGB/000001_1729159946.jpg',
			link: 'https://24h.pchome.com.tw/prod/DSAEQ1-A900HZCGB',
			price: 8590
		}
		,
		{
			name: 'Parallels Desktop 20 for Mac (Standard Edition)',
			src: 'https://img.pchome.com.tw/cs/items/DSAEKWA900HZ0L3/000001_1742264195.jpg',
			link: 'https://24h.pchome.com.tw/prod/DSAEKW-A900HZ0L3',
			price: 3888
		}
		,
		{
			name: '自然輸入法V13 專業版1人3台',
			src: 'https://img.pchome.com.tw/cs/items/DSAEC3A900GNI4D/000001_1694490567.png',
			link: 'https://24h.pchome.com.tw/prod/DSAEC3-A900GNI4D',
			price: 3888
		}
		,
		{
			name: 'Cyberlink 訊連科技威力導演 2025 旗艦版【盒裝版】',
			src: 'https://img.pchome.com.tw/cs/items/DSAEADA900I4AB2/000001_1732765806.jpg',
			link: 'https://24h.pchome.com.tw/prod/DSAEAD-A900I4AB2',
			price: 4280
		}
		,
		{
			name: 'PlayStationSONY PS5 Slim 輕型光碟版主機 2018A01+PS5遊戲任選*1 加碼送PS5靈魂駭客2+PS4人龍7光與闇去向',
			src: 'https://cs-a.ecimg.tw/items/DGBJG9A900IBVHP/yt000001_1738739439.jpg',
			link: 'https://24h.pchome.com.tw/prod/DGBJG9-A900IBVHP',
			price: 4280
		}
		,
		{
			name: 'https://24h.pchome.com.tw/prod/DGBJCP-A900I9J2P',
			src: 'https://img.pchome.com.tw/cs/items/DGBJCPA900I9J2P/000001_1736942417.jpg',
			link: 'https://24h.pchome.com.tw/prod/DGBJCP-A900I9J2P',
			price: 18270
		}
	];

	// 計算總價
	$: totalPrice = buyList.reduce((sum, buy) => sum + buy.price, 0);
</script>

<h1>九月十月十一月十二月可能購買</h1>
<hr />
{#each buyList as buy}
	{#if buy.name}
		<!-- 避免空資料渲染 -->
		<div style="margin-bottom: 20px;">
			<img src={buy.src} alt={buy.name} width="150" />
			<br />
			<a class="hover:text-blue-500" href={buy.link} target="_blank">{buy.name}</a>
			<br />
			<label>{buy.price.toLocaleString()} 元</label>
			<br />
			<label>{buy.price.toLocaleString('zh-u-nu-hanidec')} 元</label>
			<br />
		</div>
	{/if}
{/each}

<hr />
<h3>總金額：{totalPrice.toLocaleString()} 元</h3>
<h3>總金額：{totalPrice.toLocaleString('zh-u-nu-hanidec')} 元</h3>
<h3>是否不超過三七萬元：{totalPrice<370000?"是":"否"}</h3>
<br />
