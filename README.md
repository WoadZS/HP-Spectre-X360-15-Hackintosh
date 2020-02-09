# HP-Spectre-X360-15-Hackintosh
EFI files for HP Spectre X360 15-bl112dx

## macOS版本 Version
MacOS Catalina 10.15.3  
Clover Version v5103
## 配置 Specs
|配置 Parts|参数 Details
|:---:|:---:|
电脑型号 Computer Model | HP Spectre X360 15-bl112dx
CPU | i7-8550U
显卡 Graphics card | UHD620<br>~~NVIDIA MX150~~ 已禁用（Disabled）
声卡 Audio | Realtek ALC295 (Injected ID:3)
内建显示器 Display | 4K 触摸屏 Touch
网卡蓝牙 WiFi | DW1560
内存 RAM | 8G * 2
硬盘 SSD | 海康威视 Hikvision C2000 Pro 512GB
BIOS | v.40

## 更新历史 Changelog
### 2020.2.9  
1. 打上IRQ补丁已解决部分音频问题<br>Apply IRQ Fix in DSDT to fix some minor audio issues.
2. 取消`-v`模式并缩短Clover等待时间<br>Cancel `-v` mode and reduce the wait time before OS booting.  
3. 更新AirportBrcmFixup.kext并删除不使用的kext<br>Update AirportBrcmFixup.kext and delete useless kexts.  
### 2020.2.5  
1. 禁用触摸屏，因为更新MacOS系统后触摸屏和触摸板有冲突，触屏会取代触摸板工作，而ApplePS2SmartTouchPad并不能提供良好的防误触功能<br>Disabled TouchScreen cause only Touchscreen can working after upgrading macOS, you can still use ApplePS2SmartTouchPad to activte touchpad but with loss of many functions.
2. 再次修正DSDT，解决关机重启问题<br>Fix DSDT to solve reboot after shotdown
### 2020.2.3  
1. 变更内存补丁为AptioMemoryFix.efi和EmuVariableUefi.efi以修复关机后自动重启的问题<br>Change Memory Fix EFI files to AptioMemoryFix and EmuVariableUefi to solve shutdown = reboot
2. 变更声卡注入ID为3<br>Change Audio Injected ID to 3 from 14
3. 升级系统至MacOS Catalina 10.15.3<br>Upgrade MacOS version to acOS Catalina 10.15.3

### 2020.1.21
1. 变更FakeSMC为VirtualSMC，并修改配套Kexts<br>Change FakeSMC to VirtualSMC, as well as relative kexts and efi
2. 成功驱动触摸屏<br>Touch Screen available now
3. 变更触摸板驱动为魔改版ApplePS2SmartTouchPad<br>Change touchpad kexts VoodooPS2Controller to MOD ApplePS2SmartTouchPad.kext
4. 更新了Clover到5103<br>Upgrade Clover to 5103
5. 修改了部分DSDT和SSDT<br>Modified DSDT and SSDT
6. 升级了驱动到截止2020年1月21日最新的版本<br>Upgrade Kexts to the latest version(2020.1.21)
7. 附带了放置在LE中的Kexts<br>Attached kexts located in /Library/Extensions
8. 升级系统至MacOS Catalina 10.15.2<br>Upgrade MacOS version to acOS Catalina 10.15.2

## 正常工作部件 Working
* CPU 变频 Frequency   
* 4K显示及硬件加速 4K Display & Hardware Acceleration   
* 无线功能 WiFi  
* HDMI接口输出 HDMI Port Output  
* 触摸板 Trackpad  
* 声卡 Audio  
* 睡眠 Sleep 
* ~~触摸屏 Touch Screen~~ 将VoodooI2CHID.kext放到LE里面就能启用，但会导致触摸板失效<br>You can put VoodooI2CHID.kext back in to LE to enable that, but you will lose touchpad
* FN 小太阳亮度调整<br>FN key support brightness adjust.

## 已知无法正常工作的部件和问题 Known Issues
* Type-C 转 HDMI 输出会导致重启（HDMI接口可正常输出）<br>Type-c external display will cause reboot(HDMI Port works well)
* 蓝牙 无法确认是否是卡坏了<br>Bluetooth, not sure the card is fully fuctional.
* 有一个Type-C接口只能充电无法进行数据传输<br>One of the Type-C Port can only be used for charging, instead of data transfering;
* 雷电3 无法工作<br>Thunderbolt 3 is not working
* 读卡器 无法工作<br>SDcard reader is not working
