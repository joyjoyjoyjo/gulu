# gulu -- 一个UI框架
[![Build Status](https://travis-ci.org/joyjoyjoyjo/gulu.svg?branch=master)](https://travis-ci.org/joyjoyjoyjo/gulu)
## 介绍
这是我在学习Vue过程中做的一个UI框架。
## 开始使用
1. 安装 

    使用本框架前，请在CSS中开启border-box
    ```css
    *，*::before,*::after{box-sizing: border-box;}
    ```
    IE8及以上浏览器都支持此样式。
    
    你还需要设置默认颜色变量（后续会改为SCSS变量）
    ```css
    :root {
        --button-height: 32px;
        --font-size: 14px;
        --button-bg: white;
        --button-active-bg: #eee;
        --border-radius: 4px;
        --color: #333;
        --border-color: #999;
        --border-color-hover: #666;
            }
    ```
    IE15及以上浏览器都支持此样式。
    
2. 安装gulu
    ```javascript
    npm i --save gulu
    ```
3. 引入gulu
    ```javascript
    import {Button,ButtonGroup,Icon} from 'gulugulu-test-1'
    import 'gulugulu-test-1/dist/index.css'
    export  default {  
      name:'app',
      components: {
           'g-button':Button,
           'g-icon':Icon,
       }
    }
    ```
## 文档
## 提问
## 变更记录
## 联系方式
## 贡献代码
