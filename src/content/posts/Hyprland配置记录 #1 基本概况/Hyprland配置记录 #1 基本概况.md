---
title: Hyprland配置记录 #1 基本了解
published: 2025-04-29
description: 简短的Hyprland配置记录
image: https://raw.githubusercontent.com/hyprwm/Hyprland/main/assets/header.svg
tags: [Linux, Wayland, Hyprland]
category: Linux
draft: false
---
## 前言
之前一直使用的是suckless的dwm[^1]，也是一种机缘巧合，突发奇想转到Wayland下试一试，之前一直都是在使用Xorg下的窗口管理器/桌面。  
比较担心的是关于Nvidia驱动的问题，但是已经2025年了，依托社区的贡献，Nvidia显卡在Wayland服务下也可以很好的运作，同时Hyrpland官网Wiki也给出了相对应的专题来辅助配置多显卡/Nvidia显卡在Hyprland中的使用。  
因此在3月底花费了一周左右的时间迁移到了Hyprland，不得不承认的是Hyprland的丝滑程度超出我的预期，在Xorg下我曾经使用picom作为窗口渲染器，但是有时候依旧会有肉眼可见的卡顿，或许是我并未配置好picom的缘故，不过Hyprland的体验使得我很满意。  
关于Xorg下的软件可以通过Xwayland在Wayland服务中运行，这使得很多非Wayland生态的软件亦可在Wayland中运行，除了DPI需要单独设置以适配整体DPI之外，暂时没有遇到什么特别大的问题，当然，Steam在Wayland下的表现对我而言也相当好，包括Proton和Wine，基本满足了我日常生活学习的需要。
关于选择Hyprland的原因，在ArchWiki中，Hyprland被分到了Dynamic(动态)的部分[^2]，虽然与严格意义上的Tiling(平铺)有区别，但是对我而言她可以胜任我以往使用平铺窗口管理器的操作和习惯，为什么不选择Sway？我也不知道（笑  
总之就是在彻底想好选Sway还是Hyprland还是其他Wayland下的窗口管理器之前就已经开始安装Hyprland了（逃  
## 安装Hyprland
在Hyprland的官方Wiki有给出大部分发行版安装Hyprland[^3]，这里可以直接参考官方给的内容，我使用的是ArchLinux，故选用
```sudo pacman -S hyprland```
来安装。  
同样的，Hyprland在AUR上也有git版本，以及包含所有`hypr*`生态的meta版本，当然，通过源代码编译也是可以的。  
在Hyprland的Wiki可以看到一个很有意思的专题，`Preconfigured setups`[^4]，预配置设置，`Preconfigured setups`中则收录部分其他用户配置好的Hyrpland，大部分只需要做少许适配自己的微调就可以使用了。
## Hyprland配置文件
根据Wiki中Configuration的Start页面，Hyprland的配置文件位于`$XDG_CONFIG_HOME/hypr/hyprland.conf`，对于ArchLinux而言，一般位于`~/.config/hypr/`文件夹下[^5]，同时也给出了示例配置文件[hyprland.conf](https://github.com/hyprwm/Hyprland/blob/main/example/hyprland.conf)。  
这份配置文件分为了几个部分
- MONITORS
- MY PROGRAMS
- AUTOSTART
- ENVIRONMENT VARIABLES
- PERMISSIONS
- LOOK AND FEEL
- KEYBINDINGS
- WINDOWS AND WORKSPACES

其中，我们最需要关注的是`KEYBINDINGS`、`ENVIRONMENT`、`AUTOSTART`、`MY PROGRAMS`，这四个分别代表`按键绑定`、`环境变量设置`、`自启动设置`、`自定义应用`，关于这个自定义应用后面在详细解释，剩余的这些部分除去`PERMISSIONS`之外都和外观有关系。  

下一篇将记录关于按键绑定的部分。

[^1]: https://dwm.suckless.org/
[^2]: https://wiki.archlinux.org/title/Wayland#Dynamic
[^3]: https://wiki.hyprland.org/Getting-Started/Installation/
[^4]: https://wiki.hyprland.org/Getting-Started/Preconfigured-setups/
[^5]: https://wiki.hyprland.org/Configuring/Start/
