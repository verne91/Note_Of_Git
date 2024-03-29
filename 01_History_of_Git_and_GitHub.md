#Git和GitHub历史
##Git历史##
[《Git权威指南》][1]对Git的历史有一个比较详细的叙述。Git其实就是一个分布式的版本控制系统。  

可以想象，其实在程序员开始的最初是不需要版本控制的，因为最初的程序很小，全靠程一个程序员独立开发，这在人类活动中相对来说是比较简单的，因为只需要靠个人的智力，不需要团队的参与。

随着计算机的不断发展，计算机程序越来越复杂，单个项目所包含的文件也越来越多，即便是对单个程序员所开发维护的项目而言，对项目文件的更改和版本维护也开始越来越吃力，而对于一些更大的需要团队协作开发的项目而言，项目的更改和版本的维护简直就是个灾难。这其实完全可以想象出来，不同文件添加，相同文件的修改，相同文件在不同程序员间的修改，不同版本的合并等等。

刚开始，版本的控制主要是使用一些简单的文件比较工具来实现，通过比较文件的不同，将不同的文件部分进行添加合并。后来开始出现像CVS和SVN那些集中式的版本控制系统。而关于集中式和分布式的版本控制系统的区别，在[GotGitHub][2]和[分布式版本控制系统入门][3]中有阐述。其实最大的区别是在于对源代码存储和访问的方式上，集中式的版本控制对源码的保护和改动都是基于服务器的，需要通过中心服务器的连接执行所有操作，由服务器监控，所有项目的成员只能对服务器中的一个版本库进行提交。而对于分布式的版本控制，每个程序员本地都可以有一个版本库，所作的修改都是在本地进行的，对改动进行任意的提交，只有进行推送之后才把改动发到服务器中。

传说Linux之父Linux是集中式版本管理系统的反对者，所以，在1991-2002年之间，开源社区有很多人向Linux提议使用CVS进行Linux内核开发的版本控制系统，但是他一直都没有使用，他宁愿用手工修补文件的方式维护代码。

2002年到2005年，Linux终于选择了一个商业的版本控制系统BitKeeper作为Linux内核代码管理工具，它是一个分布式的版本控制工具。但2005年，Andrew Tridgell想对BitKeeper进行反向工程，以便开发一个可以跟BitKeper交互的开源工具，这激怒了BitKeeper软件所有者BitMover公司，于是便收回了对Linux社区免费使用BitKeeper的授权。于是，在迫不得已间，Linux选择自己开发一个分布式的版本控制工具，于是便诞生了Git。而关于Git命名的由来，可以参考[Git FAQ][4]。

从2005年4月到6月，Git已经初具规模，开始维护Linux核心的源代码了。而Linux功成身退将Git交给Junio C Hamano维护。最初Git除了核心命令外，其他的都是脚本语言开发的，并且每个功能都作为一条独立的命令。后来，Git逐渐演变，成百个Git独立命名被封装在一个Git命令中。最后，慢慢发展成了现在的这个样子，并且从Linux平台延伸至Windows,mac等很多不同平台。

##GitHub##
GitHub是一个面向开源以及私有软件项目（私有项目托管需要付费）的托管平台，并且只支持Git作为唯一的版本库格式进行托管。因此，说白了，GitHub就是一个利用Git整合了一些面向项目开发的人员服务的版本控制服务器。

根据[GotGitHub][5]记录，GitHub是2008年4月10日正式发布的，相对于之前1999年的SouceForge和2005年的GoogleCode，GitHub后来居上，并且注册用户在2011年即已超过百万了，托管版本库数量超300万，还不乏知名的开源项目如：Ruby on Rails、Hibernate、phpBB、Jquery、Prototype等。

GitHub因为采用了一种不同的付费商业模式（私有项目付费托管方式），所以其整体看起来非常的干净舒服，不会跟SourceForge一样有很多的广告，而GoogleCode还没用过，不好下结论。


[1]:http://book.douban.com/subject/6526452/
[2]:http://www.worldhello.net/gotgithub/01-explore-github/010-what-is-github.html
[3]:http://www.ibm.com/developerworks/cn/aix/library/au-dist_ver_control/
[4]:https://git.wiki.kernel.org/index.php/GitFaq#Why_the_.27Git.27_name.3F
[5]:http://www.worldhello.net/gotgithub/01-explore-github/010-what-is-github.html