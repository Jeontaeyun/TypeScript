# Express Middleware \| 미들웨어

## Express 미들웨어

 소프트웨어를 만들 때 처음부터 끝까지 다 만드는 경우는 거의 없습니다. 다른 사람이 만든 소프트웨어를 부품으로 사용해서 생산성을 높여야합니다.

Express는 서버의 역할을 하면서 새로운 기능을 추가할 때 미들웨어를 사용하며 **요청과 응답의 중간\(midddle\)에 위치하여 미들웨어**라 부릅니다.

| 구분  | 설명  |
| :--- | :--- |
| Built-In Middleware | Express 에 내장되어 있는 API 미들웨어 |
| Third-Party Middleware | Express 외에 다른 사람들이 만든 API 미들웨 |

{% hint style="info" %}
**미들웨어 정의**

 분산 컴퓨팅 환경에서 서로 다른 기종의 하드웨어나 프로토콜, 통신환경 등을 연결하여, 응용프로그램과 그 프로그램이 운영되는 환경 간에 원만한 통신이 이루어질 수 있게 하는 소프트웨어
{% endhint %}

### Express 미들웨어 실행 순서

 Express에는 다양한 종류의 미들웨어가 있습니다. 이들 미들웨어의 순서를 반드시 알아둬야 할 필요는 없지만, 이를 고려하지 않아 에러가 발생할 수 있습니다.

1. Application-Level Middleware
2. Router-Level Middleware
3. Error-handling Middleware
4. Built-In Middleware
5. Third-party Middleware

미들웨어를 잘 설계하면 애플리케이션이 실행되는 흐름을 잘 조절할 수 있습니다. 

### app.use와 미들어 

 미들웨어는 주로 app.use와 함께 사용됩니다. 미드뤠어는 use메소드로 app에 장착합니다. 선언된 순서대로 미들웨어는 순차적으로 거친 후 라우터에서  클라이언트로  응답을 보냅니다.

```javascript
...
app.use(logger('dev'));
app.use(express.json());
app.use(epress.urlencoded({extended: false}));
app.use(cookieParser());
...
app.use('/'. indexRouter);
app.use('/users', usersRouter);

// 404처리 미들웨어
app.use((req,res, next) => {
    next(createError(404);
});

// 에러 처리 미들웨
app.use((err, req, res, next) => {
    res.locals.message = err.message;
    res.locals.error = req.app.get('env') === 'development' ? err : {} ;
    
    res.status(err.status || 500);
    res.render('error');
});
```

