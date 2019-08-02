# Express Middleware \| 미들웨어

## Express 미들웨어

 소프트웨어를 만들 때 처음부터 끝까지 다 만드는 경우는 거의 없습니다. 다른 사람이 만든 소프트웨어를 부품으로 사용해서 생산성을 높여야합니다.

Express는 서버의 역할을 하면서 새로운 기능을 추가할 때나, 

| 구분  | 설명  |
| :--- | :--- |
| Built-In Middleware |  Express에 내장되어 있는 API 미들웨어 |
| Third-Party Middleware | Express외에 다른 사람들이 만들어 놓은 API 미들웨 |

{% hint style="info" %}
**미들웨어 정의**

분산 컴퓨팅 환경에서 서로 다른 기종의 하드웨어나 프로토콜, 통신환경 등을 연결하여, 응용프로그램과 그 프로그램이 운영되는 환경 간에 원만한 통신이 이루어질 수 있게 하는 소프트웨
{% endhint %}

### Express 미들웨어 실행 순서

 Express에는 다양한 종류의 미들웨어가 있습니다. 이들 미들웨어의 순서를 반드시 알아둬야 할 필요는 없지만, 이를 고려하지 않아 에러가 발생할 수 있습니다.

1. Application-Level Middleware
2. Router-Level Middleware
3. Error-handling Middleware
4. Built-In Middleware
5. Third-party Middleware

미들웨어를 잘 설계하면 애플리케이션이 실행되는 흐름을 잘 조절할 수 있습니다. 

