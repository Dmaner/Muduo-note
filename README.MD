# Muduo源码学习记录

> 记录通过对muduo的学习, 增加对网络编程能力

# Muduo编译安装

安装依赖

```shell
sudo apt-get install cmake libboost-dev libboost-test-dev
```

下载muduo

```shell
git clone https://github.com/chenshuo/muduo.git
```

编译安装

```shell
cd muduo
./build.sh install # 完成后在上级目录会有build文件
```

设置头文件目录方便编译

```shell
cd ~/build/release-install-cpp11/include
sudo cp -r muduo /usr/include/
cd ~/build/release-install-cpp11/lib
cp -r * /usr/include/
```

测试: 编译一个echo服务器

代码

```text
见note/echo.cc
```

编译命令

```shell
g++ -o echo echo.cc -lmuduo_net -lmuduo_base -lpthread
```

效果
```shell
dman@DESKTOP:~$ ./echo
20201231 13:08:22.453775Z  9566 INFO  pid = 9566 - echo.cc:60
```

# 参考
Linux多线程服务器编程