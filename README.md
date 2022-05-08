# tuya-BK7231N

大家好，最近拿到tuya同学寄过来的两片板子，周末有空玩一下。

# Wi-Fi&BLE SoC NANO主控板（BK7231N）

你们肯定没想到，这是一个既能支持wifi又能支持BLE的主控板，主控板用的是博通的芯片BK7231N。

涂鸦的官网主控板介绍

![https://developer.tuya.com/cn/docs/iot/tuya-sandwich-wifi-and-ble-soc-board-BK7231N?id=Kao72e6net3bs](https://developer.tuya.com/cn/docs/iot/tuya-sandwich-wifi-and-ble-soc-board-BK7231N?id=Kao72e6net3bs)

官网宣传图片

![image](https://user-images.githubusercontent.com/11375905/167281304-aeda7569-ae7f-47ea-9c2b-7dcd92ce785d.png)


接上电源开机的照片

![24d182c21d42a1922be4f04d07d7267](https://user-images.githubusercontent.com/11375905/167281271-02c2d7fd-8eb8-4b42-a5bc-7f714f0a2213.jpg)

## 博通BK7231N 介绍

芯片官方介绍链接

![http://www.bekencorp.com/index/goods/detail/cid/39.html](http://www.bekencorp.com/index/goods/detail/cid/39.html)
 
 
![image](https://user-images.githubusercontent.com/11375905/167281755-5ed29190-d50e-4ff4-b1b0-677633135b06.png)

ARM9是很经典的应用了。

# SDK介绍

SDK 是从tuya官方直接以压缩包的形式发给我的，因为涉及商业内容，我不能直接把SDK源码全部开源，想拿到SDK代码的可以联系文末的同学。

## SDK 编译方式

`./build_app.sh apps/tuya_bk7231n_pet_feed_demo/ tuya_bk7231n_pet_feed_demo 0.0.0.1`

这个SDK主打的是宠物喂养，里面有一个demo是用来实现宠物喂养相关的示例代码。

我记得我们当时做宠物猫厕所的时候，我们用的是乐鑫的ESP32,这也是一个双模WIFI、BLE模组，因为是使用模组，从外观上看ESP32更大一些，博通的这个更偏小一些。

编译结束后会提示编译成功

```C
time: 0.97s
Good bye!
End Combined
generate ota file
sw_version:0.0.0.1
tuya_bk7231n_pet_feed_demo_0.0.0.1.rbl file_size:0x962d0
tuya_bk7231n_pet_feed_demo_0.0.0.1.rbl sum:0x4ad2931
header_sum:0x58f
ug_file size:
615152
/mmt/tuya/ty_iot_pet_app_sdk_bk7231n_0.0.2-beta.20/platforms/bk7231n/bk7231n_os/tools/generate
*************************************************************************
*************************************************************************
*************************************************************************
*********************tuya_bk7231n_pet_feed_demo_0.0.0.1.bin********************
*************************************************************************
**********************COMPILE SUCCESS************************************
*************************************************************************
not is ci build
```

并在对应的文件夹下面生成编译产物

![image](https://user-images.githubusercontent.com/11375905/167282404-01ebd8a6-6867-42aa-84f2-3fd518d18060.png)

* QIO是生产固件，生产时下载
* UA是用户固件，本地调试用原厂工具烧录时使用
* UG是升级固件

## 烧录文件
* 点击烧录软件的烧录按钮
* 按下工程模块的复位按键，然后会自动进行烧录

![录制_2022_05_08_17_45_33_548](https://user-images.githubusercontent.com/11375905/167290788-3ead6885-336a-410f-b9be-1da8e58ae238.gif)


# 参考

https://www.cnblogs.com/dongxiaodong/p/15674465.html

