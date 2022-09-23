# day4

表格
thead
tbody
tfoot

樣式可以用 html 上支援的
<table border="3" width="300">

若要改 表格內的編筐線
td {
  border: 5px solid red;
}

表格標題很特別, 寫在 table 裡面, 但是顯示會在 table 外面
css: 改變標題位置
caption {
  caption-side: bottom; //會跑到表格下方
  text-align: left; // 不一定要居中 
}

在 tbody > tr > 一樣可以用 th > 表達這一行的標頭

column 欄
span 跨
-> colspan 跨幾個欄的寬度 (合併)
-> colspan="2" 
-> rowspan 跨列

所有的 th 預設值都會居中 + 粗體

表格裡面是可以去設定寬度的
thead th:nth-child(1) {
  width: 25%;
}
thead th:nth-child(2) {
  width: 25%;
}
thead th:nth-child(3) {
  width: 25%;
}
thead th:nth-child(4) {
  width: 25%;
}
若沒寫的就會自動縮放

表格 CSS 屬性
table {
  border: 2px solid red;
  border-collapse: collapse; // 折疊, 會把編框之間的空間去掉
  border-spacing: 10px; // 反之可以把空間加大
}

作業：1:16:30

------
## CSS
> 行內樣式 inline style
不好維護, 不太使用
<p style="color: red">  
在 HTML 裡面夾雜了另外一個語言
style 的直, 裡面是 css 的語法
p , style , = "" 都是 HTML 語法
color: red 是 CSS 語法
光箱效果 display: none -> display: block 可輕易用程式做 inline style 的控制


>
選取器 {     // 你要設定的對象 or 我要選取的目標並對他做設定, 所以叫選取器
    屬性: 直
}
<style>
      p {    // 
        color: red;
      }
   </style>

class 給予網頁中的資料 分類, 就可針對不同的分類給予設定
.info {
  color: blue;
}

當多個選取器對同一物件產生作用時
就要講到優先權 (特異性, 獨特性), 越獨特, 優先權就越高 (或是說明確性)
若是相同級別的選取器, 後面會覆蓋前面

id : 一個頁面中只能出現一次  // 在 css 中是 ok 的, 但是在程式中很容易出錯

優先權：id > class > tag > * > 繼承 (選到同一個對象時, 要依據誰為優先)

若用算分數的概念, * 和 繼承 都是 0 分


影片 : css reflow

div span { // div 裡面的 span
  
}

* { }  // 萬用選取器, 意思是什麼都選
所以下面的 case , span 是藍色  // 選取的目標不一樣
* {
  color: blue;
}
div {
  color: red;
}
<div>
  <span> haha </span>



<div>
  <span>

div {
  color: red; // div 的子物件也會同時吃到爸爸的設定, 稱作繼承
}
span {
  color: blue
}

-> span 會是藍色, 因為 div 與 span 選取的"對象"不同, 特異性很清楚

-> 繼承 : 自己沒有被選取到, 所以跟著父層做設定 (跟內外圈沒有關係, 而是跟選取的目標)

繼承的概念就像這樣：
span {
  color: inherit;  // 預設直
}

但不是每個屬性都會被繼承
文字相關屬性會被繼承