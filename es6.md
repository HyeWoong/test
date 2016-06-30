# ES6 스타일 가이드
## 1.유형 (Type)

**Primitives:** 원시형(Primitive type)은 그 값을 직접 조작합니다.

* string
* number
* boolean
* null
* undefined

    const foo = 1;<br/>
    let bar = foo;<br/>
    bar = 9;<br/>
    console.log(foo, bar); // => 1, 9

