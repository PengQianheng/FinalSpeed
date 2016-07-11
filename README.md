**详细内容参考[官网教程](http://www.ip4a.com/t/515.html)**
# FinalSpeed服务端安装
## 安装
使用root用户登录，在当前目录依次键入以下命令：
* wget https://raw.githubusercontent.com/PengQianheng/FinalSpeed/master/install_fs.sh
* chmod +x install_fs.sh
* ./install_fs.sh 

## 卸载
* sh /fs/stop.sh ; rm -rf /fs

## 启动
* sh /fs/start.sh; tail -f /fs/server.log

## 停止
* sh /fs/stop.sh

## 重新启动
* sh /fs/restart.sh; tail -f /fs/server.log

## 查看日志
* tail -f /fs/server.log

## 设置服务端口
默认udp 150和tcp 150 ,修改端口后服务端会自动修改防火墙.

linux版: mkdir -p /fs/cnf/ ; echo 端口号 > /fs/cnf/listen_port ; sh /fs/restart.sh

windows 版: 在cnf目录下新建文件listen_port,文件内容为端口号.

注意:由于finalspeed的工作原理,不要开放finalspeed所使用的tcp端口.

## 设置开机启动
* chmod +x /etc/rc.local

使用vim编辑:

* vim /etc/rc.local

加入该行：sh /fs/start.sh

## 设置每天3点自动重启
* crontab -e

添加该行：0 3 * * *  sh /fs/restart.sh
