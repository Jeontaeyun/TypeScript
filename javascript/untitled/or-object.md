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
| 객체.toString\(\); |  |
| 객체.valueOf\(\); |  |
| Object.create\(prototype, 속성들\); | 객체를 생성하는 방법 중 하나입니다. |
| Object.defineProperties\(객체, 속성들\); |  |
| Object.defineProperty\(객체, 속성, 설명\); |  |
| Object.getOwnPropertyDescriptor\(객체, 속성\); |  |
| Object.freeze |  |
| Object.seal |  |
| Object.preventExtensions |  |
| Object.keys\(\); |  |
| typeof |  |
| delete obj.key | 객체 내의 속성을 지울 수 있습니다. 성공하면 true 실패하면 false를 반환합니다. |

