# 本地开发过程中课直接与服务器进行文件同步

版本： v1.0.0

## 使用方法：

先安装node、npm等工具~

先填写好config.json 文件，然后在目录下执行 node main.js

目前没有测试过Windows


### config.js 参数简介

{
    "receiver": "http://jiaowu/",
    "base": "/Users/fanmingfei/ldsnwork/server/",
    "to": "/data/www/jiaowu/server",
    "unwatchSuffix": [".swp"],
    "unwatchPath": [".git","Runtime"]
}


* receiver 接收文件的url

本插件是通过post请求发送文件，所以服务端需要一个文件进行接收，文件是从FEX的FIS库中直接拿过来的，

链接：<https://github.com/fex-team/fis3-command-release/blob/master/tools/receiver.php>

直接放在服务器可以访问到的地方，把访问URL放在receiver

* base 本机项目目录

* to 测试机项目目录

* unwatchSuffix 不进行监控的文件后缀名， 比如说一些没有用的 可能会出现的 .psd、.zip 之类的都不需要监控，注意这里是带"."的。

* unwatchPath 不进行监控的目录，有些目录不需要进行监控，因为每次开启监控都要重新吧所有文件上传一次，像一些无需第一次更新的目录卸载上面，就不会在执行代码的时候把它上传上了，但是开始监控以后会实时监控这些目录。


