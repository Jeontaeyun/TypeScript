# 프록시 객체\(ES6\)

## 프록시 객체 \| Proxy

 **프록시 객체는  기존 객체를 건들지 않고 새 기능을 추가하거나 기존 기능을 수정할 수 있는 객체**를 말합니다. 

바벨에서 지원하지 않아 IE에서는 사용할 수 없지만  최신 브라우저에서는 모두 지원합니다. 

| 프록시 구성  | 설명  |
| :--- | :--- |
| 타겟 | 목표하는 객체를 의미 |
| 핸들러  | 추가 또는 수정할 기능을 기술하는 부분으로 옵션을 가진다. |

 다음과 같은 방식으로 생성할 수 있습니다.

```javascript
const proxy = new Proxy(target, handler);
```

```javascript
const target = {};
const handler = {
    set: function(target, name, value){
        console.log(`${name}가 ${value}로 설정되었습니다.`);
    }
};
const proxy = new Proxy(target, handler);
proxy.zero = 'Zero'  // zero가 Zero로 설정되었습니다.
target.zero; // undefined
```

| 프록시 옵션 | 설명  |
| :--- | :--- |
| get\(target, proxyKey\) | 속성 값을 호출할 때 어떤 행동을 하는지 정의하는 옵션  |
| set\(target, porxyKey, proxyValue\)  | 속성 값을 설정할 때 어떤 행동을 하는지 정의하는 옵션 |
| has |  |
| deleteProperty |  |
| apply | 함수를 호출할 때 그 행동을 가로채 프록시 객체에 대신 호출하는 옵션  |
| construct\(target, args\) | new를 통해서 함수를 호춯할 때 그 행동을 가로채 프록시 객체에 대신 호출하는 옵션  |
| getOwnPropertyDescriptor |  |
| defineProperty |  |
| getPrototypeOf |  |
| setPrototypeOf |  |
| ownKeys |  |
| preventExtensions |  |
| isExtensible |  |

 프록시를 이용하여 객체 생성을 재정의할 수 있으며, 객체의 여러가지 기능을 확장할 수 있게 해줍니다. 어떤 특정 동작을 할 때마다 설정해 둔 핸들러가 실행되기 때문에 자동화 작업에도 사용할 수 있을 것 같습니다. 

