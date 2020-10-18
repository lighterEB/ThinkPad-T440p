# ThinkPad-T440p
ThinkPad T440p Hackintosh Catalina (10.15.7) Clover config.plist + kexts
ThinkPad T440p Hackintosh BigSur (11.0 beta10) OpenCore config.plist + kexts

# 更新

* **2020-10-18**:   添加[OpenCore（0.6.2)](https://github.com/acidanthera/OpenCorePkg/releases/tag/0.6.2)引导文件用于安装引导MacOs 11.0（Big Sur beta10），更新[ALCPlugFix](https://github.com/Sniki/ALCPlugFix/releases/tag/v1.7)，在Big Sur下使用方法为：

  ```shell l
  sudo spctl --master-disable
  cd ALCPlugFix
  ./install.sh
  ```

  

* **2020-10-11**：增加alc_fix文件夹，其中install.sh用于修复耳机麦克风二合一插孔，保证3.5mm耳机正常使用。使用方法如下：

  打开终端输入：

  ```bash
  sudo mount -uw /
  killall Finder
  cd alc_fix/
  sudo sh install.sh
  ```

  

# 硬件配置

![image](https://github.com/lighterEB/ThinkPad-T440p/blob/main/t440p-Catalina15.7.png)

CPU：i7-4770HQ （BGA转PGA）

内存：三星 DDR3L-1600MHZ 16G（8G x 2）

硬盘：512G （ssd）+ 512G （HDD）

网卡：DW1560（BCM94352）

显卡：Intel Iris Pro 5200

显示器：1920x1080 分辨率（B140HAN03.2 HW1A 镜面屏）



# 工作状态

* 电源管理/睡眠										    ✅
* 背光调节                                                     ✅
* 电池信息                                                     ✅
* Wi-Fi/接力                                                   ✅
* 内置扬声器/麦克风                                     ✅
* USB接口，摄像头内建                               ✅
* FaceTime/iMessage                                  ✅
* 显卡硬件加速                                              ✅
* DVD光驱                                                      ✅
* 系统自动升级                                               ✅
* 触控板/小红点（全部手势完美支持）       ✅
* 睡眠唤醒正常不会崩溃                                ✅

# 未知问题

* 拓展坞（待测）
* SD卡读卡器（待测，可能无法使用）

# 描述

此仓库为thinkpad t440p 黑苹果 Clover（供MacOs 10.15.x用户使用）以及OpenCore（供MacOs 11 beta 用户使用）理论上支持所有t440p的用户，可以达到99%近乎完美的程度。

# 说明

将系统版本对应的文件夹重命名为EFI拷贝到系统EFI分区使用，请勿将两个EFI文件夹同时放进EFI分区以免产生错误。如果您的bios已经通过刷写解锁CFG Lock，请将

> EFI-OC/OC/config.plist->Kernel->Quirks->AppCpuPmCfgLock<False/>
>
> EFI-OC/OC/config.plist->Kernel->Quirks->AppXcpmCfgLock<False/>

另外，您需要自行添加您的机型相关信息以便能正常使用iCloud、iMessage、FaceTime、Apple Store等功能。
