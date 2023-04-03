~~~
在 Arch Linux 中安装多媒体解码器
由于 Arch Linux 是纯粹的社区发行版，可以规避一些法律风险。因此 Arch Linux 的官方软件源中就有一些多媒体包。
你只需要运行：
sudo pacman -Sy gst-plugins-{bad,good,base,ugly} gst-libav lame
就可以解决大部分的多媒体解码了。但是有时候你希望使用 VLC 解码，要么你可以直接安装 VLC：
sudo pacman -Sy vlc
如果你还需要 h.265 编码格式的解码，或者你想要 vlc 解码器，又不想安装 vlc 播放器。你可能需要启用 AUR。
使用 AUR 工具安装（你得提前安装好 yay，或者其他 AUR 工具）：
yay -S gst-plugin-libde265 libvlc
~~~
