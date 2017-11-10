---
title: 前端测试框架-mocha
date: 2017-08-23 21:19:57
tags:
    - nodejs
    - 测试
    - macha
categories:
    - 技术
    - 前端
    - 前端测试
---
## mocha 前端测试框架

### 安装mocha
首先需要一个nodejs环境,比如说新建一个工程mocha-test
```bash
mkdir mocha-test
cd mocha-test
npm init
npm install -s mocha
```
为了方便可以全局安装
```bash
npm install -g mocha
```
### 编写单元测试用例
```javascript
//add.js
function add(a,b){
    return a+b;
}
module.exports=add;
```
测试用例
```javascript
var add = require('./add');
var expect = require('chai').expect;
describe('加法函数测试',function  ( ) {
     it('1+1=2',function(){
        expect(add(1,1)).to.be.equal(2);
     });
      it('2+1=3',function(){
        expect(add(2,1)).to.be.equal(3);
     });
});
```
其中``` require('chai').expect```为第三方的一个断言库。describe为开始一个测试套件,it为一个测试用例。
具体断言库的使用还需要参考具具体的API

