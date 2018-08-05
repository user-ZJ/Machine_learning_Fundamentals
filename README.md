# 机器学习基础
## 环境配置
### Ubuntu环境下编译TensorFlow
1. 安装oracle版本jdk1.8 下载地址http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html
2. 安装Python3及tensorflow依赖包
sudo apt-get install python-pip python-dev python-numpy swig
3. 安装Bazel
>源码安装
$ git clone https://github.com/bazelbuild/bazel.git
$ cd bazel
$ git checkout tags/0.1.0
$ ./compile.sh
将执行路径 output/bazel 添加到 $PATH 环境变量中
>
>release安装
https://github.com/bazelbuild/bazel/releases
chmod +x PATH_TO_INSTALL.SH
./PATH_TO_INSTALL.SH --user
将export PATH=$PATH:/home/user/bin加入到.bashrc
4. 克隆TensorFlow仓库
git clone --recurse-submodules https://github.com/tensorflow/tensorflow
--recurse-submodules 参数是必须得, 用于获取 TesorFlow 依赖的 protobuf 库.
5. android sdk和NDK下载
https://developer.android.google.cn/studio/#downloads
https://developer.android.google.cn/ndk/downloads/
6. 编译TensorFlow
$ bazel build -c opt //tensorflow/tools/pip_package:build_pip_package
$ bazel-bin/tensorflow/tools/pip_package/build_pip_package /tmp/tensorflow_pkg
.whl 文件的实际名字与你所使用的平台有关
$ pip install /tmp/tensorflow_pkg/tensorflow-0.5.0-cp27-none-linux_x86_64.whl
7. 常见错误
status 4 是内存不足的问题，只需要增加swap空间即可
Ubuntu下增加swap空间的命令如下：
生成swap镜像文件
sudo dd if=/dev/zero of=/mnt/1024Mb.swap bs=1M count=1024
对该镜像文件格式化
sudo mkswap /mnt/1024Mb.swap
挂载该镜像文件 
sudo swapon /mnt/1024Mb.swap
至此，使用free -m 即可查看到swap空间已经增加成功。

参考：http://www.tensorfly.cn/tfdoc/get_started/os_setup.html


# 两类问题

    分类：把数据划分成不同的类别
    回归：建立数据间的连续关系

# 方差和协方差区别
均值：
![](image/junzhi.png)
方差：
![](image/fangcha.png)
协方差：
![](image/xiefangcha.png)

方差和协方差区别：
1. 方差的计算公式，我们知道方差的计算是针对一维特征，即针对同一特征不同样本的取值来进行计算得到；而协方差则必须要求至少满足二维特征。可以说方差就是协方差的特殊情况。　
2. 方差和协方差的除数是n-1，这样是为了得到方差和协方差的无偏估计

