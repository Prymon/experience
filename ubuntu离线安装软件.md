> 如果不能联网，需要离线安装软件包，下文是离线安装说明(将ubuntu的安装iso镜像作为apt源)
```shell
# 备份apt源
sudo cp /etc/apt/sources.list  /etc/apt/sources.list.bak
# 挂载ubuntu iso
mkdir /tmp/apt-source
sudo mount -o loop ubuntu-16.04.1-server-amd64.iso /tmp/apt-source
sudo sh -c "echo 'deb file:///tmp/apt-source  xenial main restricted' > /etc/apt/sources.list"
# 刷新apt源
sudo apt-get update
# 安装必须软件
sudo apt-get install imagemagick -y
sudo apt-get install unzip -y
sudo apt-get install zip -y
# 恢复默认apt源（可不执行）
sudo cp /etc/apt/sources.list.bak  /etc/apt/sources.list
sudo apt-get update
sudo umount /tmp/apt-source
```
