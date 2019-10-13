# static

## static

 static 미들웨어는 정적 파일들을 제공합니다. 익스프레스에 내장되어 있는 미들웨어이기에 따로 설치할 필요없이 다음과 같이 사용할 수 있습니다.

```javascript
...
app.use(express.static(path.join(__dirname,'public')));
...
```

위와 같이 static안의 인자로 정적 파일이 담겨 있는 폴더를 지정하면 해당  폴더에 접근할 수 있습니다. 

 위와  같이 사용할  경우 실제 서버의 폴더 경로에는 public이 들어 있지 않아 서버의 폴더 경로와 요청 경로가 달라지게 됩니다. 이는 외부인이 **서버의 구조를  쉽게 파악할 수 없게해 보안에 큰 도움**이 됩니다. 

 또한 다음과 같이 정적 파일을 제공할 주소를 지정할 수 있습니다. 

```javascript
app.use('/img', express.tatic(path.join(__dirname,'public')));
```

위는 http://localhost:3000/img라는 경로를 가지게 됩니다. 

