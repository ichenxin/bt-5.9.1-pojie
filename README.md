# 宝塔5.9.1专业版手动破解方法

# 首先安装面板免费版

CentOS
```
yum install -y wget && wget -O install.sh http://download.bt.cn/install/install.sh && sh install.sh
```

Debian/Ubuntu
```
wget -O install.sh http://download.bt.cn/install/install.sh && sh install.sh
```

# 然后升级专业版
```
wget -O update.sh http://download.bt.cn/install/update_pro.sh && bash update.sh pro
```

找到路径/www/server/panel/class 找到文件名或者直接搜索：common.py

搜索代码164行
data = panelAuth().get_order_status(None)

替换成
data = {'status' : True,'msg' : {'endtime' : 32503651199 }}

完成后，进入 /www/server/panel/data 新建一个文件 文件名为：userInfo.json 内容空的，如果存在这个文件的删掉重新新建文件。

最后输入命令 /etc/init.d/bt restart 重启宝塔 完美嗨皮！！

注意：安装前请关闭宝塔网页  防止错误

# 如果使用失败，请恢复成免费版
代码为
```
wget -O update.sh http://download.bt.cn/install/update.sh && bash update.sh free
```

本地玩下可以 运营请支持正版
