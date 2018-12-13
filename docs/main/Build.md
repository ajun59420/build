# 从源码运行
1. 从 `https://github.com/TeaWeb/build` 中下载项目，放到本地磁盘上；
2. 设置全局变量`GOPATH`为项目目录路径；
3. `cd` 到 *src/main* 目录
4. 执行 `init.sh` 初始化项目，如果下载中出现网络错误，可以尝试多次运行此脚本；
5. 执行 `run.sh` 启动项目；
6. 在浏览器中访问 `http://127.0.0.1:7777` 。

# 从源码编译
1. 从 *https://github.com/TeaWeb/build* 中下载项目，放到本地磁盘上；
2. 设置全局变量`GOPATH`为项目目录路径；
3. `cd` 到 *src/main* 目录
4. 执行 `init.sh` 初始化项目，如果下载中出现网络错误，可以尝试多次运行此脚本；
5. 运行 `build-[系统版本].sh` 构建可执行文件；
6. 构建后的文件在 `项目根目录/dist/` 目录下。