~~~
sudo pacman -Sy gst-plugins-{bad,good,base,ugly} gst-libav lame       #直接运行即可  
sudo pacman -Sy vlc        #但是有时候你希望使用 VLC 解码，要么你可以直接安装 VLC：
yay -S gst-plugin-libde265 libvlc       #如果你还需要 h.265 编码格式的解码，或者你想要 vlc 解码器，又不想安装 vlc 播放器。你可能需要启用 AUR。使用 AUR 工具安装（你得提前安装好 yay，或者其他 AUR 工具）
~~~
