## 共享文件夹
```
vmware-toolbox-cmd -v确认运行

sudo mkdir /mnt/hgfs创建

sudo vmhgfs-fuse -o allow_other -o auto_unmount .host:/ /mnt/hgfs允许root和其他用户访问
```
## vi编辑文件时上下左右键出现ABCD现象
```
sudo apt-get update
sudo apt-get remove vim-common
sudo apt-get install vim
```
## export
```
export LD_LIBRARY_PATH=../../lib/uclibc:$LD_LIBRARY_PATH
```
