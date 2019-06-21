# 安装python3,pip3,setuptools
```shell
sudo yum install epel-release
sudo yum install python34
curl -O https://bootstrap.pypa.io/get-pip.py
sudo /usr/bin/python3.4 get-pip.py
```

# 安装最新版docker
```shell
curl -s https://get.docker.com/ | sh
```

# 安装docker-compose
```shell
yum -y install py-pip python-dev libffi-dev openssl-dev gcc libc-dev make
sudo curl -L "https://github.com/docker/compose/releases/download/1.24.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
docker-compose --version
```

# FileBrowser(多线程下载)(需要docker,docker-compose)
```shell
git clone https://github.com/bboysoulcn/awesome-dockercompose.git
cd awesome-dockercompose/filebrowser/
nano docker-compose.yaml
# 修改下面的data为宿主机的目录
- "/data:/srv"
# 保存
docker-compose up -d
```

# 当前目录下开启nginx下载服务器,不过不显示目录.[使用方法](https://gwjczwy.github.io/2019/04/26/%E4%BD%BF%E7%94%A8nginx%E6%90%AD%E5%BB%BA%E6%96%AD%E7%82%B9%E7%BB%AD%E4%BC%A0%E6%96%87%E4%BB%B6%E4%B8%8B%E8%BD%BD%E6%9C%8D%E5%8A%A1%E5%99%A8/)
```
docker container run -d --rm --name nginx -p 0.0.0.0:80:80 -v $PWD:/usr/share/nginx/html nginx
```

# WPScan
```shell
docker run -it --rm wpscanteam/wpscan --url https://target.tld/ --enumerate u
```
后面的 --url 参数是要扫描的域名 详见 [https://xz.aliyun.com/t/2794](https://xz.aliyun.com/t/2794)

# sqlmap
```shell
#### 显示详细信息 从Google寻找目标 跳过询问 绕过WAF
python sqlmap.py -v3 -g inurl:php?uid= –answers="quit=N,follow=N,keep testing=Y,sitemap=Y,test=Y" --batch –tampertamper/between.py,tamper/randomcase.py,tamper/space2comment.py
```

