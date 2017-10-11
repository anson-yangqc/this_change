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

```javascript
function cat(){
	this.food = "fish"
}
cat.prototype.say = function(){
		console.log("I love "+this.food);
	}

var blackCat = new cat();
blackCat.say();//I love fish

function dog(){
	this.food = '狗粮'
}
var whiteDog = new dog()
blackCat.say.call(whiteDog);//I love 狗粮
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

## es6类的绑定（react常用）
```javascript
constructor(){
	super()
	//初始化state
	this.state = {}
	//绑定this
	this.addComment = this.addComment.bind(this);
}
```
```javascript
<p><button type="button" onClick={(this.add).bind(this)}>提交</button></p>
第一个this指实例
第二个this是说add方法里面的this用实例作this
```
