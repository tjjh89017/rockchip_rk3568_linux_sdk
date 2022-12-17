# Photonicat with OpenWrt official image

Some patch from photonicat original github repo

# build 

- Ubuntu 20.04

```
sudo apt update
sudo apt install build-essential flex bison genext2fs \
    ccache ecj fastjar file g++ gawk gettext git \
    java-propose-classpath libelf-dev libncurses5-dev \
    libncursesw5-dev libssl-dev python2.7-dev python3 \
    unzip wget python3-distutils python3-setuptools python3-dev \
    rsync subversion swig time xsltproc zlib1g-dev \
    device-tree-compiler gcc-aarch64-linux-gnu bc lz4 python
```

```
git clone https://github.com/tjjh89017/rockchip_rk3568_linux_sdk -b openwrt --single-branch rk3568-linux-sdk
cd rk3568-linux-sdk
git submodule update --init
./rk3568-config-photonicat-openwrt.sh
export CROSS_COMPILE=aarch64-linux-gnu-
./build.sh

cd openwrt
make menuconfig ARCH=aarch64
./build.sh

# ipk 
./openwrt/staging_dir/packages/armvirt/
```

Ref: https://photonicat.com/wiki/Photonicat_%E7%BC%96%E8%AF%91_OpenWRT,_Debian
