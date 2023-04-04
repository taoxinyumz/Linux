## 安装视频解码器
~~~
sudo pacman -Sy gst-plugins-{bad,good,base,ugly} gst-libav lame       #直接运行即可  
sudo pacman -Sy vlc        #但是有时候你希望使用 VLC 解码，要么你可以直接安装 VLC：
yay -S gst-plugin-libde265 libvlc       #如果你还需要 h.265 编码格式的解码，或者你想要 vlc 解码器，又不想安装 vlc 播放器。你可能需要启用 AUR。使用 AUR 工具安装（你得提前安装好 yay，或者其他 AUR 工具）
~~~

## 安装flash插件
~~~
sudo yaourt -S chromium-pepper-flash
~~~

## 安装声音
~~~
sudo pacman -Syu #更新系统
sudo pacman -S pulseaudio pulseaudio-alsa pavucontrol #安装 PulseAudio
pulseaudio --start #安装完成后，启动 PulseAudio 服务
pacmd list-sinks #检查 PulseAudio 是否已经正确安装
~~~

## 视频无法播放时怎么办
~~~
应该是更新后wireplumber 取代 pipewire-media-session 产生的冲突问题，我是通过
注释  /etc/pulse/default.pa中的
# load-module module-suspend-on-idle
~~~

## 安装setuptools
~~~
sudo pacman -S python-setuptools    #在 Arch Linux 上，可以使用该命令安装
~~~
