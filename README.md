# Constellation
<h1><img class="alignnone  wp-image-99" src="https://catmaoblog.files.wordpress.com/2016/10/6lqz4de.png" alt="Icon made by Freepik from www.flaticon.com" width="40" height="40" /> <a href="https://catmaoblog.wordpress.com/2016/10/16/constellation/" target="_blank">點我前往</a></h1>
<h1><img class="alignnone  wp-image-41" src="https://catmaoblog.files.wordpress.com/2016/10/3h9rzur.png" alt="Icon made by Popcorns Arts from www.flaticon.com" width="40" height="40" /> 前言</h1>
大部分輸入月日判斷星座的程式都會想到用一堆 if else 來寫，但在方文聘老師的教導下，第一次看到了超級簡短的星座判斷程式碼，不需要 if else ，有一點難懂但是真的是一個很厲害的作法，最底下的參考資料有附上方老師的部落格，有興趣鑽研程式的人可以看看，但這篇星座的老師似乎沒放在部落格。
<h1><img class="alignnone  wp-image-43" src="https://catmaoblog.files.wordpress.com/2016/10/ril6i6c.png" alt="Icon made by flaticon from www.flaticon.com" width="40" height="40" /> 程式碼</h1>
這次程式碼的部分主要解說如何用月日判斷出其星座。
<pre><code>var B = [21, 20, 21, 21, 22, 22, 24, 24, 24, 24, 23, 23];
var Const = ["水秤", "雙魚", "牡羊", "金牛", "雙子", "巨蟹", "獅子", "處女", "天秤", "天蠍", "射手", "魔羯"];

...

// m 為月份， d 為日期
var index = (Number(m) + Math.floor(d / B[m - 1]) + 10) % 12;
</code></pre>
<ol>
	<li>B 的數字為該星座當月開始的天數，如下圖紅色的數字。<img class="alignnone size-full wp-image-259" src="https://catmaoblog.files.wordpress.com/2016/10/gtd03uh.png" alt="gtd03uh" width="1344" height="572" /></li>
	<li>就單看 Math.floor( d / B[m - 1] ) 的部分，是要算出他是該星座當月開始的天數之前或之後， Math.floor 為無條件捨去。如果今天 d 為 10 ， m 為 2 ，則 10 / B[ 2 - 1 ] → 10 / 20 = 0.5 ，無條件捨去後為 0 ，所以是該星座當月開始天數（ 02 / 20 ）之前，就不會是雙魚座，判定為水瓶座。</li>
	<li>原本的 index 更詳細的拆解為：
<pre><code>var index = (Number(m) - 1 + Math.floor(d / B[m - 1]) + 11) % 12;</code></pre>
簡化過後才變成 + 10 ， -1 這個部分是我調了很久的數值才定下來的，一定有其他的寫法，大家可以試試看～，但我說不出非常清楚的原理。</li>
	<li>取 % 12 的原因是 12 月陣列為 11 ，取餘數後就可以得到 0 ~ 11 的值。</li>
</ol>
<h1><img class="alignnone  wp-image-42" src="https://catmaoblog.files.wordpress.com/2016/10/tpodion.png" alt="tpodion" width="40" height="40" /> 圖片素材</h1>
<ul class="alt">
	<li>Chen Yoo</li>
</ul>
<h1><img class="alignnone  wp-image-42" src="https://catmaoblog.files.wordpress.com/2016/10/tpodion.png" alt="tpodion" width="40" height="40" /> 參考資料</h1>
<ul class="alt">
	<li><a href="http://blog.xuite.net/wen_pinn/blog" target="_blank">新充滿奇蹟的寶寶 / 方文聘老師</a></li>
	<li><a href="http://www.freepik.com/free-vector/beautiful-constellations-background_844910.htm" target="_blank">封面底圖 / Designed by Freepik</a></li>
</ul>
