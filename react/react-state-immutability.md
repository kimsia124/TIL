# React State Immutability

리액트가 State Immutability를 유지하는 이유:

- 화면을 업데이트할 때, 변수의 레퍼런스를 비교하여 빠른 업데이트가 가능하도록 하기 위해.
- Side Effect가 발생할 확률을 낮추기 위해.



#### Immutable Object Variable을 만드는 방법

[object-rest-spread](https://github.com/sebmarkbage/ecmascript-rest-spread)를 사용한다:

```javascript
const object = { a: 1, b: 2, c: 3 };
const nextObject = { ...object, b: 2 }; //사본을 만들어서 b 값만 덮어 쓰기
```



array를 immutable하게 update 할 때는 concat()을 사용하면 편하다.

```javascript
const array = [
  { id: 1, value: true },
  { id: 2, value: true },
  { id: 3, value: false }
];

let nextArray = array.concat({ id: 4 });
```

