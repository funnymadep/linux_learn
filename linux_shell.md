# linux常规指令


## 常用linux指令

### 查看图片

```bash
    eog xxx.png
    eog xxx.jpg
    eog xxx.bmp
```

###  查看pdf

```bash
    evince xxx.pdf
```

###  后台运行程序且输出到/dev/null

```bash
    nohup ./your_exe >> /dev/null 2>&1 &
```

###  查看当前网段的所有ip地址

```bash
    nmap -sn 192.168.1.1/24
```
### linux ssh连接

```bash
    ssh usrname@ip地址
    #ssh sd123456@192.168.1.103
```
### 查找指定文件

```bash
    find /dir -name filename
```
### 查看linux基础信息

```bash
    neofetch
```
### 查看目录结构

```bash
    tree
```

### 转换图片类型与格式

``` bash
    convert image.png -resize 64x64 image.ico
    #sudo apt intall imagemagic
```
