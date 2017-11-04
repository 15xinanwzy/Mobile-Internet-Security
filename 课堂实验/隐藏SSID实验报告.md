# 课内实验——隐藏SSID
> 说明：由于课堂抓包时没有加--beacons参数导致抓到的包不完整，因此实验所用的数据包是拷贝同学的
### 方法1.手工发现隐藏SSID：
在wireless traffic中找到SSID为全0的数据包，展开条目寻找到连接过它的终端MAC地址,选择收到回复的Probe response的其中一个MAC地址进行过滤。其中第三个SSID需要经过转码，过程如图所示：

* 1.cap

![](https://raw.githubusercontent.com/15xinanwzy/Mobile-Internet-Security/master/%E8%AF%BE%E5%A0%82%E5%AE%9E%E9%AA%8C/hidden-ssid%20Images/phpWireshark1-1.png)

![](https://raw.githubusercontent.com/15xinanwzy/Mobile-Internet-Security/master/%E8%AF%BE%E5%A0%82%E5%AE%9E%E9%AA%8C/hidden-ssid%20Images/phpWireshark1-2.png)

第一个SSID为：uc4nuup

* 2.cap

![](https://raw.githubusercontent.com/15xinanwzy/Mobile-Internet-Security/master/%E8%AF%BE%E5%A0%82%E5%AE%9E%E9%AA%8C/hidden-ssid%20Images/phpWireshark2-1.png)

![](https://raw.githubusercontent.com/15xinanwzy/Mobile-Internet-Security/master/%E8%AF%BE%E5%A0%82%E5%AE%9E%E9%AA%8C/hidden-ssid%20Images/phpWireshark2-2.png)

第二个SSID为：<length:  13>

* 3.cap

![](https://raw.githubusercontent.com/15xinanwzy/Mobile-Internet-Security/master/%E8%AF%BE%E5%A0%82%E5%AE%9E%E9%AA%8C/hidden-ssid%20Images/phpWireshark3-1.png)

![](https://raw.githubusercontent.com/15xinanwzy/Mobile-Internet-Security/master/%E8%AF%BE%E5%A0%82%E5%AE%9E%E9%AA%8C/hidden-ssid%20Images/phpWireshark3-2.png)

在终端用PHP进行转码：

![](https://raw.githubusercontent.com/15xinanwzy/Mobile-Internet-Security/master/%E8%AF%BE%E5%A0%82%E5%AE%9E%E9%AA%8C/hidden-ssid%20Images/phpDecode3.png)

第三个SSID为：你们期待的中文SSID来了

### 方法2.使用python程序运行找出隐藏SSID：
* 代码：

[https://github.com/15xinanwzy/Mobile-Internet-Security/blob/master/%E8%AF%BE%E5%A0%82%E5%AE%9E%E9%AA%8C/hidden-ssid.py](https://github.com/15xinanwzy/Mobile-Internet-Security/blob/master/%E8%AF%BE%E5%A0%82%E5%AE%9E%E9%AA%8C/hidden-ssid.py)

* 运行结果：

![](https://raw.githubusercontent.com/15xinanwzy/Mobile-Internet-Security/master/%E8%AF%BE%E5%A0%82%E5%AE%9E%E9%AA%8C/hidden-ssid%20Images/hiddenSSID123.png)