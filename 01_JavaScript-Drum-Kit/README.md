


透過js做出鍵盤鋼琴的效果,並當按下琴鍵時產生一個效果
在按下其他琴鍵後會關閉特效並在新的按鍵中啟用.


Step1.新增keydown listener

利用window.addEventListener('keydown',playSound);
來監聽鍵盤動作


Step2. 建立function playSound

1. 利用監聽到的e.keyCode來取得對應的audio標籤以及該按鍵的div
2. 判斷傳入的e.keyCode是否有對應的audio標籤, 沒有的話則return
3. 將對應的div加上playing樣式, 產生對應的css效果
4. 將對應的audio的播放時間改為0 
5. play()


Step3. 新增Listener transitionend

1. 找出className='key'的元件
2. 當該元件觸發結束之後,呼叫removeTransition


Step4. 建立function removeTransition

1. 判斷e.propertyName 是否為‘transform‘,不是的話return
2. 是的話移除playing樣式







[Template literals](https://developer.mozilla.org/zh-TW/docs/Web/JavaScript/Reference/Template_literals)

模板字串

第一次使用,還問朋友到底怎麼打出來（以為是注音符號的ˋ四聲）
利用  \`  反引號來組合字串
允許嵌入運算式的字串字面值（string literals）,可以透過樣板字面值來使用多行字串及字串內插（string interpolation）功能


```
    const audio = document.querySelector(`audio[data-key="${e.keyCode}"]`);

    const key = document.querySelector(`.key[data-key="${e.keyCode}"]`);
```

















