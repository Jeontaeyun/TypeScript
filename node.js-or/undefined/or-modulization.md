# 모듈화 \| Modulization

## 모듈화 

 노드는 코드를 모듈로 만들 수 있다는 점에서 브라우저의 자바스크립와 다릅니다. 

{% hint style="info" %}
**모듈**이란 특정한 기능을 하는 함수나 변수들의 집합입니다. 
{% endhint %}

 모듈로 만들어 두면 여러 프로그램에 해당 모듈을 재 사용할 수 있습니다. 자바스크립트에서 코드를 재사용하기 위해 함수로 만드는 것과 비슷합니다. 

### 모듈화 방법 

| 구분  | 설명  |
| :--- | :--- |
| const 변수명 = require\('모듈파일'\) | 모듈을 불러와 변수에 대입해주는 방법 require 메소드를 이용한다.  |
| module.exports = 모듈 | 모듈을 내보내는 방법 내보내는 모듈은 변수가 될 수 있고 객체가 될 수 있다. |
| exports.이름 = 모듈 설 | 특정 이름으로 모듈을 내보내는 방법입니다. {모듈1, 모듈2} 등 디스트럭쳐링을 통해 해당 모듈을 불러올 수 있습니다.  |

여러 파일에 걸쳐 재사용되는 함수나 변수들을 모듈로 만들어두면 편리합니다. 그러나 모듈이 많아지고, 모듈 간의 관계가 얽히게 되면 구조를 파악하기 어렵다는 단점도 있습니다. 

노드의 대부분의 파일은 다른 파일을 모듈로 사용하고 있으므로 모듈을 만들고 사용하는 방법을 꼭 알아두어야 합니다. 
