```
sudo add-apt-repository ppa:graphics-drivers/ppa
sudo apt update
sudo apt install ubuntu-drivers-common
ubuntu-drivers devices
sudo apt -o Acquire::http::proxy=http://192.168.101.73:1080 install nvidia-driver-450
sudo reboot
nvidia-smi
nvidia-smi -L
```

下载cuda :https://developer.nvidia.com/cuda-10.2-download-archive?target_os=Linux&target_arch=x86_64&target_distro=Ubuntu&target_version=1804&target_type=runfilelocal

```
sudo sh cuda_10.2.89_440.33.01_linux.run
$accept
//取消驱动选择
$install
```

配置cuda
```
$sudo apt install vim
$sudo vim ~/.bashrc
//尾部添加以下三行
export CUDA_HOME=/usr/local/cuda-10.2
export LD_LIBRARY_PATH=/usr/local/cuda-10.2/lib64
export PATH=${CUDA_HOME}/bin:${PATH}
$source ~/.bashrc
$nvcc -V
```
安装cuDNN
https://developer.nvidia.com/rdp/cudnn-download
wget https://developer.nvidia.com/compute/machine-learning/cudnn/secure/8.0.5/10.2_20201106/cudnn-10.2-linux-x64-v8.0.5.39.tgz

安装添加软连接
```
sudo tar -xvf cudnn-10.2-linux-x64-v8.0.5.39.tgz
sudo cp -a cuda/lib64/. /usr/local/cuda-10.2/lib64/
sudo cp -a cuda/include/. /usr/local/cuda-10.2/include/
sudo vim /etc/ld.so.conf.d/cuda.conf
//添加
/usr/local/cuda/lib64
//保存
sudo ldconfig
```
dlconfig中is not a symbolic link错误
```
$ sudo ln -sf /usr/local/cuda-10.2/targets/x86_64-linux/lib/libcudnn.so.8.0.5 /usr/local/cuda-10.2/targets/x86_64-linux/lib/libcudnn.so.8

$ sudo ln -sf /usr/local/cuda-10.2/targets/x86_64-linux/lib/libcudnn_adv_train.so.8.0.5 /usr/local/cuda-10.2/targets/x86_64-linux/lib/libcudnn_adv_train.so.8

$ sudo ln -sf /usr/local/cuda-10.2/targets/x86_64-linux/lib/libcudnn_ops_infer.so.8.0.5 /usr/local/cuda-10.2/targets/x86_64-linux/lib/libcudnn_ops_infer.so.8

$ sudo ln -sf /usr/local/cuda-10.2/targets/x86_64-linux/lib/libcudnn_cnn_infer.so.8.0.5 /usr/local/cuda-10.2/targets/x86_64-linux/lib/libcudnn_cnn_infer.so.8

$ sudo ln -sf /usr/local/cuda-10.2/targets/x86_64-linux/lib/libcudnn_adv_infer.so.8.0.5 /usr/local/cuda-10.2/targets/x86_64-linux/lib/libcudnn_adv_infer.so.8

$ sudo ln -sf /usr/local/cuda-10.2/targets/x86_64-linux/lib/libcudnn_cnn_train.so.8.0.5 /usr/local/cuda-10.2/targets/x86_64-linux/lib/libcudnn_cnn_train.so.8

$ sudo ln -sf /usr/local/cuda-10.2/targets/x86_64-linux/lib/libcudnn_ops_train.so.8.0.5 /usr/local/cuda-10.2/targets/x86_64-linux/lib/libcudnn_ops_train.so.8
```

# 删除驱动
sudo apt-get purge --remove nvidia-*
