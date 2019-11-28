原来使用`vmware`虚拟机,使用的`NAT`模式,只有自己的主机能连自己本地的虚拟机,感觉不太灵活.

修改为使用桥接模式,这样,虚拟机就相当于一台真实的电脑.同局域网的电脑都可以连接到虚拟机.

修改配置如下:

1. 进入`vmware`的`编辑` -> `虚拟网络编辑器` -> `更改设置` -> 选择`桥接模式`,选择`物理网卡`.
2. 重启虚拟机.
3. 可以手动设置ip或自动获取ip
4. 控制台输入`ifconfig`查看ip
5. 使用`xShell`连接即可.

![](https://github.com/zhaowenxu/java_markdown_doc/blob/master/images/vmware_config.png?raw=true)



**更多修改操作参考**

<https://docs.vmware.com/cn/VMware-Workstation-Pro/12.0/com.vmware.ws.using.doc/GUID-AC956B17-30BA-45F7-9A39-DCCB96B0A713.html> 