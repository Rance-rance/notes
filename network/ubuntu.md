# 修改ubuntu的IP地址

## netplan

以下命令适用于netplan目录下只有一个配置文件的情况,若有多个,则需要判断使用哪个配置文件.

```
#vim /etc/netplan/*.yaml
```

配置文件的内容应该为:

```yaml
network: 
  ethernets:
    <网卡>:
      addresses: 
      - [<ip地址>/<子网掩码>]
      nameservers:
      	addresses: 
      	- <DNS>
      	search: []
      routes:
      - to: default
      	via: <网关>
  version: 2
```

其中网卡一般不用改变.ip地址,子网掩码,DNS和网关等需要配置.

使用这种方式配置,虚拟机是如何访问外部网络的呢?使用桥接模式,即将虚拟机和宿主机同时接入一个虚拟交换机.

使配置生效:

```
#netplan apply
```

## network

