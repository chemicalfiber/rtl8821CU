# Realtek RTL8811CU / RTL8821CU USB无线网卡的Linux驱动程序

## 使用说明
这是一篇给小白看的使用说明，具体的编译构建指南请查阅<a href="https://github.com/chemicalfiber/rtl8821CU/tree/master/README-Original-en.md">README-Original-en.md<a/>

### 一、确认你的主机环境是Linux（废话）
这里以Ubuntu 20.04LTS作为演示

### 二、安装前置条件和编译环境：
安装`git`、`gcc`、`make`、`bc`、`linux-header或者kernel-devel`。
如果你的系统的包管理系统没有抽风的话`linux-header或者kernel-devel`应该会在安装前面4项的时候自动帮你安装好了。
```shell script
sudo apt install gcc g++ build-essential git dkms
```
### 三、下载驱动源码：
常规做法：
```shell script
git clone https://github.com/chemicalfiber/rtl8821CU.git
```
如果你在中国大陆地区或网络环境不佳：
```shell script
git clone https://ghproxy.com/https://github.com/chemicalfiber/rtl8821CU.git
```
或者：
<a href="https://ghproxy.com/https://github.com/chemicalfiber/rtl8821CU/archive/master.zip" target="_blank">点我直接下载源码zip</a>

你需要手动解压下载后的zip包。
### 四、编译安装：
在终端中逐条输入下列命令：
```shell script
cd rtl8821CU
chmod +x dkms-install.sh
sudo ./dkms-install.sh
sudo modprobe 8821cu
reboot
```

### 五、检查验证
如果你也是使用Ubuntu 20.04LTS，你可以在右上角的快捷设置菜单中看到多出来一项`USB 无线网络 未连接`，这项便是成功驱动之后的USB网卡，使用它连接到你的无线网络吧。

在Gnome的无线网络设置页面中，如果你先前也有内置的PCI无线装置，那么Gnome一般不会默认显示你的USB网络设置，它会在设置窗口上方显示为`Realtek 无线网络`。