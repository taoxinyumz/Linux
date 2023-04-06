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

## 持久性改变字体
~~~
vim /etc/vconsole.conf
FONT=late2-16     #/etc/vconsole.conf 的 FONT 变量可以用来在启动时设置字体, 对于所有的终端都具有持久性作用。
~~~

## 安装Wechat
~~~
git clone https://gitclone.com/github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting\n
git clone https://gitclone.com/github.com/zsh-users/zsh-autosuggestions.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions\n
vim ~/.zshrc
source ~/.zshrc
echo "export TERM=xterm-256color" >> ~/.zshrc
yay -S deepin-wine-wechat
ls
yay -S axel
axel -a https://github.91chi.fun/https://github.com/vufa/deepin-wine-wechat-arch/releases/download/v3.9.0.28-3/deepin-wine-wechat-3.9.0.28-3-x86_64.pkg.tar.zst
axel -a https://gh.ddlc.top/https://github.com/vufa/deepin-wine-wechat-arch/releases/download/v3.9.0.28-3/deepin-wine-wechat-3.9.0.28-3-x86_64.pkg.tar.zst
sudo pacman -U deepin-wine-wechat-3.9.0.28-3-x86_64.pkg.tar.zst
yay -S deepin=wine6-stable
yay -S deepin-wine6-stable
yay -S deepin-wine6-helper
yay -S deepin-wine-helper
sudo pacman -U deepin-wine-wechat-3.9.0.28-3-x86_64.pkg.tar.zst
yay -S deepin-wine-qq
yay -S fcitx5 fcitx5-qt fcitx5-gtk fcitx5-configtool
vim ~/.pam_environment
vim ~/.xprofile
yay -S rime-cloverpinyin
cd ~/.local/share/fcitx5
ls
cd rime
ls
less default.custom.yaml
reboot
cd ~/.config/fcitx5
ls
cd conf
ls
nohup clash &
ping www.baidu.com
cd app
git clone https://hub.fgit.gq/ayamir/fcitx5-nord.git
cd fcitx5-nord
cp -r Nord-Dark/ Nord-Light/ ~/.local/share/fcitx5/themes/
vim ~/.config/fcitx5/conf/classicui.conf
clash
cd ~
pwd
~~~





