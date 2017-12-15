



Step1.製作時針分針秒針樣式
利用class hand製作時針分針秒針的樣式

Step2.利用取得當前時間來計算出時鐘對應的角度
寫一個function setDate()取得當前時間,再計算時針分針秒針的角度
利用element.style.tranform做出位移的感覺

Step3.設定計時器
利用setInterval(setDate, 1000);每秒取得當前時間





Javascript語法筆記

Date()
  取得時間的函數，一定要搭配new來使用new Date()
  date.getSeconds():取得當前秒數
  date.getMinutes():取得當前分鐘
  date.getHours():取得當前小時

setInterval()
```
  setInterval(setDate, 1000);

```
  定時器，有兩個參數setInterval(callback, time)
  第一個是要執行的function，第二個是時間

let&const
  使用let及const宣告變數
  let宣告的值可變
  const則不可變
  作用域與var不同
  let及const是block內
  var則是function內


css語法筆記

box-shadow
  第一次用的css, box-shadow屬性將一個或多個陰影附加到元素。


transform: translateY(t)
  第一次使用的css, 指定元素由參考點縱向移動
  t代表移動向量的座標
  [參考資料](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/translateY)



transform:rotate();
  旋轉物件，數值的後方要加上角度deg,以下範例:
  ```
  transform:rotate(90deg);
  ```
  正值為順時針，負值為逆時針旋轉。

transform-origin: 100%;
  第一次使用,可以用來設置旋轉物件的軸心




在範例中,為了要讓指針的原點都從12點整開始,在計算時間的function最後都加上90
改成在.clock-face整個區域轉90度
這樣就不用計算function時還要再+90度



[Demo](https://milletbard.github.io/javascript30/02_JSandCSS_Clock/milletbard.html)
