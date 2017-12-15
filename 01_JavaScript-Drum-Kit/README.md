



透過js做出鍵盤鋼琴的效果,並當按下琴鍵時產生一個效果
在按下其他琴鍵後會關閉特效並在新的按鍵中啟用.


Step1.新增keydown listener

利用window.addEventListener('keydown',playSound);
來監聽鍵盤動作


Step2. 建立function playSound

1. 利用監聽到的e.keyCode來取得對應的audio標籤以及該按鍵的div
2. 判斷傳入的e.keyCode是否有對應的audio標籤, 沒有的話則return
3. 將對應的div加上playing樣式, 產生對應的css效果
```
    key.classList.add('playing');

```
4. 將對應的audio的播放時間改為0 
```
    audio.currentTime = 0;
```
5. play()


Step3. 新增Listener transitionend

1. 找出className='key'的元件
2. 當該元件觸發結束之後,呼叫removeTransition


Step4. 建立function removeTransition

1. 判斷e.propertyName 是否為‘transform‘,不是的話return
2. 是的話移除playing樣式




#forEach
```
   arr.forEach(callback function)
```
語法理解
```
    var cats = ['NeiNei', 'MaiMai'];
   
    //for迴圈
    for(var i = 0; i < cats.length; i++) {
    	console.log(cats[i]);
    }

    //forEach
    cats.forEach(function(data){
  	   	console.log(data);
  	});
  ```





#ES6的新語法 


  #傳統寫法
```
function mycat1(cat) { console.log('my cat\'name is ' + cat ) } ;
```
  箭頭函式
```
var mycat1 = cat =>  console.log('my cat\'name is ' + cat ) ;
```
  ＊如果沒有參數或是有兩個參數,要加上括號
```
var mycat2 = () => console.log('my cat\'name is NeiNei ' ) ;
```

```
var mycat3 = (cat1, cat2) => console.log('my cats\'name is ' + cat1 + ' and ' +cat2 ) ;
```


  #Template literals
   模板字串

[參考連結](https://developer.mozilla.org/zh-TW/docs/Web/JavaScript/Reference/Template_literals)

第一次使用,還問朋友到底怎麼打出來（以為是注音符號的ˋ四聲）
利用  \`  反引號來組合字串,範圍內可以利用${}加上變數操作
允許嵌入運算式的字串字面值（string literals）,可以透過樣板字面值來使用多行字串及字串內插（string interpolation）功能



```
    const audio = document.querySelector(`audio[data-key="${e.keyCode}"]`);

    const key = document.querySelector(`.key[data-key="${e.keyCode}"]`);
```



#addEventListener

  #第一次使用的transitionend
[參考資料](https://developer.mozilla.org/en-US/docs/Web/Events)




#加入點擊功能

+getAttribute  返回元素的指定名稱的屬性的值
[參考資料](https://www.w3schools.com/jsref/met_element_getattribute.asp)

```
    function playSound(e) { 
    let key1 = e.keyCode || this.getAttribute('data-key');

    const audio = document.querySelector(`audio[data-key="${key1}"]`);
    const key = document.querySelector(`.key[data-key="${key1}"]`);

    if(!audio) return; // stop the function
    key.classList.add('playing');
    audio.currentTime = 0;
    audio.play(); // play sound
    
    keys.forEach(key => key.addEventListener('click', playSound))
    //加入click功能
  };
```

[DEMO](https://milletbard.github.io/javascript30/01_JavaScript-Drum-Kit/milletbard.html)


















