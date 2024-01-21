#### 这是一个本地部署webtim项目的文件夹，若您下载了该文件夹进行本地测试运行，请不吝再给[tim项目](https://github.com/donnie4w/tim "tim项目")与[tldb项目](https://github.com/donnie4w/tldb "tldb项目")点上一星⭐，作者在此先行感谢您为开源项目注入动力❤️

- tim：https://github.com/donnie4w/tim
- tldb: https://github.com/donnie4w/tldb

##### 以下是说明：

webtim运行依赖tldb数据库与tim即时通讯服务器。webtim启动前，应该确保先启动了tldb数据库，再启动tim服务器，最后启动webtim服务。

在本文件夹中，已经按linux，windows，macos系统分别放置了相应操作系统的执行文件，并在外层文件中放置了start脚本，可以执行start脚本，一键启动即可，启动时，脚本会先启动tldb数据库，并等待12秒，原因是tldb需要初始化，后启动tim服务器与webtim后台服务。

##### 脚本与配置数据说明

1. 脚本指定 tldb的客户端监听端口为 5837，该参数在执行脚本中设定
2. tim文件夹中，tim.json为tim服务配置文件，其中指定了数据库本地地址，用户密码，与tim监听端口和后台地址
3. webtim文件夹中，webtim.json 指定了数据库地址，tim后台地址。在webtim.json中设置了webtim的浏览器访问端口为6060

##### 成功启动所有服务后

1. 访问本地webtim服务器：http://localhost:6060 即可。与访问https://tim.tlnet.top 是一样的界面，说明本地部署成功。

2. tim后台可以查看资源与用户连接的数据：地址为http://localhost:8001 用户名密码为 admin 123 

3. tldb管理后台地址 http://localhost:4001 用户名密码  admin 123 登录可以查看tim与webtim各自建立的表与生成的数据。以tim开头的表为tim服务器建立的表，以webtim开头的表则为webtim项目建立的表。webtim建立的表与通讯没有直接关系，只供webtim页面的部分数据查询使用。

注意：执行脚本前，应当确认脚本与tldb,tim,webtim等执行文件 有执行权限。若是其他操作系统，请自行在https://tlnet.top/download 中下载系统相应的tldb，tim执行文件，或由源码自行编译打包。


- 在linux或macos上 ，本地部署webtim时，启动可能出现一些错误，如
![](https://tlnet.top/f/1705822912_9928.jpg)

##### 数据库生成binlog文件的权限问题：可以有两种方法可以解决
1. 一是文件增加权限，如：chmod -R 777 tldb/_data/bin  ；再重新运行 ./start.sh
2. sudo运行，如 sudo ./start.sh

![](https://tlnet.top/f/1705823155_20244.jpg)

##### 成功启动的全过程：

![](https://tlnet.top/f/1705823184_4192.jpg)

最后出现 webtim start [:6060] 说明本地成功启动webtim

------------

有问题可以email作者：donnie4w@gmail.com 或微信 donnie4w
也可在webtim技术说明中 找到 tim微信群