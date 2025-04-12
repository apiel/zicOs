# zicOs Buildroot

What’s Inside:
- `configs/zicbox_defconfig`: starter config (CM4, SSH, Wi-Fi, PulseAudio, opkg)
- `board/zicbox/overlay/`: folder for system overlays (includes autostart script for `/opt/zicBox/pixel`)

Install dependencies:

```sh
sudo apt update
sudo apt install build-essential git cpio rsync unzip bc
```

Clone it:

```sh
git clone --recursive https://github.com/apiel/zicOs.git
cd zicOs
```

> **Note:** If the repository has already been cloned but submodules are missing, run the following command to pull them:
>
> ```sh
> git submodule update --init
> ```

Build it:

```sh
cd buildroot
make BR2_DEFCONFIG=../zicbox_defconfig defconfig
make
```

Flash `output/images/sdcard.img` to your SD card.