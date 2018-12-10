shadowsocks客户端配置
=====================

shadowsocks的服务器端和客户端安装过程一样。服务器端命令用`ssserver`，客户端用命令`ss-local`。客户端config文件内容：

```
{
  "server":"server地址",
  "local_address": "127.0.0.1",
  "local_port":1082,
  "server_port":服务器端口,
  "password":"服务器端密码",
  "timeout":300,
  "method":"加密方式"
}

用`ss-local -c /path/of/config`就可以成功连接ss服务器。但是这时是socks5代理。可以在fedora的network设置中设置代理为manual方式，打开socks5代理。

### 设置自启动模式

用systemd方式添加自启动脚本，新建systemd的启动配置文件

```
vim /etc/systemd/system/shadowsocks.service
```

在文件中添加如下内容：

```
[Unit]
Description=Shadowsocks Client Service
After=network.target

[Service]
Type=simple
User=root
ExecStart=/usr/local/bin/ss-local -c /etc/shadowsocks-libev/config.json

[Install]
WantedBy=multi-user.target
```

启动脚本：

```
systemctl start shadowsocks
```

将脚本设置为自启动：

```
systemctl enable shadowsocks
```
