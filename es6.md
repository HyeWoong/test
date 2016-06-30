# ES6 스타일 가이드
## 1.유형 (Type)

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
