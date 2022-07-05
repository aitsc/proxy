# 使用方式
1. 本地安装并打开 [clash](https://github.com/Fndroid/clash_for_windows_pkg/releases)
2. 本地打开cmd执行: ssh 服务器用户名@服务器地址 -p 服务器端口 -R 23456:127.0.0.1:7890
3. 服务器执行命令 (或者下载proxy用sftp上传到用户目录): cd && git clone https://github.com/aitsc/proxy.git
4. 服务器执行命令测试 (下面2个都可以,首选第1个):
   - ~/proxy/proxychains4 -f ~/proxy/proxychains.conf curl baidu.com
   - ~/proxy/mgraftcp --http_proxy=127.0.0.1:23456 curl baidu.com
5. 将上面的 "curl baidu.com" 修改为自己要执行的命令和参数, 例如 "python xxx.py", "pip install xxx", ...

# Other
sudo yum install gcc make git

## proxychains-ng
Compiled on centos7 on 2022-07-04, >=4.16
```shell
git clone https://github.com/rofl0r/proxychains-ng
cd proxychains-ng
./configure --prefix=/usr --sysconfdir=/etc
make & make install
make install-config
vi /etc/proxychains.conf
```

## graftcp
Compiled on centos7 on 2022-07-03, >=0.4.0
```shell
cd && mkdir tmp && cd tmp
wget https://go.dev/dl/go1.18.3.linux-amd64.tar.gz
tar -xzf go1.18.3.linux-amd64.tar.gz
export PATH=$PATH:$(pwd)/go/bin
git clone https://github.com/hmgle/graftcp.git
cd graftcp && make
```