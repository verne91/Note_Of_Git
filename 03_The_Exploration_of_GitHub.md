#GitHub点滴#

##GitHub认证##
GitHub是使用Git作为唯一工具的远程版本控制服务平台。因为Git是没有账号密码的，它是一个分布式的版本控制系统，所以在从本地推送更新至GitHub时自然需要一个认证进行支持，以控制代码的提交。首先GitHub有一个公钥管理功能，利用SSH公钥私钥生成工具生成每台电脑的公钥私钥，把公钥添加进GitHub账号的SSH公钥中，这样用这台电脑推送更新时才能够真正推送成功。

在Windows中的msysgit已经有了SSH公钥私钥生成功能，如果没有此功能的Git或者其他系统，就需要自己用SSH公钥私钥软件生成。msysgit生成公私钥对：

    ssh-keygen -C "YourEmailAccount@something.com" -t rsa

![如图][1]
[1]:./image/SSH_generation.jpg "公钥私钥生成"

