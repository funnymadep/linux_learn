# 树莓派

## 树莓派修改ip地址(debian12)

### 树莓派修改wifi ip地址
```bash
sudo nmcli connection modify shundong-5G ipv4.addresses 192.168.1.150/24 ipv4.method manual
```

### 树莓派修改网线 ip地址
```bash
sudo nmtui
```
**然后进去配置**
**选择网线**
**配置自己想要的ip**
