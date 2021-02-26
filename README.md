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

# Package opencv4 was not found in the pkg-config search path. Perhaps you should add the directory containing `opencv4.pc'

$sudo sh -c 'echo "/usr/local/lib" > /etc/ld.so.conf.d/opencv.conf'
$sudo ldconfig
