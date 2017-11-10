---
title: axios-vue跨域
date: 2017-09-08 17:33:59
tags:
    - 前端
    - axios
categories:
    - 技术
    - 前端
---
#  axios webpack开发环境跨域
##  1.设置axios的baseUrl
```javascript
//这里的be4app和下面的代理中保持一致
const ajaxUrl = env === 'development' ?
  '/be4app' :
  env === 'production' ?
  'https://www.url.com' :
  'https://debug.url.com';

const ajax = axios.create({
  baseURL: ajaxUrl,
  timeout: 30000
  withCredentials:true
});

```
## 2.设置devServer代理
```javascript
//be4app 根据实际的后台项目名称来配置
 devServer: {
        proxy: {
         '/be4app': { 
                target: 'http://127.0.0.1:8080',
                changeOrigin: true
              },
              pathRewrite:{
                '^/be4app':''
              }
            }
          },
```
比如实际后端的url是：http://127.0.0.1:8080/be4app/data/list
那么使用axios时为：上面的ajax.post('/data/list',param).then(callback);
