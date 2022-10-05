# day10

## grid
display: grid
grid-auto-flow: column // 預設是 row, 資料排列的流向
grid-template-columns: 200px 200px 200px;
grid-template-columns: repeat(3, 100px)
grid-template-columns: 200px repeat(3, 100px)
grid-template-columns: repeat(3, 1fr)
grid-template-columns: 1fr 1fr 1fr
gap: 10px
gap: 10px 20px
若寫死寬度或高度 加上 gap 可能會超過髖骨的/高度 （用 fr 就不會有問題)
fr 概念就跟分配剩餘空間一樣

item 也可以給 width/height

這裡也有 justify-content 的屬性 // 控制格子
center

alifn-content // end 格子往下移

有剩餘空間, item 就可以用 margin: auto;