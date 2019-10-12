# 클러스터 \| Cluster

## 클러스터 \| Cluster 

 노드는 싱글 스레드를 사용합니다. 하지만 **cluster 모듈을 통해 싱글 스레드인 노드가 CPU코어를 모두 사용**할 수 있게 해줍니다. 

 포트를 공유하는 노드 프로세스를 여러 개 둘 수도 있어 요청이 많이 들어왔을 때 병렬로 실행된 서버의 개수만큼 요청이 분산되게 할 수 있습니다. 

 이렇게 될 경우 **서버에 무리가 덜 가게되는 장점**을 가지지만 **세션을 공유하지 못한다는 단점** 등이 발생해 **Redis 등의 서버를 도입하여 해결**해야 합니다. 

```javascript
const cluster = require("cluster");
const http = require("http");
const numCPUs = require("os").cpus().length;

if(cluster.isMaster){
    console.log(`마스터 프로세스 아이디: ${process.pid}`);
    
    // CPU 개수만큼 워커 생산
    for(let i = 0 ; i < numCPUs; i += 1){
        cluster.fork();
    }
    
    // 워커가 종료되면
    cluster.on("exit", (worker, code, signal) => {
        console.log(`${worker.process.pid}번 워커가 종료되었습니다.`);
    });
} else {
    
    // 워커들이 포트에서 대기
    http.createServer((req,res)=>{
        res.write("");
        res.end("");
    }).listen(8085);
    
    console.log(`${process.pid}번 워커 실행`);
}

```

클러스터에는 **마스터 프로세스**와 **워커 프로세스**가 있다. 

마스터 프로세스는 CPU 개수만큼 워커 프로세스를 만들고, 8085번 포트에서 대기합니다. 요청이 들어오면 만들어진 워커 프로세스에 요청을 분배합니다. 

 워커 프로세스는 실질적인 일을 하는 프로세스입니다. 

### 워커 프로세스 종료 시 새로 하나 생성하는 방법

```javascript
cluster.on("exit", (worker, code, signal) => {
    console.log(`${worker.process.pid}번 워커가 종료되었습니다.`);
    cluster.fork();
});
```

 직접 cluster 모듈로 클러스터링을 구현할 수도 있지만, 실무에서는 **pm2 등의 모듈로 cluster 기능을 사용하곤 합니다**. 

