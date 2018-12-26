# MAC远程连接Ubuntu桌面

* 安装VNC服务
```bash
sudo apt-get install x11vnc
```

* 配置VNC
```bash
x11vnc -storepasswd
```

* 启动VNC服务
```bash
x11vnc -forever -shared -rfbauth ~/.vnc/passwd
```

* 连接VNC服务
```txt
打开splotlight，搜索［屏幕共享］，运行。输入IP:5900
```

## 参考资料
* [Mac 远程桌面 ubuntu16.04 unity](https://www.cnblogs.com/nowgood/p/Macremotedesktop.html)