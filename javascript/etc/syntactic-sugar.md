---
description: >-
  해당 페이지는 자바스크립트를 이용해서 프로그램을 구현할 때 알아두면 문법적으로 유용한 Syntactic Sugar를 정리하기 위한
  페이지입니다.
---

# Syntactic Sugar

## Syntactic Sugar란?

 Syntactic Sugar는 자바스크립트를 이용하여 프로그램을 구현할 때 알아두면 유용한 문법적 기술입니다. 위키피디아의 정의를 보면 사람이 이해하고 표현하기 쉽게 디자인된 프로그래밍 언어 문법입니다. 이를 통해서 길게 구현할 코드를 좀 더 짧고 간결하게 구현할 수 있습니다.

### 01. 보호 연산자와 기본값 연산자

 자바스크립트를 이용한 코드들을 보면 && 과 \|\| 을 이용한 코드를 많이 볼 수 있습니다. 특히 리액트에서는 조건부 렌더링으로 보호연산자\(&&\)를 쓰기도 합니다. 보통 &&과 \|\| 는 true 나 false 를 처리하는 논리연산자로 사용되는데 0, '', NaN, null, undefined 등의 값이 false가 되는 특성을 이용해 유용하게 사용할 수 있습니다.

#### 보호 연산자 \| Guard Operator

 보호 연산자는 리액트 프레임워크에서 조건부 렌더링을 할 때 사용하는 \(&&\)를 떠올리면 이해하기가 쉽습니다.

```text
const condition = false;
const guardOperator = condition && (...);

console.log(guardOperator)
// undefined
```

```text
const condition = true;
const guardOperator = condition && (...);

console.log(guardOperator)
// (...)
```

 위와 같 특정 조건\(Condition\)에 맞춰서 그 뒤를 반환하는지에 대한 역할을 합니다. 즉,  condition이 true이면 \(...\)을 반환하고 아닐 때는 undefined를 반환합니다.

#### 기본값 연산자 \| Default Operator

 기본값 연산자는 리액트 프레임워크에서 삼항 연산자를 대신해 기본값\(default\)을 정할 때 많이 사용됩니다.

```text
const condition = false; // null, undefined ...
const defaultOperator = condition || deafult;

console.log(defaultOperator);
// default
```

```text
const condition = "this is Default"; // true
const defaultOperator = condition || deafult;

console.log(defaultOperator);
// "this is Default"
```

 위와 같이 앞의 값이 없을 때는 default 값을 반환하고 condition에 값이 있을 때는 condition의 값을 반환합니다.

### 02. 불린 변환

 해당 값이 true 인지 false인지를 체크하기 위해 느낌표 두개를 사용할 수 있습니다.

```text
const a = [];
const b = NaN ;
!!a    // true
!!b    // false
```

### 03. 함수 호출 

 함수 호출은 if/else 문법으로 함수를 조건부 호출하는 번거로움을 줄이기 위해서 고안된 방법이다. 

```text
// Before
if(success) {
    pro.start();
}
else{
    pro.stop();
}

// After
const method = (success ? 'start' : 'stop');
pro[method]();
```

 자바 스크립트는 객체의 속성을 object\['method'\] 방식으로 호출할 수 있다는 점을 이용한 구현 방식이다.



