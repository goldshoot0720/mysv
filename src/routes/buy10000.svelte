<script>
	let buyList = [
		{
			name: '圖解考試的科學：高效率學習的關鍵',
			src: 'https://im2.book.com.tw/image/getImage?i=https://www.books.com.tw/img/001/096/47/0010964719.jpg&v=64ca306ck&w=348&h=348',
			link: 'https://www.buys.com.tw/products/0010964719?sloc=main',
			price: 432
		},
		{
			name: '法律人的第一本書（7版）',
			src: 'https://im1.book.com.tw/image/getImage?i=https://www.books.com.tw/img/001/099/24/0010992430.jpg&v=666c1bb8k&w=348&h=348',
			link: 'https://www.buys.com.tw/products/0010992430?sloc=main',
			price: 380
		},
		{
			name: '圖解憲法：國家考試的第一本書（第五版）',
			src: 'https://im2.book.com.tw/image/getImage?i=https://www.books.com.tw/img/001/099/91/0010999157.jpg&v=66c7135dk&w=348&h=348',
			link: 'https://www.buys.com.tw/products/0010999157?sloc=main',
			price: 675
		},
		{
			name: '圖解民法：國家考試的第一本書（第五版）',
			src: 'https://im2.book.com.tw/image/getImage?i=https://www.books.com.tw/img/001/093/99/0010939969.jpg&v=6357bafak&w=348&h=348',
			link: 'https://www.buys.com.tw/products/0010939969?sloc=main',
			price: 675
		},
		{
			name: '圖解刑法：國家考試的第一本書（第七版）',
			src: 'https://im2.book.com.tw/image/getImage?i=https://www.books.com.tw/img/001/098/33/0010983319.jpg&v=65d7224ck&w=348&h=348',
			link: 'https://www.buys.com.tw/products/0010983319?sloc=main',
			price: 612
		},
		{
			name: '圖解行政法：國家考試的第一本書（第五版）',
			src: 'https://im1.book.com.tw/image/getImage?i=https://www.books.com.tw/img/001/097/49/0010974918.jpg&v=655f2a30k&w=348&h=348',
			link: 'https://www.buys.com.tw/products/0010974918?sloc=main',
			price: 675
		},
		{
			name: 'KIOXIA 鎧俠 Exceria Plus G3 SSD M.2 2280 PCIe NVMe 1TB Gen4x4',
			src: 'https://img.pchome.com.tw/cs/items/DRAHGTA900GOJVX/000001_1703815399.jpg',
			link: 'https://24h.pchome.com.tw/prod/DRAHGT-A900GOJVX',
			price: 2090
		},
		{
			name: 'CASIO 卡西歐 精選經典文青輕薄超實用指針錶系列-多款任選II(MQ-24/MQ-24UC/MQ-76/LQ-139)',
			src: 'https://i2.momoshop.com.tw/1724744124/goodsimg/0011/640/304/11640304_B.webp',
			link: 'https://www.momoshop.com.tw/goods/GoodsDetail.jsp?i_code=11640304&Area=search&mdiv=403&oid=1_4&cid=index&kw=MQ-24+',
			price: 474
		},
		{
			name: '寫經得佛系療癒：願望滿足現世平安套書（25k標準本）】（二冊）：《寫•觀世音菩薩普門品》＋《寫•阿彌陀經》',
			src: 'https://i4.momoshop.com.tw/1731485554/goodsimg/0013/449/728/13449728_B.webp',
			link: 'https://www.momoshop.com.tw/goods/GoodsDetail.jsp?i_code=13449728&Area=search&mdiv=403&oid=1_7&cid=index&kw=%E5%BC%B5%E6%98%8E%E6%98%8E+%E9%98%BF%E7%B1%B3%E9%A7%9D%E7%B6%93',
			price: 442
		},
		{
			name: '【讓自己安心】手寫經書組合套書（三冊）:《寫心經》、《寫•藥師經》、《寫•金剛經》',
			src: 'https://i1.momoshop.com.tw/1692296385/goodsimg/0010/353/059/10353059_B.webp',
			link: 'https://www.momoshop.com.tw/goods/GoodsDetail.jsp?i_code=10353059&Area=search&mdiv=403&oid=1_1&cid=index&kw=%E5%BC%B5%E6%98%8E%E6%98%8E+',
			price: 639
		},
		{
			name: '快速精通iOS 18程式設計：從零開始活用Swift與SwiftUI開發技巧',
			src: 'https://im1.book.com.tw/image/getImage?i=https://www.books.com.tw/img/001/101/74/0011017436.jpg&v=67dbee36k&w=348&h=348',
			link: 'https://www.books.com.tw/products/0011017436?sloc=main',
			price: 639
		}
	];

	// 計算總價
	$: totalPrice = buyList.reduce((sum, buy) => sum + buy.price, 0);
</script>

<h1>六月七月可能購買</h1>
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
<h3>是否不超過一萬元：{totalPrice<10000?"是":"否"}</h3>
<br />
