Linux下v2ray客户端配置
=====================

先到`https://github.com/v2ray/v2ray-core/releases/`上下载Linux用的客户端，随后解压出一个名为「v2ray-vx.xx-linux-xx」的文件夹，把脚本最后让您下载的`config.json`放到这个文件夹里。

运行软件的方式有两种：

第一种，请在刚才的文件夹里打开终端，运行

```
./v2ray --config=/到这个文件夹的路径/config.json
```

第二种，可以建立一个桌面项，像图标一样双击运行：

```
[Desktop Entry]
Name=V2Ray
GenericName=V2Ray Client
Comment=A platform for building proxies to bypass network restrictions.
Exec=/到你文件夹的路径/v2ray --config=/到你文件夹的路径/config.json
Icon=/到自定义图标图片的路径
Terminal=true
Type=Application
Categories=Network;Internet;
```

保存上面的内容至`v2ray.desktop`，随后使用

```
chmod a+x v2ray.desktop
```

就可以双击执行V2Ray了。若要想这个桌面项出现在应用程序列表里，那就把`v2ray.desktop` 文件复制到 `/usr/share/application` 里即可。（需要root）

接下来就是设定系统代理，让其指向 127.0.0.1 的 1080 端口。
