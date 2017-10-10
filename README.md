## this指向的是调用它的对象
* show(); //show里面的this指向的是window
* webigs.show(); //show里面的this指向的是webigs

## call
```javascript
    this.showResdiv.call(this);//传入什么，this就指向什么
```
## apply
* 跟call用法一样

## bind
```javascript
    gMarker.addListener('click', function() {
			this._resultClick && this._resultClick(result,infowindow);
    }.bind(this)); //传入什么，this就指向什么
 ```
## var _this = this
* 保存this指针方法
