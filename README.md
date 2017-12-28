# shadowsocksqt5-
shadowsocksq5的安装与设置全局代理


 本文基于Ubuntu 16.04，使用Shadowsocks-Qt5和GenPAC，达到全局代理的效果。
基本软件：

Ubuntu 16.04

Shadowsocks-Qt5

GenPAC

pip

 一、准备
Shadowsocks-Qt5

sudo add-apt-repository ppa:hzwhuang/ss-qt5

sudo apt-get update

sudo apt-get install shadowsocks-qt5

下载完成后在终端打开shadowsocks-qt进行配置

 pip：

sudo apt-get install python-pip python-dev build-essential 

sudo pip install --upgrade pip 

sudo pip install --upgrade virtualenv 

GenPAC：

sudo pip install genpac

sudo pip install --upgrade genpac






 二、开搞
必须准备工作完成以后才能开始下面的事情。
(1) 进入终端，Ctrl+Alt+T，cd到你希望生成文件存放的位置
例如：
cd /home/leo/Software





(2) 执行下面的语句
sudo genpac --proxy="SOCKS5 127.0.0.1:1080" --gfwlist-proxy="SOCKS5 127.0.0.1:1080" -o autoproxy.pac --gfwlist-url="https://raw.githubusercontent.com/gfwlist/gfwlist/master/gfwlist.txt"




注意：
上面语句中127.0.0.1:1080应按照自己的情况填写。
如果出现下面这种报错：
fetch gfwlist fail. online: https://raw.githubusercontent.com/gfwlist/gfwlist/master/gfwlist.txt local: None
那么换成执行下面的语句：
sudo genpac --proxy="SOCKS5 127.0.0.1:1080" -o autoproxy.pac --gfwlist-url="https://raw.githubusercontent.com/gfwlist/gfwlist/master/gfwlist.txt"




(3) 全局代理

systemsetting –> network –> network proxy

“Method”选择“Automatic”

“配置URL”填写
file:///home/leo/Software/autoproxy.pac        (在配置URL这栏不要加上双引号！ )

       注： /home/leo/Software/autoproxy.pac （这是刚才你下载的autoproxy.pac的文件路径）

最后点击“应用到整个系统”
