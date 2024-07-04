---
title: "Linux 使用过程中的一些问题及解决方案"
date: 2024-07-01 00:00:00 +0800
tags: [Linux]
categories: Linux调优
---

## 在不同distro中，`pacman -Syu` 的提示不一样

> 实例：
>
> ```bash
> # Arch Linux by default
> ~> sudo pacman -Syu
> :: Synchronizing package databases...
>  core is up to date
>  extra is up to date
>  multilib is up to date
>  archlinuxcn                          1943.4 KiB  3.31 MiB/s 00:01 [####################################] 100%
> :: Starting full system upgrade...
> resolving dependencies...
> looking for conflicting packages...
> 
> Packages (24) aha-0.5.1-3  ca-certificates-mozilla-3.101.1-1 ...
> 
> Total Download Size:    83.24 MiB
> Total Installed Size:  320.17 MiB
> Net Upgrade Size:        1.34 MiB
> 
> :: Proceed with installation? [Y/n] 
> 
> # endeavour OS by default
> 
> ~> sudo pacman -Syu
> :: Synchronizing package databases...
>  core is up to date
>  extra is up to date
>  multilib is up to date
>  archlinuxcn is up to date
> :: Starting full system upgrade...
> resolving dependencies...
> looking for conflicting packages...
> 
> Package (24)                     Old Version     New Version     Net Change  Download Size
> 
> extra/aha                        0.5.1-2         0.5.1-3           0.00 MiB       0.01 MiB
> core/ca-certificates-mozilla     3.101-1         3.101.1-1         0.00 MiB       0.37 MiB
> 
> Total Download Size:    83.24 MiB
> Total Installed Size:  320.17 MiB
> Net Upgrade Size:        1.34 MiB
> 
> :: Proceed with installation? [Y/n]
>  ```

前者是默认的，后者是在`/etc/pacman.conf`中将注释了的`VerbosePkgLists`解除注释后的效果。