## Shadowsocks 一键安装脚本
使用 root 用户登录，运行以下命令：
```bash
wget --no-check-certificate -O shadowsocks-all.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-all.sh
chmod +x shadowsocks-all.sh
./shadowsocks-all.sh 2>&1 | tee shadowsocks-all.log
```

## 开启 BBR 加速
使用 root 用户登录，运行以下命令：
```bash
wget "https://github.com/cx9208/bbrplus/raw/master/ok_bbrplus_centos.sh"
chmod +x ok_bbrplus_centos.sh
./ok_bbrplus_centos.sh
```
