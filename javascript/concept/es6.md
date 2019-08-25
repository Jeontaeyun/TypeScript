# 자바스크립트의 모듈시스템\(ES6\)

## 자바스크립트의 모듈 시스템

  ES6 이전의 자바스크립트는 리소스 관리가 어렵다는 단점이 있었습니다.  웹에서는 해당 페이지에 필요한 모든 파일을 미리 불러와야 하고, 그 파일들이 사용하는 변수가 겹치지 않게 잘 살펴 봐야했습니다.

 이 때문에 자바스크립트의 라이브러리들은 $, React 등의 네임스페이스를 사용해야 했습니다. 또한, 스크립트를 로딩하는 순서도 중요합니다.

 해당 스크립트가 실행 되기 전에 필요한 자바스크립트 파일이 먼저 로딩되지 않으면 특정 키워드가 정의 되지않았다는 에러가 발생합니다. 

{% hint style="info" %}
**Node.js와 ES6의 모듈 시스템**

Node.js에서는 ES2015의 모듈 시스템을 지원하지 않습니다.  단 Node.js 버전9 부터는 모듈 시스템을 지원하지만 확장자를 mjs로 지정한 후, 실행시 node --experimental -modules \[파일명\] 처럼 귀찮은 방식을 사용해야 합니다.  
  
Node.js에서 원래 사용하는 **require**과 **module.exports,** **exports.변수명**의 방식을 사용하는 것이 낫습니다.
{% endhint %}

### import ... from ... 으로 불러오

 **위와 같은 문제를 해결하고 의존성을 관리하기 위해** 사람들은 commonJS와 requireJS같은 자체적인 모듈 라이브러리를 만들었습니다. 자바스크립트의 최신 버전인 ES6에서는 이런 기능을 지원해주게 되었습니다.

 ES6의 모듈 시스템파일의 맨 첫 부분에 **import 패키지 from '패키지파일'** 을 통해 해당 파일이 어떤 패키지를 필요로 한다고 선언하는 방식입니다. 

물론 **선언한 패키지는 해당 파일 안에서만 유효합니다.** 

```javascript
import React from 'react;
import {render} from 'react-dom'
import * as newName from './newName'
//위와 같이 as키워드를 통해 모듈의 이름을 재설정 할 수 있습니다.
import * from './all'
// export한 모든 것을 모아서 import 해주는 방식입니다. default도 객체의 멤버로 들어갑니다.
```

### export default ... 으로 내보내기 

 모듈을 불러오기 위해서는 모듈을 내보내야 합니다. ES6의 모듈 시스템에서는 다음과 같은 방식으로 모듈을 내보냅니다.

```javascript
const taeyun = "taeyun"
const stark = "stark"
export {a} ;                                // 객체형태로 내보냅니다.
export const job = "developer" ;            // 선언과 동시에 내보냅니다.
export default stark;                       // 불러올 때 괄호를 사용하지 않고 이름 도 바꿀 수 있게 내보냅니
```

 ES2015의 모듈 시스템은 기본적으로 strict 모드\(use strict\)로 동작합니다. 

모듈 시스템을 브라우저에서 지원하기 위해서는 BabelJS같은 컴파일러를 사용해서 ES5 스타일로 바꿔줘야 합니다. \(크롬 60버전 부터 브라우저에서 도 모듈을 사용할 수 있

{% hint style="info" %}
**strict 모드**  


strict 모드는 ES5에 추가된 키워드로 자바스크립트가 묵인 했던 에러들의 에러 메세지를 발생시킵니다. strict 모드를 사용하면 보안에 강한 자바스크립를 작성할 수 있습니다. 

함수나 스크립트 안에 "use strict"를 넣어주면 use strict 모드로 변경됩니다. 
{% endhint %}

