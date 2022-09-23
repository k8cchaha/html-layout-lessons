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
