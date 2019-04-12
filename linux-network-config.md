# Linux⽹络配置

## 配置静态IP
* 编辑配置文件
```bash
sudo nano /etc/netplan/50-cloud-init.yaml
```

* 修改配置信息
```txt
network:
    ethernets:
        ens160:
            addresses:
            - 172.16.33.129/24
            dhcp4: false
            gateway4: 172.16.33.254
            nameservers:
                addresses:
                - 202.102.152.3
                search: []
    version: 2
```

## 应用配置
```bash
sudo netplan apply
或
sudo netplan --debug apply
```

## 参考资料
* [How to setup a static IP on Ubuntu Server 18.04](https://askubuntu.com/questions/1029531/how-to-setup-a-static-ip-on-ubuntu-server-18-04)
* [How to configure Network Settings in Ubuntu 18.04 Bionic Beaver](https://www.serverlab.ca/tutorials/linux/administration-linux/how-to-configure-network-settings-in-ubuntu-18-04-bionic-beaver/)
* [How To Configure IP Address In Ubuntu 18.04 LTS](https://www.ostechnix.com/how-to-configure-ip-address-in-ubuntu-18-04-lts/)
* [How to configure a static IP address in Ubuntu Server 18.04](https://www.techrepublic.com/article/how-to-configure-a-static-ip-address-in-ubuntu-server-18-04/)
* [How to Configure Network Static IP Address in Ubuntu 18.04](https://www.tecmint.com/configure-network-static-ip-address-in-ubuntu/)
* [Configure Static IP Addresses On Ubuntu 18.04 LTS Server](https://websiteforstudents.com/configure-static-ip-addresses-on-ubuntu-18-04-beta/)
* [How to configure static IP address on Ubuntu 18.04 Bionic Beaver Linux](https://linuxconfig.org/how-to-configure-static-ip-address-on-ubuntu-18-04-bionic-beaver-linux)
* [linux 下 /etc/network/interfaces 作用](https://blog.csdn.net/guoyaoyao1990/article/details/12623729)
