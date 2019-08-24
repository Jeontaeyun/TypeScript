# 객체 \| Object

## 객체 \| Object

 Object 객체도 하나의 객체입니다. 하지만 모든 객체의 최상위 객체입니다. 사실 모든  객체는 Object 객체로부터 상속을 받기 때문에 모든 객체는 Object 객체의 메소드들을 사용할 수 있습니다.

### Object 객체 메소드

| 구분  | 설명  |
| :--- | :--- |
| 객체.hasOwnProperty\(속성명\); | 객체의 속성이 상속받지 않은 속성인지 알려줍니다. 자신의 속성이면 true 부모의 속성이면 false를 반환합니다. |
| 객체.isPrototypeOf\(대상\); | 객체가 대상의 조상인지 ture, false로 알려줍니다.  |
| Object.getPrototypeOf\(객체\); | 객체의 prototype을 조회합니다. |
| Object.setPrototypeOf\(객체, prototype\); | 객체의 prototype을 설정합니다. |
| instanceof | 객체가 특정 생성자의 자식인지 조회할 수 있습니다.  |
| 객체.propertyIsEnumerable\(속성\); | 해당 속성이 열거 가능한 속성인지 알려줍니다. 열거 가능이란 for-in과 같은  반복문 안에서 쓸 수 있는지를 말합니다. |
| 객체.toString\(\); | 기본적으로 \[object Object\]와 같이 객체의 종류를 알려주고 사용자가 임의로 수정할 수 있습니다.  |
| 객체.valueOf\(\); | 객체의 기본 값을 의미합니다.  |
| Object.create\(prototype, 속성들\); | 객체를 생성하는 방법 중 하나 입니다. |
| Object.defineProperties\(객체, 속성들\); | 객체의 속성을 자세하게 정의하는 메소드입니다. |
| Object.defineProperty\(객체, 속성, 설명\); | 객체의 속성 중 configurable이 true인 데이터의 설명을 다시 정의합니다. |
| Object.getOwnPropertyDescriptor\(객체, 속성\); | 속성의 설명 값을 불러옵니다.  |
| Object.freeze\(객체\) | writable을 false로 해도, value가 객체인 경우에는 객체의 속성을 바꾸는 것을 막지 못하는데 이 때 freeze를 사용해 객체 전체를 바꾸지 못하게 고정할 수 있습니다. |
| Object.seal\(객체\) | 속성의 추가, 제거를 막고 configurable을 false로 바꿉니다. 속성 값은 writable이 true일 때 바꿀 수 있습니다. |
| Object.preventExtensions\(객체\) | 속성의 추가만 막고 속성 제거, 값 변경, 설정 변경은 가능합니다.  |
| Object.keys\(\); | 객체의 속성명을 모두 가져와 배열로 만듭니다. enumerable이 false인 것은 제외합니다.  |
| typeof | 변수의 타입을 알려줍니다. null과 array는 object로 처리되니 이 부분을 주의해야 합니다. |
| delete obj.key | 객체 내의 속성을 지울 수 있습니다. 성공하면 true 실패하면 false를 반환합니다. |
| **Object.assign\(목표, 소스1, 소스2, ...\)** | 객체를 얕은 복사하는 메소드입니다. 깊은 복사는 할 수 없습니다. 소스들을 목표에 모두 복사해서 합칩니다. 중복된 값은 덮어 씌웁니다. |
| **Object.is\(값1, 값2\)** | 두 값이 같은 지 비교합니다.  |
| **Object.values\(객체\)** | Object.keys\(\)에 대응하는 메소드로 객체의 enumerable한 속성값들만 배열로 만들어 줍니다. 함수형 프로그래밍에 도움됩니다. |
| **Object.entries\(객체**\) | Object.keys와 Object.values를 함쳐놓은 메소드로 함수형 프록래밍에 도움이 됩니다.  |

{% hint style="info" %}
**네이티브 자바스크립트로 깊은 복사를 하는 방법**

네이티브 자바스크립트로 깊은 복사를 하는 방법은 아직 제공되지 않는다. 따라서 cutom method를 만들거나, JQuery나 Lodash와 같은 서드 파티 라이브러리를 사용해야 한다.

Lodash와 Underscore, JQuery등은 자바스크립트를 다룰 때 발생하는 어려움을 도와주는 라이브러리이다. C++의 STL과 비슷하다. 
{% endhint %}

{% hint style="info" %}
**Enumerable \| 열거할 수 있는, 셀 수 있는** 

JS 객체 속성은 Enumerable\(열거자\) 또는 Nonenumerable\(비열거자\)로 정의할 수 있으며, 이들을 탐색, 검색, 반복할 수 있는 build-in 메소드를 제공하고 있습니다.
{% endhint %}

#### 객체 속성 

| 구분  | 설명 |
| :--- | :--- |
| writable | 속성값을 변경할 수 있는지에 대한 여부를 나타냅니다 |
| enumerable | for...in 반복 문등 객체를 이용한 반복문 안에서 사용 가능한지를 나타냅니다 |
| configurable | 속성의 설명을 바꿀 수 있는지 나타냅니다 |
| value | value는 속성의 값을 나타냅니다 |
| get | get은 속성의 값을 가져올 때 사용합니다 |
| set | set은 속성의 값을 설정할 때 사용합니 |

기본적으로 객체 속성 writable, enumerable, configurable은 false입니다.

### 동적 속성 생성 \(ES+\)

 ES2015+부터는 속성의 이름에 변수의 값이 사용될 때 자체적으로 계산해주는 동적 속성 생성이 가능하게 되었습니다. 

```javascript
const value = 1;
const object = {
    ['hi_'+value] : "hi"
}

// object = {
    hi_1 : "hi"
}
```

 ES2015 이전에는 속성의 이름에 변수를 넣으면 자동으로 계산을 하지 못해서 다음과 같이 사용해야 했습니다.

```javascript
var value = 1;
var object = {

}
object['hi_'+value] = "hi"
// object = {
    hi_1 : "hi"
}
```

