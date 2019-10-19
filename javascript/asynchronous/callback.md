# 콜백과 콜백지옥

## 자바스크립트 비동기 처리와 콜백 함수

 자바스크립트의 **비동기 처리**란 **특정 코드의 연산이 끝날 때 까지 코드의 실행을 멈추지 않고 다음 코드를 먼저 실행하는 자바스크립트의 특성**을 의미합니다. 

 주로 Ajax 통신이나, setTimeout 등 백그라운드에서 동작하는 API등이 비동기 처리를 하며 주로 비동기 처리 후 수행되어야 할 콜배 함수를 넣어주는 방식입니다. 

### 자바스크립트 비동기 처리가 필요한 이유

자바스크립트에서 비동기 처리가 필요한 이유는 화면에서 서버로 데이터를 요청했을 때 서버가 언제 그 요청에 대한 응답을 줄지도 모르는데 마냥 다른 코드를 실행 안하고 기다릴 순 없기 때문입니다. 

 만약 **자바스크립트가 비동기 처리가 아닐 경우엔 특정 동작에 시간이 오래 걸릴 경우 브라우저가 정지하는 현상이 발생할 것**입니다. 

### 자바스크립트 비동기 처리와 콜백

 만약 자바스크립트의 비동기 API가 다음과 같이 사용 되면 문제가 발생할 것입니다. 

```javascript
function getData(){
    let tableData;
    $.get('URL path' , function(response) {
        tableData = response;
    });
    return tableData;
}

console.log(getData()); // undefined
```

만약 위와 같이 처리하면 $.get\(...\)이 실행되는 동안 tableData가 반환 되며 비동기 HTTP 통신을 통한 데이터 호출에 문제가 발생합니다. 

이 부분을 해결하기 위해 다음과 같이 수정해 줍니다. 

```javascript
// 비동기로 처리하는 함수에 callback function을 넣어주는 구조로 작
function getData(callbackFunc){
    $.get('URL path', function(response){
        callbackFunc(response);
    }
}

getData((response)=>{
    console.log(response);
});
```

위와 같은 문제를 해결하기 위해 우리는 함수의 인자로 **콜백 함수\(Callback Function\)**를 넣어줍니다. 

### 콜백 지옥 Callback Hell

 콜백 지옥은 비동기 처리 로직을 위해 콜백 함수를 연속해서 사용할 때 발생하는 문제입니다. 콜백 지옥의 예시는 다음과 같습니다. 

```javascript
$.get('URL', (response) => {
    parseValue(response, (id) => {
        auth(id, (result) => {
          display(result, (text) => {
               console.log(text);   
          });  
        });
    });
});
```

 웹 서비스를 개발하다 보면 서버에서 데이터를 받아와 화면에 표시하기까지 인코딩, 사용자 인증 등을 처리해야 하는 경우가 있습니다. 만약 이 모든 과정을 비동기로 처리해야 한다고 하면 위와  같이  콜백 안에 콜백을 연속적으로 연결하는 구조를 작성해야합니다.

 이럴 경우 코드 구조상 **가독성도 떨어지고** **로직을 변경하기도 어렵습니다**. 이런 구조를 콜백 지옥이라고 합니다.

