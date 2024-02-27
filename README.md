Required packages
```
sudo apt-get update && sudo apt-get install -y git lzop build-essential gcc bc libncurses5-dev libc6-i386 lib32stdc++6 zlib1g:i386 p7zip-full p7zip-rar
```
Toolchain 6.3.1
```
sudo mkdir -p /opt/toolchains && wget https://releases.linaro.org/components/toolchain/binaries/6.3-2017.05/aarch64-linux-gnu/gcc-linaro-6.3.1-2017.05-x86_64_aarch64-linux-gnu.tar.xz && sudo tar Jxvf gcc-linaro-6.3.1-2017.05-x86_64_aarch64-linux-gnu.tar.xz -C /opt/toolchains/
```
Add lines below to ~/.bashrc
```
export ARCH=arm64
export CROSS_COMPILE=aarch64-linux-gnu-
export PATH=/opt/toolchains/gcc-linaro-6.3.1-2017.05-x86_64_aarch64-linux-gnu/bin/:$PATH
```

build:
```
make ARCH=arm64 rk3566_optimized_linux_defconfig && make ARCH=arm64 KERNEL_DTS=rk3566 KERNEL_CONFIG=rk3566_optimized_linux_defconfig
```

wifi and bt; see wifibt folder
