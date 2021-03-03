
# 安装 python3.8
```
下载源码
wget https://www.python.org/ftp/python/3.8.0/Python-3.8.0.tgz
解压源码
tar -xvzf Python-3.8.0.tgz
进入目录
cd Python-3.8.0
配置安装路径
./configure --with-ssl --prefix=/usr/local/python3
安装python3.8.0依赖
#sudo apt-get update
#sudo apt-get upgrade
#sudo apt-get dist-upgrade
sudo apt-get install build-essential python-dev python-setuptools python-pip python-smbus libncursesw5-dev libgdbm-dev libc6-dev zlib1g-dev libsqlite3-dev tk-dev libssl-dev openssl libffi-dev
编译
make
安装
sudo make install
删除软链接
sudo rm -rf /usr/bin/python3
sudo rm -rf /usr/bin/pip3
新建软链接
sudo ln -s /usr/local/python3/bin/python3.8 /usr/bin/python3
sudo ln -s /usr/local/python3/bin/pip3.8 /usr/bin/pip3
检查是否安装成功
python3
```

