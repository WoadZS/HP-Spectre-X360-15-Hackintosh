# HP-Spectre-X360-15-Hackintosh
EFI files for HP Spectre X360 15-bl112dx

## macOS版本 Version
MacOS Catalina 10.15.2
Clover Version v5103
## 配置 Specs
|配置 Parts|参数 Details
|:---:|:---:|
电脑型号 Computer Model | HP Spectre X360 15-bl112dx
CPU | i7-8550U
显卡 Graphics card | UHD620<br>~~NVIDIA MX150~~ 已禁用（Disabled）
声卡 Audio | Realtek ALC295 (Injected ID:14)
内建显示器 Display | 4K 触摸屏 Touch
网卡蓝牙 WiFi | DW1560
内存 RAM | 8G * 2
硬盘 SSD | 海康威视 Hikvision C2000 Pro 512GB
BIOS | v.40

## 更新历史 Changelog
2020.1.21
1. 变更FakeSMC为VirtualSMC，并修改配套Kexts Change FakeSMC to VirtualSMC, as well as relative kexts and efi
2. 成功驱动触摸屏 Touch Screen available now
3. 变更触摸板驱动为魔改版ApplePS2SmartTouchPad Change touchpad kexts VoodooPS2Controller to MOD ApplePS2SmartTouchPad.kext
4. 更新了Clover到5103 Upgrade Clover to 5103
5. 修改了部分DSDT和SSDT Modified DSDT and SSDT
6. 升级了驱动到截止2020年1月21日最新的版本 Upgrade Kexts to the latest version(2020.1.21)
7. 附带了放置在LE中的Kexts Attached kexts located in /Library/Extensions
8. 升级系统至MacOS Catalina 10.15.2 Upgrade MacOS version to acOS Catalina 10.15.2

## 正常工作部件 Working
* CPU 变频 Frequency   
* 4K显示及硬件加速 4K Display & Hardware Acceleration   
* 无线功能 WiFi  
* HDMI接口输出 HDMI Port Output  
* 触摸板 Trackpad  
* 声卡 Audio  
* 睡眠 Sleep 
* 触摸屏 Touch Screen

## 已知无法正常工作的部件和问题 Known Issues
* Type-C 转 HDMI 输出会导致重启（HDMI接口可正常输出） type-c external display will cause reboot(HDMI Port works well)
* 蓝牙 无法确认是否是卡坏了 Bluetooth, not sure the card is fully fuctional.
* FN小太阳亮度调整（设置可以调整） FN key cannot adjust brightness(You can adjust that in system setting)
* 有一个Type-C接口只能充电无法进行数据传输 One of the Type-C Port can only be used for charging, instead of data transfering;
* 雷电3 无法工作 thunderbolt 3 is not working
* 读卡器 无法工作 SDcard reader is not working