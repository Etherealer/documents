## rust 学习笔记

### 第一章 入门指南

#### 1. 1 环境搭建

1. 搭建环境前需要安装 `C++ Build Tools` 否则安装rust后无法进行编译，因此需要安装` Visual Studio` 并选择其中**面向桌面开发的C++** 一项即可

2. rust无法在安装时选择安装路径，因此想要更改rust安装路径的话需要在安装前设置环境变量 `RUSTUP_HOME` 以及 `CARGO_HOME` 
   - `RUSTUP_HOME`指定`rustup`的安装目录 例：`D:\software\rust\.rustup`
   - `CARGO_HOME`指定`cargo`的安装目录 例：`D:\software\rust\.cargo`

3. 上述两步完成后即可运行rust安装程序，此时出现三个选项，输入 1 （默认安装）即可

> 安装完成后 可打开cmd 输入`rustc -V` 以及 `cargo -V` 进行检验是否安装成功

#### 1.2 rust 更新与卸载

```shell
rustup update # 用于更新rust 版本
rustup self uninstall # 用于卸载rustup以及rust工具链
```

#### 1.3 Hello,World!

安装完rust后 我们就可以编写程序了，对于rust而言，笔者使用vscode进行编写，我们可以新建一个`main.rs`文件

编入以下代码：

```rust
fn main(){
    println!("Hello,World!");
}
```

编写完成后 通过控制台使用`rustc main.rs`对文件进行编译，编译后会生成`main.exe`文件，我们可以使用 `.\main.exe`执行文件，此外对于windows平台而言还会生成一个`main.pdb`文件，该文件带有调试信息。

下面对程序进行解析：

1. `fn`是关键字 定义函数时使用
2. `main`函数与其他程序一致，都是程序的入口函数
3. `println!` 是一个宏，用于将字符串输出到终端使用，不是函数

对于简单的程序而言，我们可以使用rustc进行编译，但对于复杂的工程而言，就需要我们使用rust的构建工具`cargo`进行处理了

#### 1.4 Hello,Cargo!

cargo是rust工具链中内置的构建系统以及包管理器，对于需要众多依赖以及复杂的项目而言，使用cargo会让工作变得更加简单。

cargo创建项目：

```shell
cargo new hello_cargo
cd hello_cargo
```

对于rust而言，`文件名、变量名以及函数名`使用`蛇形命名法`

通过上述命令我们就可以创建一个rust项目，对于这个项目而言初始内容只有两个文件以及一个目录，一个Cargo.toml文件以及一个被放置在src文件夹下的main.rs文件，同时该项目会初始化一个git仓库。

##### 1.4.1 Cargo.toml

```toml
[package]
name = "hello_cargo"
version = "0.1.0"
author = ["Your Name <you@example.com>"]
edition = "2021"

# See more keys and their definitions at https://doc.rust-lang.org/cargo/reference/manifest.html

[dependencies]

```

cargo使用toml作为标准的配置格式
