## 宿主机配置
```
Windows IP 配置


未知适配器 LetsTAP:

   连接特定的 DNS 后缀 . . . . . . . :
   本地链接 IPv6 地址. . . . . . . . : fe80::8b2b:3e34:8f4f:33f0%23
   IPv4 地址 . . . . . . . . . . . . : 26.26.26.1
   子网掩码  . . . . . . . . . . . . : 255.255.255.248
   默认网关. . . . . . . . . . . . . :

Windows IP 配置


未知适配器 LetsTAP:

以太网适配器 以太网:

   媒体状态  . . . . . . . . . . . . : 媒体已断开连接
   连接特定的 DNS 后缀 . . . . . . . :

以太网适配器 vEthernet (Default Switch):

   连接特定的 DNS 后缀 . . . . . . . :
   本地链接 IPv6 地址. . . . . . . . : fe80::2c5c:7d3a:f39c:af1b%25
   IPv4 地址 . . . . . . . . . . . . : 172.31.224.1
   子网掩码  . . . . . . . . . . . . : 255.255.240.0
   默认网关. . . . . . . . . . . . . :

以太网适配器 vEthernet (WSL (Hyper-V firewall)):

   连接特定的 DNS 后缀 . . . . . . . :
   本地链接 IPv6 地址. . . . . . . . : fe80::25fb:2d66:4145:7f98%46
   IPv4 地址 . . . . . . . . . . . . : 172.28.32.1
   子网掩码  . . . . . . . . . . . . : 255.255.240.0
   默认网关. . . . . . . . . . . . . :

无线局域网适配器 本地连接* 11:

   媒体状态  . . . . . . . . . . . . : 媒体已断开连接
   连接特定的 DNS 后缀 . . . . . . . :

以太网适配器 VMware Network Adapter VMnet1:

   连接特定的 DNS 后缀 . . . . . . . :
   本地链接 IPv6 地址. . . . . . . . : fe80::cef9:be17:f5f0:dbc2%4
   IPv4 地址 . . . . . . . . . . . . : 192.168.133.1
   子网掩码  . . . . . . . . . . . . : 255.255.255.0
   默认网关. . . . . . . . . . . . . :

以太网适配器 VMware Network Adapter VMnet8:

   连接特定的 DNS 后缀 . . . . . . . :
   本地链接 IPv6 地址. . . . . . . . : fe80::68a4:df1e:5325:1150%22
   IPv4 地址 . . . . . . . . . . . . : 192.168.80.1
   子网掩码  . . . . . . . . . . . . : 255.255.255.0
   默认网关. . . . . . . . . . . . . :

无线局域网适配器 WLAN:

   连接特定的 DNS 后缀 . . . . . . . :
   IPv4 地址 . . . . . . . . . . . . : 192.168.31.60
   子网掩码  . . . . . . . . . . . . : 255.255.255.0
   默认网关. . . . . . . . . . . . . : 192.168.31.1
```
## vm 虚拟网络配置
```
 VMnet8
NAT模式
	将主机虚拟适配器连接到此网络
    使用本地DHCP 服务将IP地址分配给虚拟机
   
子网ip 子网掩码
192.168.80.0   255.255.255.0
NAT
网关 192.168.80.2

DHCP

192.168.80.3
192.168.80.10
```
## vm的虚拟机
```
root@bun-virtual-machine:~# ip a 
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host 
       valid_lft forever preferred_lft forever
2: ens33: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 00:0c:29:22:c7:f4 brd ff:ff:ff:ff:ff:ff
    altname enp2s1
    inet 192.168.80.4/24 brd 192.168.80.255 scope global dynamic noprefixroute ens33
       valid_lft 1738sec preferred_lft 1738sec
    inet6 fe80::9d8f:8017:1f7:ab93/64 scope link noprefixroute 
       valid_lft forever preferred_lft forever
3: docker0: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc noqueue state DOWN group default 
    link/ether 02:42:fa:93:9e:1b brd ff:ff:ff:ff:ff:ff
    inet 172.17.0.1/16 brd 172.17.255.255 scope global docker0
       valid_lft forever preferred_lft forever
```
