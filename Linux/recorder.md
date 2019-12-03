## `yum`
### 配置`yum`源
#### `yum`配置文件
```
/etc/yum.conf
```
#### 源列表
```
/etc/yum.repos.d/
```
#### 查看源状态
```bash
yum repolist all
```
#### 添加aliyun源
```bash
wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo
```
或
```bash
curl -o /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo
```
然后`yum makecache`即可

## `emacs`
### 取消自动备份
在`~/.emacs`（没有则创建一个）中添加下面语句
```
(setq backup-directory-alist (quote (("." . "~/.backups"))))
```


## `OpenSSH`
### 免密登录
#### 创建密钥
```bash
# 以下两种任选其一
ssh-keygen -t rsa    #生成RSA密钥对
ssh-keygen -t ecdsa  #生成DSA密钥对
```
#### 上传公钥到服务器
```bash
ssh-copy-id root@111.111.111.111
```
若该服务器已认证需要删除重新认证
```bash
ssh-keygen -R root@111.111.111.111
```
### 别名登录
在~/.ssh/config（没有则创建一个）添加以下内容
```bash
Host XXX                              # 别名
    HostName 111.111.111.111          # ip地址
    Port 22                           # 端口号
    User root                         # 用户名
    IdentityFile  ~/.ssh/id_rsa.pub   # 公钥路径
    IdentitiesOnly yes                # 仅密钥登陆
```
config需要600权限
```bash
chmod 600 config
```
