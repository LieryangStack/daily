## 1 禁用nouveau(nouveau是通用的驱动程序)（必须）

1. `lsmod | grep nouveau` 命令查看是否有输出

2. 如果有输出， `sudo gedit /etc/modprobe.d/blacklist.conf`末尾输入：

    ```
    blacklist nouveau

    options nouveau modeset=0
    ```
3.重启后，重新查看`lsmod | grep nouveau`是否有输出

## 2 安装依赖

```
sudo apt-get update   #更新软件列表
 
sudo apt-get install g++ gcc make -y
```

## 3 安装驱动

下载相应驱动：[https://www.nvidia.cn/Download/index.aspx?lang=en-us](https://www.nvidia.cn/Download/index.aspx?lang=en-us)

```sh
sudo telinit 3  #进入文本界面
sudo service gdm3 stop   #停止显示服务
sudo chmod 777 NVIDIA-Linux-x86_64-430.26.run   #给你下载的驱动赋予可执行权限，才可以安装
sudo ./NVIDIA-Linux-x86_64-430.26.run    #安装
sudo  service  gdm3 start   #重启显示服务，完成
```