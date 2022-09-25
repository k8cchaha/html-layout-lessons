# day6

作業檢討 (amos 寫的版本)
.price {
  font-size: 32px;
}
.price .nt {
  font-size: 28px;
}
.price .up {
  font-size: 16px;
}

<div class="price">
  <span class="nt">NT</span>
  <span>10000</span>
  <span class="up">起</span>

陰影：
box-shadow

多行文字點點點
-> day6.html

一個頁面當中, 建議 h1 只出現一次

不重要的資訊, 用 div or span 就可以了 
連 p 都不會用到
-> 刻意弱化

---

## box-model 盒模型
一個物件在畫面中佔據多少空間是很重要的事情
width = 200 , font-size = 20px -> 若用中文, 就會是 10個字的寬
中文是等寬字, 英文是非等寬字

容器寬度
-> width 所設定的寬是內容能使用的寬度
加了 border , 不影響內容寬度, 所以整體容器寬度會加大
加了 padding , 仍然不影響內容寬度
加了 margin , 仍然不影響內容寬度 (佔地盤的概念)

實際佔據的空間是上述 4個相加

width, border, padding : 實際看得到的大小
margin : 是看不見的

padding 指的是邊框線的內園道內容寬度之間的距離
margin: 物件外圍所佔據的空間

4個盒子所組成：
content-box
padding-box
border-box
margin-box

!!! 很重要
box-sizing: content-box  // 預設, 另外只有 border-box 這選項
指 width 是要做用在哪一個 box 上

## inline / block / inline-block
!!! inline 會遇到空白的問題 , 無法設定寬高
<span>aa</span>
<span>aa</span>
<span>aa</span>

畫面上會長這樣：
aa aa aa

會自動加上空白

!解決方法
1. 黏再一起
<span>aa</span><span>aa</span><span>aa</span>

2. 尾巴接下一行
<span>aa</span
><span>aa</span
><span>aa</span>

3. 用註解
<span>aa</span><!--
--><span>aa</span><!--
--><span>aa</span>

4. 用負的 margin 讓他靠在一起
span {
  margin: -2px;
}

5. [最推薦] 使用 font-size: 0  // font-size 小於12 都會是 12, 除了 0
"parent tag" {
  font-size: 0;
}
span {
  font-size: 12px;
}

6. 歪法 // 概念上就歪了, 因為子曾類型被改變了, 不在是 inline 物件
"parent tag" {
  display: table;
}

inline 物件
> margin top/bottom 無效
> padding top/bottom 會有奇怪效果 -> 不要去使用 (空間沒有被撐開)
margin/padding left/right -> OK

模擬情境
1. 今天有一個 <a> 的超連結, 想讓他變成按鈕
2. background-color , color , text-decoration: none;
3. width: 50; height: 40; -> 沒作用 -> 因為是 inline 物件
4. border-radious: 50px; padding: 10px 30px;
5. [關鍵]加上 display: inline-block

inline 會受到 text-align 的影響, block 不會
使用方式：在父層設定：text-align: center/left/right  // 所有子子孫孫都會受到影響, 因為跟文字相關, 會被繼承

inline 無法使用 transform  
// transform: rotate(30deg) , scale(2) 
// 無效, 但只要加上 block 的特性就可以：display: inline-block

!!! vertical-align : inline物件 與 inline物件之間的垂直對齊

文字總共有四條線
頂線
中線
基線 (一班以此為對齊: baseline)
底線

基線 & 底線 中間有空間
img 也是 inline 物件, 所以下方會有小小空白
[解法] 調整垂直對齊的線即可 : 
img {
  vertical-align: middle / top / bottom 都可以, 不要基線就好
}
[另一種解法] 
img {
  display: block;  // 原因是 block 不對齊基線 (inline 物件才有對齊基線的問題), 這邊很多都可以, 只要不是 inline ...
}
