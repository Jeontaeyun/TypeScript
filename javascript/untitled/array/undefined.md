# 유사배열

## 유사배열 \| Array-like

### 유사 배열이란?

 자바스크립트에서 배열은 특수한 형식의 객체입니다. 즉, 내부적으로 정의된 객체입니다. 이러한 배열을 만드는 방법은 **배열 리터럴 \(\[...\]\)**로 선언하는 방식과 **new Array\(\)** 방식으로 생성하는 방법입니다.

 하지만, 다음과 같이 \[\]로 감싸져있지만 배열이 아닌 **유사 배열**도 존재합니다.

```text
NodeList [div, div, div, div, div, ...]
```

 **유사 배열\(Array-like\)** 은 배열과 같이 key값으로 숫자를 가지고, length를 나타내는 메소드가 있는 객체를 말합니다. 보통 다음과 같은 방식으로 구현됩니다.

함수의 매개변수를 나타내는 **arguments도 유사배열**입니다. 

```javascript
const arrayLike = {
    0 : "div",
    1 : "div",
    2 : "div",
    length: 3
}
```

 여기서 주의할 점은 **유사 배열의 경우 배열에서 사용되는 메소드를 사용할 수 없다는 점** 입니다.

{% hint style="info" %}
**Array.isArray\(\)**

유사 배열을 배열의 static 메소드인 isArray로 판단하면 false를 반환합니다. 
{% endhint %}

### 유사 배열에서 배열 메소드를 사용하는 방법

 유사 배열에서 배열 메소드를 사용하기 위해서는 배열의 프로토타입을 복사해야 합니다. 

```javascript
Array.prototype.forEach.call(nodes, function(item){console.log(item})
[].forEach.call(nodes, function(item){console.log(item)})
```

  call은 객체의 메소드에 붙어 내부의 this를 바꾸어주는 역할을 합니다. 

 최신 자바스크립트에서는 Array.from\(\)메소드를 통해 유사 배열을 손 쉽게 배열로 바꿀 수 있습니다.

```javascript
Array.from(유사배열).forEach(function(item){console.log(item)});
```

