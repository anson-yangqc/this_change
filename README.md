## this指向的是调用它的对象
* show(); //show里面的this指向的是window
* webigs.show(); //show里面的this指向的是webigs
```javascript
function one(initoption){
        this.age=120
    	one.prototype.add=function(){
            this.countryClick()
    	}
    }
    var two =new one(init);
    two.add() // 120
```

## call
```javascript
    this.showResdiv.call(this);//传入什么，this就指向什么
```
```javascript
function one(name){
	this.name = name
}
function two(name){
	one.call(this,name);
}
var sec = new two('two');
alert(sec.name);
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

## $.proxy()
```javascript
$(document).ready(function(){
  var objPerson = {
    name: "John Doe",
    age: 32,
    test: function(){
      $("p").after("Name: " + this.name + "<br> Age: " + this.age);
    },
	show:function(){
		alert('show')
	}
  };
  $("button").click($.proxy(objPerson,"test"));
});
</script>
```
