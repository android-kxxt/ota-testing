# Changelog for Mondrian

## 2023-12-23

- Pacman for Android(PFA) is now included in the build :tada:!
    - Default password for `shell` user is `pacman-for-android`.
    - `shell` is in sudoers by default.
    - The installation happens on first boot. It will take a while.
- The default shell for `adb shell` is now bash from PFA, if it exists.
- Sepolicy fixups for PFA.
- A statically linked bsdtar is now included in the build.

Upstream changes: https://raw.githubusercontent.com/arian-ota/changelog/lineage-20/mondrian.txt

```
* device/xiaomi/mondrian
915af95 mondrian: overlay: Configure power button and fingerprint screen location [Arian]
8f3da08 mondrian: Drop unnecessary vibrator effects [Arian]
b472093 mondrian: Move audio firmware to proper section [Arian]

* device/xiaomi/sm8450-common
48a593c6a sm8450-common: overlay: Enable multiple vibration strength levels support [Michael Bestas]
443b024e0 sm8450-common: modules from mondrian [Arian]

* frameworks/base
b434bd6e7bd8 udfps: Scale coordinates on action down events [Arian]
e1b824686891 udfps: Trigger onFingerDown with regular action down events too [Arian]

* kernel/xiaomi/sm8450
07a8cd610981 input: misc: qcom-hv-haptics: Scale vibration strength on full range [Arian]
32f7bbb12470 fixup! ARM64: configs: Add mondrian config [Arian]
13d04c9d90c1 arm64: Add config option for wl2866d camera [Arian] 
```

## 2023-12-07

- Enable more kernel features such as `POSIX_MQUEUE` and `IP_VS` to make docker work.
- Enable KernelSU.


## 2023-12-06

- All kernel module are OSS. goodix_core.ko and xiaomi_touch.ko are reverse engineered. The OSS version is still a little buggy.
- Enable some basic kernel features, such as `SYSVIPC`, `PID_NS` and `USER_NS`. More is needed for docker.
- SEPolicy modifications for PFA.
- Reserve more space and inode in vendor partition.
- Temporarily disable kernel panic on oops (/proc/sys/kernel/panic_on_oops).
- Temporarily enable CONFIG_MODULE_FORCE_LOAD.
- All builds published now are userdebug builds signed with test keys. I might publish builds signed with my keys in the future.
