# jetson_nx_opencv

# jtop安装
$sudo apt-get install python3-pip
$sudo pip3 install jetson-stats   (包含jtop）
$sudo jtop

# recipe for target 'all' failed问题解决方案

cmake -D WITH_OPENMP=ON
//已更新到shell
