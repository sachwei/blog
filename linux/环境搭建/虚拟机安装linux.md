## 人手一套Linux环境之：Windows版本教程

原创 hansonwong99 [CodeSheep](javascript:void(0);) *5月3日*

![img](https://mmbiz.qpic.cn/mmbiz_png/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0CN5RDngK3bl8lgDa9kPqy14DlGUibTU51duoAZe1F7A1rjKAThfkuQWA/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

------

# 缘由

之前写的一篇 《**[Linux环境搭建](http://mp.weixin.qq.com/s?__biz=MzU4ODI1MjA3NQ==&mid=2247485626&idx=1&sn=9fd011d30805eeaac87314073a1a50b6&chksm=fddede7ecaa95768d64cd3e9cf8587bff052021898ac4ede90e3c433021d127e9b47dbbe07e8&scene=21#wechat_redirect)保姆级操作》** 中是基于macOS宿主机系统搭建的，评论区有很多小伙伴要Windows版本的操作教程。

所以这不就趁着五一假期，从箱底掏出了那台破Windows电脑操作了一遍嘛！

![img](https://mmbiz.qpic.cn/mmbiz_jpg/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0CuwhCUYbrgO7bK7EW8myqIUFeb9W7yBUrHDWIJEOebSusG7Yy2cGZ2Q/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

其实Windows版的操作总体也大差不差，只是部分操作界面有点小变化。

还是那句话，既然学编程，提前备好Linux系统环境非常重要，建议人手一套，这样方便后续 **学Linux**、**用Linux**、**Linux环境编程**、**应用和项目部署**、**工具实验**等一系列学习和实践

------

# 软件版本

- 物理宿主机系统：`Windows 10` 专业版
- 虚拟机软件：`VMware Workstation 10.0.1`版本
- `CentOS`操作系统`ISO`镜像：`CentOS 7.4 64位`
- SSH终端软件：`SecureCRT`
- SFTP文件传输工具：`WinSCP`

------

# 安装Linux操作系统

**1、创建新的虚拟机**

![img](https://mmbiz.qpic.cn/mmbiz_png/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0CQAR8FZrfRcS7QUicjQ5gGPFialiaWRkcHqshEYhRHtzgJn4pIAyt48PgQ/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

**2、选择虚拟机硬件兼容性**

![img](https://mmbiz.qpic.cn/mmbiz_png/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0CEORfW9hxmKicvSkf0ZYpWBC0JOZicpN2yFIpqLg4SMX8SakHmj7dIHQA/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

默认即可

**3、加载Linux系统ISO镜像**

![img](https://mmbiz.qpic.cn/mmbiz_png/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0CQiasGweic0BZbn3U3gbvrmpBR0IBgP7ywxPjH6LAWrl6mJicdicCvTufsA/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

![img](https://mmbiz.qpic.cn/mmbiz_png/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0CSqadciar1hAaDGxHP7iayS2p3NtXH4CfvOXGicibKknyccZLiaYiaPibqF0Dg/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

**4、虚拟机命名并存储**

![img](https://mmbiz.qpic.cn/mmbiz_png/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0CDHibG9nUAoicVjicZWPyC0JicXNkAMMIHQGheNvYvzJicfuZRVp0p2EiatiaA/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

**5、自定义虚拟机配置**

处理器按需配置：

![img](https://mmbiz.qpic.cn/mmbiz_png/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0CRSL2Ioh6P0HrNkFHL9I8NEd8ofCfxw9GDKYibJJW8qMO510aO0ESD4A/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

内存按需配置：

![img](https://mmbiz.qpic.cn/mmbiz_png/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0CFnLX8R5ld3tspc1fO4rqoLdB32kbMxvXmmNbyGTneQOa8kMWRhpIgA/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

网络部分选择「桥接模式」即可：

![img](https://mmbiz.qpic.cn/mmbiz_png/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0CeG0Ak1zBxEJDv42icOAO5L7undzmOVBUIFX03zuyDMQCx3NsSC7dwicw/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

I/O控制器选择默认即可：

![img](https://mmbiz.qpic.cn/mmbiz_png/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0CREr6nprkFb2cNIXOabrPBHhic2FHp9qeQh7wDNroFibItLDB5JgGwSrA/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

硬盘类型选择默认即可：

![img](https://mmbiz.qpic.cn/mmbiz_png/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0Cdg3QJr1kziaOR537NMcmyZoUs2zUahfvMicnJr9eJINzELic59hFRzdfw/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

硬盘容量按需分配：

![img](https://mmbiz.qpic.cn/mmbiz_png/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0CNm0oAqOA1Hm1PNgEVbH5JI05WrJRWmZPCLiafOOBCC1D3L2pyUciaSqA/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

**6、安装设置，开启安装**

![img](https://mmbiz.qpic.cn/mmbiz_png/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0CV9AdjRb7512cGFE0GaX0mQfhG6Olp6zyrJennAAv0rUfQwrp72Lf5w/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

![img](https://mmbiz.qpic.cn/mmbiz_png/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0CNj7SbwgPjERNtfqJPyMrzdDvF06LUZ7vibupamTAYuiaClF2y0TyFW1g/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

**7、进入系统安装界面**

![img](https://mmbiz.qpic.cn/mmbiz_png/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0ClPe0dkCysK8bDMUrucLxX6QLYGuwDfPoYrzOXKibU8mcy2xo5lsPb8Q/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

![img](https://mmbiz.qpic.cn/mmbiz_png/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0CGmgNxia9mLXWsopjicsc9RI0hMNj8Ms0VkPoL0FDqxngomt2PNmb7MEA/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

**8、选择安装语言**

![img](https://mmbiz.qpic.cn/mmbiz_png/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0CzWOOcZdVppPgJJfQFicicpISYU9bov2L1bI5qn5qP3NjIl04YscEzEbw/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

**9、选择预安装的软件**

![img](https://mmbiz.qpic.cn/mmbiz_png/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0CZpK6wMsIBX6D8LvBQnK6ZwNj9vlmJCYX3icY4TDHLyp8PmKfYX5I5tQ/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

![img](https://mmbiz.qpic.cn/mmbiz_png/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0C3UCz6mTOSqnEHsKibFMkNqlGecHUgCfyzXsUXwsCdc1KSbmXWR1dNpw/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

**10、配置分区**

![img](https://mmbiz.qpic.cn/mmbiz_png/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0C9AZDpPA2Zicvia8kia8Ov0bWSicQMDssmpWoibPwpwdOM37ge6K4LVPdp5Q/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

![img](https://mmbiz.qpic.cn/mmbiz_png/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0CIgibcfIrSJLmnoFq1lE1krzfLcB0xyf3ImWyvPcvvb4vT76CIGxLZ3g/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

没有特别需求可以选择自动分区，大家如果有需要可以自定义分区。

**11、进入正式安装过程**

![img](https://mmbiz.qpic.cn/mmbiz_png/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0COskNdAhYiajEuwFSPRwGOhPpqjKAsO6giaCWNdFjERP3dYS0ETmia8L4Q/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

![img](https://mmbiz.qpic.cn/mmbiz_png/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0Cb6b6WpO8stmxDEpicZp2dgUhH0HzpkPKBXryOcjAVXZic8n3hJlf5JAg/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

**12、安装完成并重启**

![img](https://mmbiz.qpic.cn/mmbiz_png/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0CFk53SsD1lC3WZIwlEogotVC0DHsqYjNaSuJ1BoyLLEP53eV64sNp0Q/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

**13、进入新系统**

![img](https://mmbiz.qpic.cn/mmbiz_png/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0CJZlnkEbLAVc94bqIZJMvvbvLulHk7FhowfibyYUUkbB8MG9dgibUWdwg/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

![img](https://mmbiz.qpic.cn/mmbiz_png/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0CmUuxjGa2uxjK3ZbJrlcMQEfYWndI05bvFibwb8SvnlNVAoVy1atjYow/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

------

# 系统是装好了，但还有几个问题

**问题一：** 虚拟机内Linux系统与外网无法连通

![img](https://mmbiz.qpic.cn/mmbiz_png/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0CH0913sjwqH42bZgPAdcKUrNRlqOOqcXls4m03runObY3AM93xRO7hw/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

**问题二：** 虚拟机内Linux系统与外部宿主机无法连通

比如我这里的物理宿主机的IP地址为：`192.168.31.156`

![img](https://mmbiz.qpic.cn/mmbiz_png/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0CBLpNw3Mich0jZGtviaq74BTRdzyk4wqoDu0k9dYxHk01uFHrE3ibwvKJQ/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

**问题三：** 虚拟机内Linux系统节点与节点之间无法连通（如果装了多个Linux节点的话）

------

# 网络配置（极其重要！）

**1、首先尝试查看虚拟机系统的IP地址**

使用命令`ifconfig`进行查看。我们会发现装好的系统并没有为它设置IP地址。

**2、设置虚拟机与物理宿主机的网络连接**

![img](https://mmbiz.qpic.cn/mmbiz_png/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0CP3axlKcIjkS78eHBPB7xwQysFl2l9AnlvyWqa0CU4pqn7S1DHFzWQg/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

选择**桥接模式**，并选择桥接到物理宿主机的上网网卡即可：

![img](https://mmbiz.qpic.cn/mmbiz_png/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0CiadLk7r2acQyXJq4ngbcFu7Cuq5vqEPTHPBlluD0MOZ83nBKCc0YK6w/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

小伙伴们可以按实际情况进行选择。

**3、为虚拟机配置固定静态IP**

首先使用`dhclient`工具为本机分配一个网络内可用的IP地址：

![img](https://mmbiz.qpic.cn/mmbiz_png/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0CEQTpmPiaianbyOMdFUrUhnxeMhyJAkTaNsFJkK0ia9cAvq0rEUCUBoWJA/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

接下来编辑虚拟机系统网卡配置，将上面分配所得的IP地址配置进去：

使用命令编辑：`vim /etc/sysconfig/network-scripts/ifcfg-ens33`

修改配置如下：

```
TYPE=Ethernet
PROXY_METHOD=none
BROWSER_ONLY=no
BOOTPROTO=static
DEFROUTE=yes
IPV4_FAILURE_FATAL=no
IPV6INIT=yes
IPV6_AUTOCONF=yes
IPV6_DEFROUTE=yes
IPV6_FAILURE_FATAL=no
IPV6_ADDR_GEN_MODE=stable-privacy
NAME=ens33
UUID=824ec4bd-a9ae-4410-8346-17ce7f3dd111
DEVICE=ens33
ONBOOT=yes
IPADDR=192.168.31.21
NETMASK=255.255.255.0
GATEWAY=192.168.31.1
DNS1=119.29.29.29
```

尤其注意下图红色标记部分的配置：

![img](https://mmbiz.qpic.cn/mmbiz_png/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0CjJVWxk57TDaAhp9BMZofDpiaTKpMWLZvsDWvSNyRicqasl3dQuNo0ZCQ/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

编辑完成，重启网络设置即可

```
systemctl restart network.service
```

------

# 检查安装配置结果

**1、检验虚拟机系统网络和外界的连通性**

包括检查和外网的连通、和物理宿主机的连通、以及和兄弟节点（前提是你安装了多个虚拟机系统节点的话）之间的连接

![img](https://mmbiz.qpic.cn/mmbiz_png/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0CZjggIny4iczTFTdapY7GOUQ7WPRNEibcqWpEcmejg11cmYpFUyswY9Zw/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

**2、反向检查物理宿主机和虚拟机系统网络的连接性**

![img](https://mmbiz.qpic.cn/mmbiz_png/xq9PqibkVAzomOC8yrnibPPQeqnCiav4t0C0VOLOtqzQayiaGZsiaYKMVLfNicQqjjIHgDCrwzicEhecm7ppnnEsXSILQ/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

至此，大功告成！