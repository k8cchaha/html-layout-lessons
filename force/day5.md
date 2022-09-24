# day5
!important > animation > inline-style > ID > class > tag > * > 繼承

ID, class, tag, * 是選取器
!important, inline-style 是屬性

inline style : 直接寫在 HTML 裡面的
!important : 對單一屬性做最高級別的優先權

參考：https://www.zhangxinxu.com/wordpress/2022/05/deep-in-css-cascade/

@layer
沒有在 layer 裡面的優先權會高於 layer 裡面的優先權
@layer aa {
  p {
    color: red;
  }
}
包在不同 layer 裡面的優先權是 看 layer 的順序
後面的比較高, 不管 id, class, tag ...
但在同一個 layer 內的還是會看

可以在一開始就決定 layer 的順序  // 好控制
@layer aa,bb;

layer 內可以再包 layer
父層的層級優先於子層, 同層才會比較選取優先權
@layer aa {
  p {
    color: blue
  }
  @layer aa-1 {
    .box {
      color: pink
    }
  }
}

也可拆開來寫
@layer aa {

}
@layer aa.aa-1 {

}

@layer 裡面若有 "!important", 在不同 layer 中的層級會反轉, 在前面的優先高
會有優先權反轉的狀況 : 發生在 layer 與 layer 和 layer 與原生CSS (不在 layer 內的)
子層優先會大於父層

下面會有作用的是 .box

p {
  color: white;
}

@layer aa {
  p {
    color: red  !important;
  }
  .box {
    color: blue  !important;
  }
}

@layer bb {
  p {
    color: yello !important;
  }
}

----

## inline , block
網頁當中所有物件可以區分為2大特性 : inline & block
inline : 
會跟其他東西通通排在一起, 橫向排列, 該換行還是會換行
span 是inline 類型的物件
img 也是
em, strong, a 也是

block : 
區塊, 特性是不疃內容有多少都佔滿一整列的空間, 預設的寬度是 auto, 預設的情況下, 寬度是父曾的寬度

margin 是物件外圍的空間
margin: auto 這關鍵字的意思是 "把剩餘空間拿來做分配"
margin-left: auto -> 把剩餘空間都給左邊
margin-right: auto -> 把剩餘空間都給右邊
所以上面兩行合在一起就居中了

所以今天針對 "block" 物件要水平置中, 很常用到 margin : auto

若 block 想要垂直居中：
為何 margin-top , margin-bottom 不會有效果 
-> 因為 block 佔據的空間高度跟他內容高度是一樣的, 所以沒有剩餘的垂直空間 (寬度則是整個橫列都是他的)
-> 有剩餘空間才能做分配

若圖片想要居中
-> img 是 inline 物件 -> 可以用 text-align 做水平置中, 屬性要設在 parent (針對內容的 inline 物件) 
-> vertical-align 是在行裡做垂直置中, 針對 inline 物件做垂直置中, 但只有在該行高內
-> 也可以把 img 變成 block, 就可以用 margin 做居中

block 的物件可以設定高度
inline 的對寬高的設定都沒作用
===

可以利用 display 屬性改變 inline or block
若 inline 改成 block 就會佔掉一整行的空間了

===

只要把一個物件設定成 flex, 本身可以設定寬跟高 (類似 block)
可以對底下第一層的子曾物件呈現橫排的效果 & 並可以轉換成類似 block 的特性

img 的寬度常用 : 100% 跟父層一致

雷！inline-block 與 inline-block 之間有個 3px 左右的空間, 

用 flex-wrap 可以檢查寬度是否精準
( border, padding, margin )