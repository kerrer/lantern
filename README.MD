# Docker 运行 Lantern 4.9.0，科学上网
[![Build Status](https://travis-ci.org/wilon/lantern.svg?branch=master)](https://travis-ci.org/wilon/lantern)
```diff
+ 输入我的邀请码 YMD8TTG 来获得三个月的蓝灯专业版！
- 输入我的邀请码 YMD8TTG 来获得三个月的蓝灯专业版！
```

## 安装方法

```
docker pull wilon/lantern
```

或者源码构建，更适合国内网络：
```
docker build -t wilon/lantern https://raw.githubusercontent.com/wilon/lantern/master/Dockerfile-CN
```

启动：
```
docker run -itd --restart=always --name lantern -p 3128:3128 -p 8080:8080 wilon/lantern
```

## 测试

浏览器打开：http://0.0.0.0:8080/

##### · 测试是否能上Google

`curl -kvx 127.0.0.1:3128 http://www.google.com/humans.txt`，能看到 **Google is built by a**... 就是成功了！

##### · 测试响应时间

`curl -kx 127.0.0.1:3128 -w %{time_namelookup}::%{time_connect}::%{time_starttransfer} https://www.google.com/humans.txt`

## 使用方法

##### · MacOS 配置

设置 -> 网络 -> 高级 -> 代理： *HTTP*、*HTTPS*填上`127.0.0.1:3128`

##### · WIN 配置

设置 -> 网络和Internet -> 代理 -> 手动设置代理： 填上`127.0.0.1:3128`

------
有问题？ [发issues](https://github.com/wilon/lantern/issues)
