# Window 와 BOM 객체

## Window

 자바스크립트는 브라우저를 처음 브라우저를 조작하기 위해 고안된 언어이기 때문에 자바스크립트에서 window 객체는 브라우저 전체를 조작하는 객체이다.

  window 에 관련된 객체는 크게 BOM 객체와 DOM 객체가 있으며 window 자체를 객체로 사용하는 몇 개의 메소드가 있다. window의 대표적인 메소드는 다음과 같다.

| 구분 | 설명 |
| :--- | :--- |
| window.close\(\) | 현재 창을 닫습니다.  |
| window.open\(주소, 새 창 여부 ,설정값\) | 새 창을 엽니다. 팝업 창의 형태로 열 수 있고, 새 탭으로 열수도 있습니다. |
| window.encodeURI\(\) | 주소에 한글이 들어가면 한글이 이상한 글자로 변환하는데, 한글을 해당 문자열로 변환하고 싶을 때 encodeURI\(\)를 사용합니다. |
| window.decodeURI\(\) | encodeURI\(\)를 통해 변경된 문자를 한글로 바꾸고 싶을 대는 decodeURI\(\)를 사용합니다. |
| window.setTimeout\(함수, 시간\) | 지정해 둔 시간\(밀리초, ms\) 뒤에 지정해 둔 함수가 실행되는 메소드 입니다.  |
| window.setInterval\(함수, 시간\) | 지정해 둔 시간\(밀리초, ms\)마다 지정해 둔 함수를 반복하는 메소드 입니다. |
| window.clearTimeout\(setTimeout\) | setTimeout으로 실행되는 코드를 사용 중지 하는 메소드 입니다. |
| window.clearInterval\(setInterval\) | setInterval으로 실행되는 코드를 사용 중지 하는 메소드 입니다. |
| window.alert\(문구\) | 해당 문구를 가지는 경고창을 띄웁니다. |
| window.confirm\(문구\) | 해당 문구를 가지는 확인/취소 창을 띄웁니다. |
| window.prompt\(문구\) | 해당 문구를 가지는 질의 응답 창을 띄웁니다. |
| window.moveTo\(x위치, y위치\) | 창의 위치를 이동 시킬 때 사용합니다. |
| window.resizeTo\(너비값,높이값\) | 창의 크기를 변경시킬 때 사용합니다. |

 window 객체는 모든 객체를 포함하는 조상객체입니다. 즉, 전역 객체입니다. 따라서 window 객체를 참조할 때는 window라는 키워드를 생략할 수 있습니다. 실제로 우리가 객체를 만들면 window 변수를 만들면 window객체 포함됩니다.

## BOM \| 브라우저 객체 모델 

 브라우저에 계층적으로 내장되어 있는 객체인 BOM 객체는 브라우저에 대한 정보를 추출하고 조작할 수 있는 객체입니다. 크게 **navigator**, **screen**, **location**, **history**, **dom** 객체가 있습니다. 특히 브라우저는 큰 틀에서 Document 부분을 하나의 파트로 구분하기 때문에 브라우저의 설정을 조작하기 위해서 나머지 4개의 객체를 알아두는 것이 좋습니다.

### navigator 객체

 현재 방문자의 브라우저나 운영체제\(OS\)에 대한 정보를 담고 있는 객체입니다.

| 속성 | 설명 |
| :--- | :--- |
| navigator.appCodeName | 방문자의 브라우저의 코드명을 반환합니다. |
| navigator.appName | 방문자의 브라우저 이름을 반환합니다. |
| navigator.appVersion | 방문자의 브라우저 버전 정보를 반환합니다. |
| navigator.language | 방문자의 브라우저 사용 언어를 반환합니다. |
| navigator.product | 방문자의 브라우저 사용 엔진 이름을 반환합니다. |
| navigator.platform | 방문자의 브라우저를 실행하는 운영체제를 반환합니다. |
| navigator.userAgent | 방문자의 브라우저와 운영체제 종합 정보를 반환합니다. |
| navigator.cookieEnabled | 방문자의 브라우저에서 쿠기 사용이 가능한지에 대한 여부를 반환합니다. |

### Screen 객체 

현재 방문자의 브라우저의 화면에 대한 정보를 담고 있는 객체입니다.

| 속성 | 설명  |
| :--- | :--- |
| screen.width | 화면의 너빗값을 반환합니다. |
| screen.height | 화면의 높잇값을 반환합니다. |
| screen.availWidth | 작업 표시줄을 제외한 화면의 너비값을 반환합니다. |
| screen.availHeight | 작업 표시줄을 제외한 화면의 높잇값을 반환합니다. |
| screen.colorDepth | 사용자 모니터가 표현 가능한 컬러 bit을 반환합니다. |

### Location 객체 

현재 방문자의 브라우저의 주소에 대한 정보를 반환합니. 새로고침을 해주거나, 현재 주소를 바꿔주는 역할을 합니다.

| 속성 혹은 메소드 | 설명 |
| :--- | :--- |
| location.href | 주소 영역에 참조 주소를 설정하거나 URL을 반환합니다. |
| location.hash | 현재 URL에 해시값\(\#에 명시된 값\)을 반환합니다. |
| location.hostname | 현재 URL에 호스트 이름\(도메인\)을 설정하거나 반환합니다. |
| location.host | 현재 URL에 호스트 이름과 포트 번호를 반환합니다. |
| location.port | 현재 URL에 포트를 반환합니다. |
| location.protocol | 현재 URL에 프로토콜을 반환합니다. |
| location.search | 현재 URL에 쿼리 값을 반환합니다. |
| location.pathname | 현재 URL의 경로를 반환합니다. |
| location.reload\(\) | 새로고침을 발생하는 메소드입니다. |
| location.replace\(주소\) | 현재 URL을 다른 주소로 교체합니다. 이때 이전 페이지의 기록이 발생하지 않습니다. |

{% hint style="info" %}
**리다이렉션 \| Redirection**

컴퓨팅에서 출력의 방향을 바꾸는 것을 말한다. 예를 들어 일반 컴퓨터의 표준 출력 장치가 모니터이지만 특정 명령을 통해 표준 출력을 프린터, 터미널 등 다양한 곳으로 출력을 바꿀 수 있습니다.

또한, 표준 입력을 표준 출력으로, 표준 출력을 표준에러로 자유 자재로 바꿀 수 있다.
{% endhint %}

{% hint style="info" %}
**웹 프로그래밍에서 리다이렉션** 

웹 프로그래밍에서 리다이렉션은 원래 접속한 URL 주소를 새로운 다른 주소로 자동으로 연결해주는 기능입니다. 
{% endhint %}

### History 객체 

현재 방문자의 브라우저의 기록을 바탕으로 페이지 이동을 제어할 수 있는 속성과 메소드를 제공합니다.

| 속성 혹은 메소 | 설명  |
| :--- | :--- |
| history.back\(\) | 방문자가 바로 직전에 방문한 페이지로 이동합니다. |
| history.forward\(\) | 방문자가 바로 다음에 방문한 페이지로 이동합니다. |
| history.go\(이동 숫자\) | 방문자가 N단계 이전 혹은 이후에 방문한 페이지로 이동합니다. 이전 페이지로 가고 싶을 때는 -\(음수\)를 사용합니다. |
| history.pushState\(객체, 제목, 주소\) | HTML5부터 추가되어 페이지를 이동하지 않고 단순히 주소만 바꿔주 |
| history.replaceState\(객체, 제목, 주소\) | HTML5부터 추가되 |
| history.length | 방문 기록에 저장된 목록의 개수를 반환합니다. |



