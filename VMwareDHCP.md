---
tittle: VMware 自動用VM建的DHCP Server
tags: Linux,VMware,DHCP
---

# VMware 自動用VM建的DHCP Server
### 1. 修改/etc/vmware/networking

* 先把設定成如下的格式
* VNET_X ==> 要設定的網卡
```
answer VNET_2_DHCP no //不用Vmware內建的DHCP Server
answer VNET_2_DISPLAY_NAME 
answer VNET_2_HOSTONLY_NETMASK 255.255.255.0
answer VNET_2_HOSTONLY_SUBNET no //不用固定IP
answer VNET_2_VIRTUAL_ADAPTER yes
```
### 2.打開Virtual Network Editor且點要設定的網卡進行如下設定
![](https://i.imgur.com/LxcDrIl.png)

### 3. 重新找DHCP Server
```
[zangmenhsu@E1304 ~]$sudo dhclient vmnet2
```

