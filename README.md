# jetson_nx_opencv

# jtop安装
$sudo apt-get install python3-pip

$sudo pip3 install jetson-stats   (包含jtop）

$sudo jtop

# opencv4.5.1 安装
https://spyjetson.blogspot.com/2020/08/jetson-xavier-nx-opencv-44.html
# 安装脚本
https://github.com/raspberry-pi-maker/NVIDIA-Jetson/tree/master/useful_scripts

# recipe for target 'all' failed问题解决方案
保证网格有梯子

# 安装dlib及其环境：
$ sudo apt install libblas-dev liblapack-dev libjpeg-turbo8-dev libopenblas-dev

$ sudo apt install libx11-dev

$ sudo apt install libboost-all-dev

//编译前注释掉dlib/cuda下cudnn_dlibapi.cpp文件的第853行的forward_algo = forward_best_algo
$ wget https://github.com/davisking/dlib/archive/v19.21.zip

```
tar xvf dlib-19.21.tar.bz2
cd dlib-19.21/
mkdir build
cd build
cmake -DBUILD_SHARED_LIBS=ON -DDLIB_USE_LAPACK=1 ..
cmake --build . --config Release
sudo make install
sudo ldconfig
```

# Gtk安装
$sudo apt install libcanberrra-gtk*
