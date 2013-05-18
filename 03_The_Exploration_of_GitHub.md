#GitHub点滴#

##GitHub认证##
GitHub是使用Git作为唯一工具的远程版本控制服务平台。因为Git是没有账号密码的，它是一个分布式的版本控制系统，所以在从本地推送更新至GitHub时自然需要一个认证进行支持，以控制代码的提交。首先GitHub有一个公钥管理功能，利用SSH公钥私钥生成工具生成每台电脑的公钥私钥，把公钥添加进GitHub账号的SSH公钥中，这样用这台电脑推送更新时才能够真正推送成功。

在Windows中的msysgit已经有了SSH公钥私钥生成功能，如果没有此功能的Git或者其他系统，就需要自己用SSH公钥私钥软件生成。msysgit生成公私钥对：

    ssh-keygen -C "YourEmailAccount@something.com" -t rsa

如下图

![如图][1]

生成了公钥私钥之后在提示的文件夹下找到id_rsa.pub（如果生成的时候没有指定其他的名字应该就是这个名字了），将其密钥复制进GitHub中账号面板下的SSH public key中，如下图所示

![GitHub公钥设置][2]

如图，你还可以为该公钥设置一个名字，方便管理。一个GitHub可以对应多个公钥，也即可以添加不同的计算机对该账号下的项目进行写权限。但是这种设置只是为了方便你在公司和家里多地的电脑可以对该账号进行操作，一般来说对团队中项目开发不应该把不同的开发人员的公钥添加进同一个账号下。对团队中多人对同个项目的开发有其他的管理方式。

在某些时候，一个GitHub账号中有多个项目，但可能有需求对某台电脑只能对某个特定项目有权限，这是可以将其生成的公钥添加进该项目的deploy key中，这样就只能对该项目有权限：

![project deploy key][3]

[1]:./images/SSH_generation.jpg "公钥私钥生成"
[2]:./images/GitHub_SSH_Key_Setting.jpg "GitHub SSH公钥设置"
[3]:./images/GitHub_Add_Project_key.jpg "GitHub Add project deploy key"

