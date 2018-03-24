1. 在函数里用let定义变量，而非var
2. 当使用常量 const 声明时，请使用大写变量，如：CAPITAL_CASING
3. let 和 const 声明只在最靠近的一个块中（花括号内）有效
4. const 在声明时必须被赋值

## 箭头函数  ##
就是函数的一种简写形式，使用括号包裹参数，跟随一个 =>，紧接着是函数体

箭头函数没有原型属性：prototype=undefined

    var getPrice = function() {
      return 4.55;
    };
    var getPrice = () => 4.55;

**当然，箭头函数不仅仅是让代码变得简洁，函数中 this 总是绑定指向对象自身,箭头函数没有它自己的this值，箭头函数内的this值继承自外围作用域。它的this是派生而来的，根据“词法作用域”派生而来。**

    function Person() {
	  //如果不把this存起来，哪么这时this指向的是window
      var self = this;
      self.age = 0;
     
      setInterval(function growUp() {
    	self.age++;
      }, 1000);
    }
    
	//ES6..............

    function Person(){
      this.age = 0;
 
      setInterval(() => {
    	// this 指向 person 对象
    	this.age++;
      }, 1000);
    }

## 解构： ##
解构可以避免在对象赋值时产生中间变量

    function foo() {
      return [1,2,3];
    }
    let arr = foo(); // [1,2,3]
     
    let [a, b, c] = foo();
    console.log(a, b, c); // 1 2 3


     
    function bar() {
      return {
	    x: 4,
	    y: 5,
	    z: 6
      };
    }
    let {x: x, y: y, z: z} = bar();
    console.log(x, y, z); // 4 5 6

## 类 ##
ES6 中有 class 语法。值得注意是，这里的 class 不是新的对象继承模型，它只是原型链的语法糖表现形式。
函数中使用 static 关键词定义构造函数的的方法和属性

    static loadAll() {
    	console.log("Loading all tasks..");
	}
**继承**

    class Car {
      constructor() {
    	console.log("Creating a new car");
      }
    }
     
    class Porsche extends Car {
      constructor() {
    	super();
		console.log("Creating Porsche");
      }
    }
     
    let c = new Porsche();
    // Creating a new car
    // Creating Porsche
extends 允许一个子类继承父类，需要注意的是，子类的constructor 函数中需要执行 super() 函数。