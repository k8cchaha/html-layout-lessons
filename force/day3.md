# Day3

aside
雜誌, 新聞較常用到
與主題間接相關

small
旁注, 附註內容 (法律, 版權)

網頁最小的 fz 是 12

早期 class 命名
不要以色彩命名 .red
不要以位置 .top
不要以尺寸 .big
不要以標籤 .h1


以下三個以往都是 div 加 class 區分


header
不是只能用在頁面的頂端, 可以用在文章的頭部區

main
頁面主要區域
應該是要獨一無二的

footer

最重要！！！
article, section

想像成一本小說
一個章節：section

article
  h1
  section
    h2
  section
    h2


首頁
清單頁
內容頁
//表單頁
聯絡我們頁

a 
href="http://"
target="_blank" 指的是在哪個框框開啟, blank 指新視窗
若沒寫 target, 在原頁面跳轉
href="02.html" 也可以直接連到其他頁面
href="#bottom" 錨點連結
href="02.html#about"

<section id="about">

html {
  scroll-behavior: smooth; // 順暢的滑動
}

p*30>Lorem
ctlorem

nav : 導覽頁, 頁面的選單

一個網頁可以有多個 nav
整個網站的, 本頁面內ㄉ

nav 
  ul
    li  a
    li  a


<form action="">
  <label for="user_name">姓名:</label>
  <input type="text" id="user_name">

  <br>

  // 不需要 for
  <label>
    姓名:
    <input type="text">
  </label>
</form>

姓名 <input type="text"
密碼 <input type="password"
信箱 <input type="email"
網站 <input type="url"
電話 <input type="tel"
生日 <input type="date"
時間 <input type="time"
年齡 <input type="number" min="18" max="50"
檔案 <input type="file"
區間 <input type="range"
色彩 <input type="color"
搜尋 <input type="search"
div
  span 興趣： /span
  label
    <input type="checkbox" 釣魚
  label
    <input type="checkbox" 上網

div
  span 性別： /span
  label
    <input type="radio" name="sex">男
  label
    <input type="radio" name="sex">女


div
  input type="submit"
  input type="reset"
  input type="button" value="我是按鈕"

!!!! 用手機會開啟對應的數位鍵盤

<textarea name="" id="" cols="30" rows="4"></textarea>

<select name="" id="">
  <option value="">請選擇</option>
</select>

<button></button>  // 比較適合搭配 css

<fieldset>
  <legend>性別:</legend>
  <label>
    <input type="radio" name="sex">男

</fieldset>
// fieldset 把元素做分組, 較少用


// label 是inline類型的物件

// chrome套件: html5 outliner 看網站 seo
// pesticide for 看頁面結構
// simple-debug css

.btn {
  display: inline-block;
  padding: 10px 20px;
  text-decoration: none;
  color: #fff;
  bg-color: #fa0;
  margin: 2px;
  border: none;
  border-radius: 6px;
  font-size: 22px;
  font-weight: normal;
  cursor: pointer;
}

.btn:hover{
  bg-color: #f00
}

<div class="btn">
<span class="btn">
<a class="btn">
<button class="btn">
<label>
<p>
<h1>


TibaMe   註冊, 主題課程
網頁多層選單