


今天要寫一個類似圖像編輯器的東西

![](/images/blog03.png)



首先是這個第一次看到的東西


### :root

:root可以宣告全局css變數
[參考](https://developer.mozilla.org/zh-TW/docs/Web/CSS/:root)

```
:root {
	--base:#ffc600;
	--blur:10px;
	--spacing:10px;
}
```




+ 在要呼叫變數的選擇器裡面，使用var()呼叫該變數，可以把它想成function
+ 變數有分大小寫

```
img {
	background: var(--base);
	padding: var(--spacing);
	filter: blur(var(--blur));
}
```



### 回到js,先宣告一個變數再使用querySelectorAll返回class controls裡的input

```
	const inputs = document.querySelectorAll('.controls input') 
```



### 一個function,功能是聲明屬性的新值

```
	function handleUpdate() {
		const suffix = this.dataset.sizing || '';
		document.documentElement.style.setProperty(`--${this.name}`, this.value + suffix);
	}
```



### 然後看看是不是有值被改變

```
	inputs.forEach(input => input.addEventListener('change', handleUpdate));
    inputs.forEach(input => input.addEventListener('mousemove', handleUpdate));
```



***


### document.querySelectorAll()

越來越熟悉的querySelector和querySelectorAll
但後者返回的是一個NodeList而不是一個Array
雖然它不是一個Array,但可以使用forEach()
[參考](https://developer.mozilla.org/nl/docs/Web/API/NodeList)


### this.dataset.sizing

可以抓取data-sizing的值,


### document.documentElement.style.setProperty

聲明屬性的新值

### element.addEventListener(event, function, useCapture)

傾聽一個事件,執行function




理解上有錯誤煩請告知
