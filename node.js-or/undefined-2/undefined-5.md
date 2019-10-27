# 노드 사용자 입력값 받기

## 사용자 입력값 받기

 Node.js에서도 C언어의 scanf와 같이 표준 입출력을 관리해주는 **readline 패키지**가 존재합니다.

```javascript
const readline = require("readline");
const  rl = readline.createInterface({
    input : process.stdin,
    output: process.stdout
});

rl.on("line", (line) => {
    console.log("hello!",line);
    rl.close();
}).on("close", ()=>{
    process.exit();
});
```

위의 코드는 사용자로 부터 한 줄의 입력만 받고 프로그램이 끝나게 됩니다. 만약 rl.close\(\)함수가 없다면 무한으로 입력을 받으며 받은 만큼 실시간으로 console.log를 찍습니다.



### 공백 문자로 두 값 구분하기

 만약 두 값을 공백으로 구분지어 입력 받은 후 처리를 해주기 위해 다음과 같이 readline을 사용할 수 있습니다.

```javascript
const readline = require("readline");
const  rl = readline.createInterface({
    input : process.stdin,
    output: process.stdout
});

let input = [];

rl.on("line", (line) => {
    input = line.split(' ').map(el=>el);
}).on("close", () =>{
    console.log(input[0] + input[1]);
    process.exit();
});
```

### 콘솔의 Interactive Shell

콘솔에서는 Interactive Shell이 계속 열려 있어 자동으로 close가 호출되지 않습니다. 일반적으로 콘솔에서는 계속해서 입력 이벤트를 기다리기 때문에 close가 실행되지 않습니다. 



