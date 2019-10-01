# 노드 파일 시스템 처리

## 노드 파일 시스템 처리 File System

### 기본적인 파일 읽기/쓰기

#### 파일 읽기 

 노드는 fs모듈을 이용해 파일 시스템에 접근할 수 있습니다. 즉, 파일을 생성하거나 삭제하고, 읽거나 쓸 수 있습니다. 

```javascript
const fs = require("fs");

fs.readFile("./readme.txt", (error, data) => {
    if(error){
        throw error;
    }
    console.log(data);
    console.log(data.toString());
}
```

 readFile은 데이터를 버퍼 형식으로 제공하기에 반드시 toString\(\)을 해주어야 원하는 결과를 얻을 수 있습니다. 

#### 파일 쓰기 

```javascript
const fs = require("fs");

fs.writeFile("./writeme.txt","글이 입력됩니다.', (error) => {
    if(error){
        throw error;
    }
    fs.readFile("./writeme.text", (error, data) =>{
        if(error){
            throw error;
        }
        console.log(data.toString());
    });
});
```

### 동기 메서드와 비동기 메서드 

![&#xB3D9;&#xAE30;&#xC640; &#xBE44;&#xB3D9;&#xAE30; &#xBC29;&#xC2DD;](../../.gitbook/assets/kakaotalk_photo_2019-10-01-14-41-28.jpeg)

 동기 - 블로킹 방식과 비동기 - 논블로킹 방식을 이해하는 것이 노드를 이해하는데 중요한 역할을 합니다. 

| 구분  | 설명  |
| :--- | :--- |
| **fs.readFileSync\(\)** | 파일을 읽는 동기 - 블로킹 방식으로 진행하는 메소드  |
| **fs.writeFileSync\(\)** | 파일을 쓰는 동기 - 블로킹 방식으로 진행하는 메소드   |

Sync\(동기\) 메소드를 사용할 경우 요청이 수백 개 이상 들어왔을 때 성능에 문제가 생깁니다.

 백그라운드각 작업을 하는 동안 메인 스레드는 아무것도 못하고 대기 해야 하기에 메인 스레드가 일을 하지 않고 노는 시간이 생기기 때문에 비효율적입니다.

### 버퍼와 스트림 Buffer and Stream

 파일을 일거나 쓰는 방식에는 **버퍼를 이용하는 방식**과 **스트림을 이용하는 방식** 크게 두 가지가 있습니다. 

| 구분  | 설명  |
| :--- | :--- |
| **버퍼링 Buffering**  | 영상을 재생할 수 있을 때까지 데이터를 모으는 동작 |
| **스트리밍 Streaming** | 영상 데이터를 조금씩 전송하는 방식의 동작  |

**노드는 파일을 읽을 때 메모리에 파일 크기 만큼 공간을 마련해두며, 파일 데이터를 메모리에 저장한 뒤 사용자가 조작할 수 있도록 해줍니다.** 메모리에 저장된 데이터가 바로 버퍼입니다. 

#### Buffer 클래스

####   

