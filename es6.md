# ES6 
## 변수선언
너그러운 var
엄격한 let, const

기존 ES5에서 변수 선언은 var를 사용하였는데 var는 중복선언이 가능하며, 어떤 자료형이나 담을수 있었다.
ES6에서는 let과 const 라는 새로운 선언 방법이 생겼다. (const 상수선언, let 변수선언)

var foo = 'bar1';
var foo = 'bar2';

let foo = 'bar1';
let foo = 'bar2';
// ERROR: Uncaught SyntaxError: Identifier 'foo' has already been declared

const foo = 1;
foo = 2;
// ERROR

**Primitives :** 원시형(Primitive type)은 그 값을 직접 조작합니다.

* string
* number
* boolean
* null
* undefined

    const foo = 1;
    let bar = foo;
    bar = 9;
    console.log(foo, bar); // => 1, 9

**Complex :** 참조형(Complex type)은 참조를 통해 값을 조작합니다.

* object
* array
* function

    const foo = [1, 2];
    const bar = foo;
    bar[0] = 9;
    console.log(foo[0], bar[0]); // => 9, 9

기존 var는 함수범위, let과 const는 블록범위를 갖는다.

var a = 1;
{
    var a = 2;
}
console.log(a); // 2

let a = 1;
{
    let a = 2;
}
console.log(a); // 1

큰 프로젝트나 복잡한 함수에서 오류를 발생할수있으니 var를 사용하지 않도록 한다.



## Class
기존 prototype 기반의 상속을 보다 명료하게 표현 합니다.
Class 문법은 새로운 객체지향 상속 모델을 제공하는 것은 아닙니다.
JavaScript class는 객체를 생성하고 상속을 다루는데 있어 훨씬 더 단순하고 명확한 문법을 제공합니다.

// ES5
'use strict';

function User(name){
  this._name = name;
}

User.prototype = Object.create(null, {
  constructor: {
    value: User
  },

  say: {
    value: function() {
      return 'My name is ' + this._name;
    }
  }
});

function Admin(name) {
  User.apply(this, arguments);
}

Admin.prototype = Object.create(User.prototype, {
  constructor: {
    value: Admin
  },

  say: {
    value: function() {
      var superClassPrototype =  Object.getPrototypeOf(this.constructor.prototype);
      return '[Administrator] ' + superClassPrototype.say.call(this);
    }
  }
});

var user = new User('Alice');
console.log(user.say()); // My name is Alice

var admin = new Admin('Bob');
console.log(admin.say()); // [Administrator] My name is Bob
// ES6
'use strict';

class User {
  constructor(name) {
    this._name = name;
  }

  say() {
    return 'My name is ' + this._name;
  }
}

class Admin extends User {
  say() {
    return '[Administrator] ' + super.say();
  }
}

var user = new User('Alice');
console.log(user.say()); // My name is Alice

var admin = new Admin('Bob');
console.log(admin.say()); // [Administrator] My name is Bob
