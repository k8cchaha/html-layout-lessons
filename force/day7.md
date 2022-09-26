# day7

若要做 menu > hover > 下方長出寬的內容
Menu 按鈕：
display: grid
grid-auto-flow: column
子內容：
display: grid

## flex
父層: 
display: flex
flex-direction
flex-wrap
flex-flow: wrap direction
justify-content
align-content
align-items
gap

子層
order
align-self
flex-grow
flex-shrink
flex-basis

flex: grow shrink basis
flex: 1 -> 1 1 0%

-----

排版時代演進：
table
--
float
inline-block
--
flex
grid

-----

主軸的方向是跟著語言, 書寫的方向 (由左到右是比較粗淺的說法)
以下兩個css屬性都會影響：
- direction
- writing-mode
html  也會有一個屬性 dir="rtl" 也可以改變  // 中東國家, 由右至左

flex-direction 改變主軸方向  // main axis

父層設 flex
子層若沒設定高度, 預設會填滿整個高

flex-wrap: 控制交叉軸的方向 // 設定 wrap 就可以換列 , 還有 wrap-reverse 可以反向

justify-content : 剩餘空間怎麼分配
space-around : 每個子物件的左右兩邊都被分配到一份  1<3>2<3>2<3>1
space-evenly : 均分所有的空間  1.5<3>1.5<3>1.5<3>1.5

align-conntent : 若有兩個列, 父高 - 第一列最高 - 第二列最高, 再平均分配給兩個列 // 預設
> 控制 "彈性列" 在 父層空間 交叉軸 的對齊與分佈

flex 加上 margin 的 auto 可以做出各種變化

鏡像
justify-content {
  center
}

item:nth-child(-n+3) {
  margin-top: auto;
}

content 是控制空間
item 是控制子物件

align-items: 彈性列當中, 交叉軸的位置
預設值是 stretch 所以會撐開 (if no set height)

flex-grow
子物件在 "主軸"方向 上剩餘空間的伸展直 (剩餘空間分給誰)
flex-grow: 2  // 拿兩份

所以有一種應用
多個div 等分
item 上的 css -> width: 0 + flex-grow: 1

-----

Amos 實作範例 (提拔我)
