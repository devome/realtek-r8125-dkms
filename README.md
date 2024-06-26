## 这是什么

RealTek R8125B 网卡驱动的 DKMS 版本，启用 TX 多队列，启用 RSS，禁用 ASPM。

## 适用对象

适用于 Debian 和基于 Debian 的发行版。

## 如何使用

需要先安装以下两个包：

- `dkms`

- 内核的`headers`文件，比如 Debian 是`linux-headers-amd64`这个包，Proxmox VE 是`proxmox-default-headers`这个包（8.0.3+），其他发行版类似。

提供一个 Proxmox VE 安装本驱动的教程：https://evine.win/p/pve-install-realtek-8125-driver/

## 如何自己编译

直接使用 [makedeb](https://docs.makedeb.org/) 来构建安装包，简单方便。先安装 [makedeb](https://docs.makedeb.org/)，然后在本仓库根目录下运行以下命令即可编译产生`realtek-r8125-dkms_<version>_amd64.deb`。

```shell
makedeb
```

注：现在RealTEK针对下载驱动启用了验证码验证，所以 [makedeb](https://docs.makedeb.org/) 无法自动下载RealTEK的驱动源码压缩包，这时，你需要自行前往 [官网](https://www.realtek.com/en/component/zoo/category/network-interface-controllers-10-100-1000m-gigabit-ethernet-pci-express-software) 将 2.5G Ethernet LINUX driver r8125 驱动手动下载到仓库根目录，然后再运行上述命令。
