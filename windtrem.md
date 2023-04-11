## 怎么给服务器连网
~~~
1.使用本地的终端连接服务器
ssh -p 2105 -X taoxy@192.168.19.178    #服务器上没有安装Xservice服务，而本地的linux系统有，所以需要通过本地连接 
2.输入连接网络的指令                      
epihany
~~~

## 下载rz/sz安装及使用方法
~~~
 首先通过sftp工具把安 装文件上传到tmp目录下
 cd app
 tar zxvf lrzsz-0.12.20.tar.gz && cd lrzsz-0.12.20
  ./configure --prefix=$HOME/app/lrzsz && make && make install   #指定安装路径并安装该软件
 cd /data/home/taoxy/app/lrzsz/bin
 ln -s /data/home/taoxy/app/lrzsz/bin/lrz rz
 ln -s /data/home/taoxy/app/lrzsz/bin/lsz sz 
 PATH=/data/home/taoxy/app/lrzsz/bin:$PATH   #添加到环境变量中去
 source ~/.bashrc  #保存修改过后的bashrc文件
 ~~~

## 下载NCBI SRA toolkit的方法
~~~
wget wget https://ftp-trace.ncbi.nlm.nih.gov/sra/sdk/3.0.2/sratoolkit.3.0.2-ubuntu64.tar.gz    #先下载安装包，上传到指定目录
tar -xzf name      #转到该目录下，并进行解压
cd dirtory         #转到解压后的目录
PATH=/data/home/taoxy/bioapp//bin:$PATH   #添加到环境变量中去
source ~/.bashrc
vdb-config --version  #用于在命令行界面中检查和显示已安装的NCBI SRA toolkit版本
~~~




























