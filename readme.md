sudo yum install gcc make git

## proxychains-ng
Compiled on centos7 on 2022-07-04, >=4.16
```shell
git clone https://github.com/rofl0r/proxychains-ng
cd proxychains-ng
./configure --prefix=/usr --sysconfdir=/etc
make & make install
make install-config
vim /etc/proxychains.conf
    socks5  127.0.0.1 46153
proxychains4 curl baidu.com
```

## graftcp
Compiled on centos7 on 2022-07-03, >=0.4.0
```shell
cd && mkdir tmp && cd tmp
wget https://go.dev/dl/go1.18.3.linux-amd64.tar.gz
tar -xzf go1.18.3.linux-amd64.tar.gz
export PATH=$PATH:$(pwd)/go/bin
go version
git clone https://github.com/hmgle/graftcp.git
cd graftcp && make
./local/mgraftcp --socks5=127.0.0.1:46153 curl baidu.com
```