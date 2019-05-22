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

# 当前目录下开启nginx下载服务器,不过不显示目录
```
docker container run -d --rm --name nginx -p 0.0.0.0:80:80 -v $PWD:/usr/share/nginx/html nginx
```
