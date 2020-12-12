# webpack-dev-middleware-for-koa
webpack dev middleware for koa 2.x.

## Usage

```javascript
const app = require('koa')();
const webpackMiddleware = require("webpack-dev-middleware-for-koa2");
app.use(webpackMiddleware(...));
```

### Example usage
```javascript
const app = require('koa')();
app.use(webpackMiddleware(webpack({
    // webpack options
    // webpackMiddleware takes a Compiler object as first parameter
    // which is returned by webpack(...) without callback.
    entry: "...",
    output: {
        path: "/"
        // no real path is required, just pass "/"
        // but it will work with other paths too.
    }
}), {
    // all options optional
      publicPath: webpackDevConfig.output.publicPath, // 增加路由访问前缀
      logLevel: "error",
}));
```