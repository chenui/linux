将CT中的lubuntu桌面版改为文字模式
=================================

CT中刷了lubuntu desktop每次启动都要启动桌面，太耗费资源。想改成文本模式。在x86版的ubuntu下很好修改，只要更改grub的启动参数就可以。但是在CT的系统中，没有grub的启动选项，google了一下，在网上有人提到可以修改`/etc/X11/default-display-manager`中的内容达到启动到文字模式的目的。

打开`/etc/X11/default-display-manager`文件，注释掉`/usr/sbin/lightdm`，加入`fasle`，重新启动就只有文字模式了，桌面关闭了。