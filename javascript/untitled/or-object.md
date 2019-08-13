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
| Object.create\(prototype, 속성들\); | 객체를 생성하는 방법 중 하나입니다. |
| Object.defineProperties\(객체, 속성들\); |  |
| Object.defineProperty\(객체, 속성, 설명\); |  |
| Object.getOwnPropertyDescriptor\(객체, 속성\); | 속성의 설명 값을 불러옵니다.  |
| Object.freeze |  |
| Object.seal |  |
| Object.preventExtensions |  |
| Object.keys\(\); | 객체의 속성명을 모두 가져와 배열로 만듭니다. enumerable이 false인 것은 제외합니다.  |
| typeof | 변수의 타입을 알려줍니다. null과 array는 object로 처리되니 이 부분을 주의해야 합니다. |
| delete obj.key | 객체 내의 속성을 지울 수 있습니다. 성공하면 true 실패하면 false를 반환합니다. |

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

