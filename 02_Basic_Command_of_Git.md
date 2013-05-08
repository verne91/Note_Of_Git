#Git基本命令#
##Git初始化##
查看Git的版本信息：  

    git --version

对于Git的首次使用，需要设置Git的全局信息，这些信息主要涉及版本提交时的提交信息，Git所使用的默认编辑器等。

配置自己的用户名和邮件地址：

    git config --global user.name "Yourname"
    git config --global user.email "Youremail@email.com"
在Git命令输出中开启颜色显示：  

    git config --global color.ui true

使用Git创建一个版本库，只需要在Git Bash中进入到版本库所在的目录然后执行命令：

    git init

右或者对于1.6.5或更新的Git版本，可以直接在`git init`后加上目录名，自动完成目录的创建。

初始化了版本库后，该目录就成了工作区，而且会在该目录下创建一个隐藏的文件夹`.git`文件夹，该文件夹就是Git的版本库了。

初始化完成后，即可往版本库中添加文件了。假如添加了一个文件README.md,可以使用命令

    git add README.md

将该文件添加进版本库，但是光执行该命令是不够的，因为该命令只是将更改提交到缓存区，还需要执行一次提交操作才能将文件真正添加进版本库：

    git commit -m "comment"

`-m`后的`"comment"`为提交说明，对于Git来说是不能省略，强制要求的。

显示版本库.git目录所在的位置：

    git rev-parse --git-dir

显示工作区的根目录：
    
    git rev-parse --show-toplevel

有时，在忘了对Git进行初始化设置用户名和email等信息时，Git会自动生成一个猜测的信息，这些可能是错误的，但是因为已经提交了，所以需要对提交的信息进行修改，在用`git config --global`进行配置完之后，可以使用:

    git commit --amend --allow-empty --reset-author

进行修改，`--amend`是表示对刚刚的提交进行修改而不产生另外新的提交，`--allow-empty`表示允许空白提交，这是因为要进行修补的提交是一个空白提交（默认情况下Git是不允许在用户信息空白的情况下提交的，为了说明更改提交信息，使用`--allow-empty`就可以提交空白的信息）。`--reset-autor`将Author的Id同步修改，否则只印象提交者的Id,使用该参数也会重置AuthorDate的信息。

