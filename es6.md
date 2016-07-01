# ES6 
## 변수선언
너그러운 var
엄격한 let, const

var foo = 'bar1';
var foo = 'bar2';

let foo = 'bar1';
let foo = 'bar2';
// ERROR: Uncaught SyntaxError: Identifier 'foo' has already been declared

기존 ES5에서 변수 선언은 var를 사용하였는데 var는 중복선언이 가능하며, 어떤 자료형이나 담을수 있었다.
ES6에서는 let과 const 라는 새로운 선언 방법이 생겼다.

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

