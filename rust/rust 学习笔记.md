## rust 学习笔记

### 一、环境搭建

1. 搭建环境前需要安装 `C++ Build Tools` 否则安装rust后无法进行编译，因此需要安装` Visual Studio` 并选择其中**面向桌面开发的C++** 一项即可

2. rust无法在安装时选择安装路径，因此想要更改rust安装路径的话需要在安装前设置环境变量 `RUSTUP_HOME` 以及 `CARGO_HOME` 
   - `RUSTUP_HOME`指定`rustup`的安装目录 例：`D:\software\rust\.rustup`
   - `CARGO_HOME`指定`cargo`的安装目录 例：`D:\software\rust\.cargo`

3. 上述两步完成后即可运行rust安装程序，此时出现三个选项，输入 1 （默认安装）即可

