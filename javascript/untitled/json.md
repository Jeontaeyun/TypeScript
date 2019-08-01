---
description: JavaScript Object Natation
---

# JSON

## JSON

 웹에서는 데이터를 교환하기 위해서 특정 형식을 서로 지켜야합니다. 가령 HTML도 하나의 데이터이고, CSS도 하나의 데이터입니다. 

  JSON은 이런 데이터를 교환하는 형식 중 하나입니다. JavaScript Object Notation이라는 약어와 같이 **자바스크립트 문법을 빌린 데이터 교환 형식**입니다.

```javascript
{
    "name" : "Stark",
    "age" : 25,
    "nickname" : "Ironman",
    "major" : "Electronic Engineering"
}
```

 저자를 JSON의 형태로 표현하면 위와 같은 방식이 됩니다. 위와 같이 자바스크립트의 객체 형식\(키-값\)으로 데이터를 교환하는 것을 JSON이라고 합니다.

 기존에는 JSON의 역할을 하기 위해 XML이라는 방법을 사용했습니다. 하지만, 최근에는 JSON의 간결함으로 인해 JSON을 많이 사용합니다.

 그리고 JSON을 사용할 때 주의해야 할 점이 있습니다.

* 함수를 사용하면 안됩니다.
* 작은 따옴표 대신 반드시 큰 따옴표를 사용해야 합니다.
* 키에도 큰 따옴표를 사용해야 합니다.

### JSON 객체 

 자바스크립트에서는 JSON 객체를 사용할 수 있도록 JSON 객체를 제공합니다. JSON 객체의 자주 사용하는 메소드는 다음과 같습니다.

| 구분  | 설명 |
| :--- | :--- |
| JSON.stringify\(json\_data\); | JSON형식의 데이터를 문자열로 만드는 메소드 |
| JSON.parse\(string\) | 문자열 형식의 JSON을 다시 JSON데이터로 만드는 메소 |

 위의 메소드는 서버가 객체를 이해 못할 경우를 위해서 문자열 형태의 데이터로 제공하고 해당 서버로 부터 온 정보를 JSON형태로 가공하기 위해 사용됩니다. 

