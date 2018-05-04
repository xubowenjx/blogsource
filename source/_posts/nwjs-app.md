---
title: nwjs-app
date: 2017-11-13 11:19:45
tags:
    - nw.js  
    - nodejs
categories:
    - 技术
    - 前端
---
# node-webkit 创建桌面app

## 下载官方SDK
>下载地址 [node-webkit](https://nwjs.io/),然后解压到本地.修改文件夹名称为nwsdk.给nw配置环境变量：复制nwsdk的文件夹路径拼在环境变量path后面,注意前面加个分号，如e:\\path1\\path2\\nwsdk


## 创建工程app
在nwsdk下创建文件夹app,然后在app文件夹下创建*index.html*和
*package.json*. 
代码如下:
index.html
```html
<html>
    <head>
        <title>
            nwjs
        </title>
    </head>
    <body>
        <h1>hellow world</h1>
    </body>
</html>
```
package.json
```json
{
    "name": "app",
    "main": "index.html"
}
```
## 试运行
```
cd nwsdk
nw app
```
## 打包成可执行文件
*   将*app内*的所有文件选中压缩成*app.nw*文件,注意不是直接压缩app文件夹,而是进入app文件夹然后全选压缩.
* 复制出压缩好的*app.nw*文件到和*nw.exe*同级
* 生成可 执行文件
    ```bash
     copy /b nw.exe+app.nw app.exe
    ```
* 运行app.exe


