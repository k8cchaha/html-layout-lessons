# Day2

HTML - 影音
- video
- audio
- source

webm 最近幾年出來的影片格式 (google 力推)
- 因為檔案超小
- safari 也支援

解析 js - v8引擎
解析 css - 

webkit
moz
ms
都是在講核心的部分

按順序
if 看得懂 webm 就用
else if 看得懂 mp4 就用
else 不支援

<標籤 屬性=直 屬性=直 屬性=直>
屬性沒有寫 =直 表示用預設值

source 沒有尾的標籤
meta, img, br, link 也是


以前標籤有長這樣
<img src="" alt="" />
那條斜線是因為 xhtml

HTML 4.0
標籤應該是用來表達這篇文章的含義
以前會出現這種, 語意不明的標籤
<font></font>
<center></center>

XHTML 1.0
XML + HTML = XHTML
因為 XML 一定要有頭尾
img 是可置換的, 不是個容器
但為了配合XML規則, 所以在尾巴加了斜線

所以新的 HTML 5 完全不需要 斜線

HTML5 shiv : 就瀏覽器掛這個就可以看得懂 HTML5

HTML 4
XHTML
HTML 5
HTML 5.1

hr 分隔線：現在比較沒在用了, 語意上較沒意義
在 HTML5 的語意是：要開始一段新的內容

HTML5 不是只是在講 5 這版本
廣義的說是：HTML, CSS, JS 在內的一套技術組合
希望減少瀏覽器對於外掛程式的網路應用服務

其他新的元素
section, article, header, nav 更容易精準表達語意內容

div 不能包在 p裡面
若這樣寫 p會被拆出來, 結構會被修改

早期這樣不行, 但也不會有事, 因為瀏覽器沒有定義怎麼修正
現在是合法的
<a>
  <div></div>
</a>

圖片
- 檔案格式
  - jpg/jpeg: 檔案小, 破壞性壓縮檔, 畫質較差, 無法去背, 無透明區, 色彩 256x256x256 適合相片
  - gif: 檔案小, 色彩只有256色, 可以做動畫, 有透明區(全透/全部透)
  - png: 漂亮的去背, 有透明(有半透), 有 256x256x256色, 但檔案較大
  - png 可以分 png8(256色, 檔案小, 有透明, 全透/全不透), png24 (位元)
  - apng,  
  - webp: 檔案小, 有256x256x256色, 可以做動畫, 有透明區 (集所有優點於一身)
  - svg: 向量圖檔, 一堆文字原始檔的組合, 檔案小 (其他都是點陣圖), 應用在小 icon, 可搭配css 做動畫
  - bmp
- 標籤 (img, figure, figcaption, picture, source)

<img src="" alt="">
若沒有圖檔, 會出現 alt 內的文字 (代替圖片顯示)
google 下關鍵字找圖時, 也會依據 alt 來找到圖

Safari 要加上寬度, 替代文字才會出來
<img src="xxx" width="100" alt="哈哈哈">

獨立解析的區塊 , 就不該跟內文一起解讀
<figure class="pic">
  <img src="" alt="">
  <figcaption>   // 用來解釋上面那張圖
    <p>cccccc</p>
  </figcaption>
</figure>

picture, source 應用在 RWD
不同裝置讀取不同的圖檔

<div class="pic">
  <img src="big.jpg">
  <img src="medium.jpg">
  <img src="small.jpg">
</div>
// 圖檔全都會下載, 浪費頻寬, 所以造就了下面的寫法
<picture>
  <source srcset="big.jpg" media="(min-width: 1200px)">
  <source srcset="medium.jpg" media="(min-width: 768px) and (max-width: 1199px)">
  <img src="small.jpg" alt="">
</picture>
// 瀏覽器端只會下載符合條件的圖, 要由大寫到小

https://developer.mozilla.org/en-US/docs/Web/HTML/Element/picture

待確認...
<img
  src="pic_500x500.jpg"
  srcset="pic_500x500.jpg 500w, pic_




是否支援：caniuse 上面查

