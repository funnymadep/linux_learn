# windows vscode cmake 环境搭建

## 1. windows的mingw自带c/c++库 无需指定
你需要下载mingw，vscode和cmake，这点不需要多叙述，然后在windows环境变量中添加mingw/bin和cmake/bin。

方法为邮件此电脑->属性->高级系统设置->环境变量，然后在系统变量里添加你的bin路径，一般目前都会在安装时自动添加。

## 2. windows的cmake 
你有两种方法

1. 需要在project之前指定编译器路径，比如

```cmake
cmake_minimum_required(VERSION 3.10)  # 必须
set(CMAKE_CXX_STANDARD 11)	# C++14

set(CMAKE_GENERATOR "MinGW Makefiles")
SET(CMAKE_C_COMPILER D:/codeSpace/MinGW/bin/gcc.exe)
SET(CMAKE_CXX_COMPILER D:/codeSpace/MinGW/bin/g++.exe)

project(cut_line)  #工程名

# include_directories("/usr/local/include/") # 头文件目录
# link_directories("/usr/local/lib/") # 链接库目录

aux_source_directory(. SRCS) # 源文件
add_executable(${PROJECT_NAME} ${SRCS}) # 生成可执行文件，这里程序名即为功能名

#target_link_libraries(${PROJECT_NAME} pthread) # 链接库
```
然后使用vscode来自己配置cmake环境 自己找编译器
```text
ctrl + shift + p > cmake: scan for kits 
ctrl + shift + p > cmake: select a kit  # 选择GCC
```
接着可以使用cmake了
```cmake
    mkdir build
    cd build
    cmake ..
```

2. (**推荐**)或者你需要cmake命令行指定编译器路径，比如
```powershell
cmake -G "MinGW Makefiles" ..
```
这样CmakeLists.txt可以正常写
```cmake
cmake_minimum_required(VERSION 3.10)  # 必须
set(CMAKE_CXX_STANDARD 11)	# C++14
project(cut_line)  #工程名

# include_directories("/usr/local/include/") # 头文件目录

# link_directories("/usr/local/lib/") # 链接库目录

aux_source_directory(. SRCS) # 源文件

add_executable(${PROJECT_NAME} ${SRCS}) # 生成可执行文件，这里程序名即为功能名

#target_link_libraries(${PROJECT_NAME} pthread) # 链接库
```

## 3.windows 的make

windows里没有make，取而代之的是mingw32-make，有两种方法
- 使用mingw32-make
```powershell
    mingw32-make
```
- (**推荐**)创造一个make

去mingw/bin目录，找到mingw32-make.exe，复制，然后重命名成make.exe
