[![Build ISO](https://github.com/danyi/SteamOS-holo-for-Danyi/actions/workflows/build.yml/badge.svg)](https://github.com/danyi/SteamOS-holo-for-Danyi/actions/workflows/build.yml)

![image](https://user-images.githubusercontent.com/97450182/167457908-07be1a60-7e86-4bef-b7f0-6bd19efd8b24.png)

# ENGLISH Version
Click [here](https://github.com/theVakhovskeIsTaken/holoiso) to access the English version.

# HoloISO china
这是一个中文本地化的分支计划！
计划将SteamOS 3 (Holo) 从语言到安装进行本地化适配,希望可以让大家更便捷的使用上SteamOS 3 (Holo)


# HoloISO 
SteamOS 3 (Holo) 是一个使用了ArchLinux 构建的linux系统.

***是的, V社宣称,甚至在面包机上SteamOS也能够运行.***


HoloISO项目，试图将Steam Desk的SteamOS Holo改为通用的、可安装的格式。重点在于重新修改Steam客户端、OS本身、Gamescope和用户创建的Deck应用所依赖的专有组件，提供提供接近官方的SteamOS体验(就像运行在Steam Desk上).


点击 [这里](https://t.me/HoloISO) 加入**HoloISO**官方 Telegram更新频道;

点击 [这里](https://steamdeck.community/forums/holoiso.29/) 访问Steam Deck官方社区论坛上的**HoloISO**讨论

**常见问题**

- 这是V社官方的SteamOS吗?
> 不是, 但是已经和官方99%部分是一样的. 原代码和包直接来自Valve，没有经过任何的编辑，ISO是在官方Steam Deck恢复映像上获取的的，从QEMU实例中运行。
- 我下载的ISO无法启动或者说无法引导?
> 目前，只有在使用这些软件制作 [BalenaEtcher](https://www.balena.io/etcher/), [RosaImageWriter](http://wiki.rosalab.ru/en/index.php/ROSA_ImageWriter), [Fedora Media Writer](https://getfedora.org/en/workstation/download/), [Rufus](https://rufus.ie) 块大小为4MB的DD模式的磁盘才能正确引导.


**Working stuff:**
- Bootup
- SteamOS OOBE (Steam Deck UI First Boot Experience)
- Deck UI (separate session)
- Deck UI (-gamepadui)
- ~~TDP/FPS limiting~~ (*0)
- Global FSR
- Shader Pre-Caching
- Switch to Desktop from plasma/to plasma without user interference.
- Valve's exclusive *Vapor* appearance for KDE Plasma
- Steam Deck pacman mirrors
- Cool-looking neofetch?
- System updates

(*0) Disabled for ALL systems due to VERY LOW hardcoded TDP/Clock values, especially for dGPUs.

**Known issues:**
- NVIDIA GPUs are supported after following this procedure:

> Only 10xx+ GPUs are FULLY supported(*1). Although 9xx support exists in drivers, gamescope doesn't launch on it. Choose your GPU type while installing HoloISO. If you encounter any issues, reboot to recovery mode, type `recoveryinit`, connect to network using `nmtui` and install required packages.

(*1) The NVIDIA support is still pretty wonky. GamepadUI will lag, meanwhile games will run fine, session startup is very random too, usually boots in 5/10 of attempts

> Older GPUs won't be supported until drivers are opensourced OR Until they support atomic KMS, accelerated Xwayland, and Vulkan DMA-BUF extensions, they simply cannot function properly with HoloISO.

- Intel GPUs/iGPUs require a Gamescope downgrade in order to boot into Steam Deck session. 

> Choose your GPU type while installing HoloISO. If you encounter any issues, reboot to recovery mode, type `recoveryinit`, connect to network using `nmtui` and install required packages.

Installation process:
-
**Prerequistes:**
- 4GB flash drive
- AMD RX Vega+/APU iGPU; 4xx/5xx, 5xxx/6xxx GPU
or Intel UHD 630+ iGPU or NVIDIA GTX 9xx+ iGPU/GPUs (preferably without Optimus [PRIME])
- UEFI-enabled device
- Disabled secure boot

**Installation types:**
- barebones 
> An OS-only installation, resembles vanilla Arch Linux installation.
- gameonly*
> Steam Deck UI only (AMD GPU only; no desktop), as said, this doesn't ship any DE, and only has the Steam Deck UI installed. 
> ****This part is currently under a renovation.***
- deckperience
> Full SteamOS 3 experience, Includes proper session switching, KDE Plasma + media apps, and Chromium pre-installed.

**Installation:**
- Flash the ISO from [releases](https://github.com/bhaiest/holoiso/releases/latest) or [actions](https://nightly.link/theVakhovskeIsTaken/holoiso/workflows/build/3.0/holoiso) for NVIDIA GPUs using [BalenaEtcher](https://www.balena.io/etcher/), [Rufus](https://rufus.ie) with DD mode, or by typing `sudo dd if=SteamOS.iso of=/dev/sd(your flash drive) bs=4M status=progress oflag=sync`
- Boot into ISO
- Run `holoinstall`
- Enter drive node, starting from, for example, `sda` or `nvme0n1` when asked
- Take your favourite hot beverage, and wait 'till it installs :3

Upon booting, you'll be greeted with Steam Deck's OOBE screen, from where you'll connect to your network, and login to your Steam account, from there, you can exit to KDE Plasma seamlessly by choosing *Switch to desktop* in the power menu, [like so](https://www.youtube.com/watch?v=smfwna2iHho).

Screenshots:
-
![Screenshot_20220508_133916](https://user-images.githubusercontent.com/97450182/167292656-1679e007-4701-4a3c-89ee-2104b5eb12cd.png)
![Screenshot_20220508_133737](https://user-images.githubusercontent.com/97450182/167292672-8bc9032d-4a21-4528-ab7e-b9dbc25a0664.png)
![Screenshot_20220508_133746](https://user-images.githubusercontent.com/97450182/167292722-a68806c1-5768-4790-a8e7-108d7c72bb08.png)
![Screenshot_20220508_133822](https://user-images.githubusercontent.com/97450182/167292731-86fed590-0260-4c5e-ac13-05d284b5fd24.png)
![Screenshot_20220508_134038](https://user-images.githubusercontent.com/97450182/167292734-90036b5f-2571-438e-8951-8d731cd4ae93.png)
![Screenshot_20220508_134051](https://user-images.githubusercontent.com/97450182/167292738-a70d266f-814d-4352-8d38-b920ae3f3381.png)

Credits:
-
(Too much people xD, to be filled later!!!)

Notes:
-

This configuration includes Valve's pacman.conf repositories, `holoinstall` script and `holoinstall` post-installation binaries.

This configuration builds a *releng-based ISO*, which is the default Arch Linux redistribution flavor.

Building the ISO:
-
Trigger the build by executing:
```
pacman -Sy archiso
git clone https://github.com/bhaiest/holoiso/
sudo mkarchiso -v holoiso
```
Once it ends, your ISO will be available in the `out` folder.

