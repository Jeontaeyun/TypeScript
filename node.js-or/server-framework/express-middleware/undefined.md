# 커스텀 미들웨어

## 커스텀 미들웨어 Custom Middleware

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

미들웨어에는 반드시 next\(\)를 넣어주어야 합니다. 

