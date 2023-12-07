# Changelog for Mondrian

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
