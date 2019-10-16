# 커스텀 미들웨어

## 커스텀 미들웨어 Custom Middleware

### 커스텀 미들웨어 Custom Middleware

 커스텀 미들웨어는 다음과 같이 만들 수 있습니다.

```javascript
...
app.set("views", path.join(__dirname, "views"));
app.set("view engine", "pug");
...
app.use((req, res, next) => {
    console.log(req.url, "저도 미들웨어 입니다.");
    next();
});
app.use(logger("dev"));
...
```

미들웨어에는 반드시 **next\(\)**를 넣어주어야 합니다. next\(\)함수를 호출해줘야 다음 미들 웨어로 넘어갑니다. 우리가 사용하는 대부분의 서드-파티-미들웨어에는 **내부적으로 next\(\)를 호출**합니다. 

next\(\)는 **미들웨어의 흐름을 제어하는 핵심적인 함수**입니다.

next\(\)는 인자의 종류로 기능이 구분됩니다. 인자를 아무것도 넣지 않으면 단순하게 다음 미들웨어로 넘어가며, route외의값을 넣으면 다른 미들웨어나 라투어를 건너 뛰고 바로 에러 핸들러로 이동하며 넣어준 값을 에러로 간주합니다. route를 넣어주면 다음 라우터로 이동합니다.

| 구분 | 설명  |
| :--- | :--- |
| next\(\) | 다음 미들웨어로 이동 |
| next\("route"\) | 다음 라우터로 이동 |
| next\(error\) | 에러 핸들러로 이동  |

### 에러 핸들링 미들웨어 Error Handling Middleware

**에러 핸들링 미들웨어**는 다음과 같습니다. 

```javascript
app.use((err, req, res, next) => {
    res.locals.message = err.message;
    res.locals.error = req.app.get('env') === 'development'? err : {};
    
    res.status(err.status || 500);
    res.render('error');
});
```

에러 핸들링 미들웨어 다른 미들웨어와 다르게 함수의 매개변수가 네개 입니다. **next 함수에 넣어준 인자가 err 매개변수로 연결**됩니다.

### app.use의 응용법

 하나의 app.use에 여러 개의 미들웨어를 연결할 수 있습니다. 순서대로 실행됩니다. 

```javascript
app.use('/', (req, res, next) => { 
    console.log('첫 번째 미들웨어'); 
    next();
} , (req, res, next) => {
    console.log('두 번째 미들웨어');
    next();
} , (req, res, next) => {
    console.log('세 번째 미들웨어');
    next();
 }); 
```

