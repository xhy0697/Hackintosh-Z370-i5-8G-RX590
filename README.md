
>卖掉了用了两年的XPS15-9560，因为性能实在跟不上，索性卖掉XPS攒了台台式机，正式用性能比较好的黑苹果了。

<img src='https://cos.ap-chengdu.myqcloud.com/tuchuang-1258561688/%E9%BB%91%E8%8B%B9%E6%9E%9C/%E9%BB%91%E8%8B%B9%E6%9E%9C10.14.5.jpg'>


## 配置如下：
- **主板：微星Z370M MORTAR**
- **CPU：i5-8600K**
- **内存：芝奇幻光戟 8G-DDR4 3000**
- **硬盘：三星(SAMSUNG) 970 EVO PLUS 500G NVMe 固态硬盘**
- **显卡：盈通RX590-8G-女装大佬**
- **网卡：博通BCM94360CD**
- **机箱：酷冷至尊Q300P**
- **显示器：DELL U2417H**

## 简介
目前除了蓝牙和WI-FI没有装（台式机没装WI-FI蓝牙卡），icloud三码完美，FACETIME，iCloud，显卡，变频，声卡都完美。

## 如何在有独立显卡的设备下（nVidia）使用macOS14

> 例如本机使用的是GTX1060的显卡，目前在macOS官网上没有办法驱动。

但换一个思路：在有集成显卡的情况下。启动Clover后如果要进入macOS，则使用本机自带的集成显卡（UHD630）可以使用macOS10.14。如果启动CLover后进入Win10，则使用主机上的独立显卡的接口：DP，进入Win10后可使用独立显卡（DP接口）。

如此一来，即便进入macOS10.14使用的是集成显卡，但可以完美正常使用，因为一般也不会在mac下玩游戏，集成显卡足以。这样的操作可能会经常切换显示器接口。但总的来说可以解决升级10.14不能用显卡的问题。

![双显卡切换](https://cos.ap-chengdu.myqcloud.com/tuchuang-1258561688/%E9%BB%91%E8%8B%B9%E6%9E%9C/%E5%8F%8C%E6%98%BE%E5%8D%A1%E5%88%87%E6%8D%A2.jpg)

## 关于网卡、蓝牙

台式机选择的博通的94360CD，说是原生苹果拆机硬件，可以直接免驱。使用之后直接可以蓝牙和Handoff，隔空投送一样完美。

## 更换1060为RX590

开启原生A卡硬件加速-RX590

![硬件加速](https://cos.ap-chengdu.myqcloud.com/tuchuang-1258561688/%E9%BB%91%E8%8B%B9%E6%9E%9C/%E7%A1%AC%E4%BB%B6%E5%8A%A0%E9%80%9F.jpg)

![硬件加速](https://cos.ap-chengdu.myqcloud.com/tuchuang-1258561688/%E9%BB%91%E8%8B%B9%E6%9E%9C/%E7%A1%AC%E4%BB%B6%E5%8A%A0%E9%80%9F2.jpg)


可以在图一里面看到硬解4K视频的时候，核显和独显都参与了解码过程，但CPU的适用率很低。此时显卡解码完美。

## 全新配置macOS 10.15 Catalina

这次更新主要从方法方式上进行更新，相应的驱动也更加完美。CPU原生支持，声卡、NVMe、USB、HDMI音频和显卡都是从主板PCI接口自动识别而来，因此设备设置里的IntelGFX和显卡设置里都**无需**添加相应的仿冒参数（3E9B007），从而UHD630和RX590都是原生PCI生成参数。

![PCI](https://cos.ap-chengdu.myqcloud.com/tuchuang-1258561688/%E9%BB%91%E8%8B%B9%E6%9E%9C/PCI.png)

![UHD630](https://cos.ap-chengdu.myqcloud.com/tuchuang-1258561688/%E9%BB%91%E8%8B%B9%E6%9E%9C/UHD630.png)

![RX590](https://cos.ap-chengdu.myqcloud.com/tuchuang-1258561688/%E9%BB%91%E8%8B%B9%E6%9E%9C/RX590.png)

从图片里可以看到显示器/显卡部分，所有信息都是从PCI设备里自动识别出来的，包括GPU1和GPU2都是自动识别的。

**而且：重点是双显卡都可以正常使用！**

我有两个显示器，分辨率为主1080P，副900P（1440*900）。

***此时独立显卡只连接的是RX590独立显卡，副显示器连接的是主板上的核显UHD630，比如副显示器看直播和视频主显示做自己工作完全不影响而且完美运行，4K硬件加速也都正常。***

***因此此方式的驱动参数设置应该是对于黑苹果来说最完美的配置。***

# 详细介绍可以在我的网站里找到

[vector.today](https://vector.today/)
