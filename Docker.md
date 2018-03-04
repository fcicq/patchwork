# Docker 

Minimum Kernel Config Checker https://github.com/moby/moby/blob/master/contrib/check-config.sh

# Security

## Seccomp-bpf Filter
Alternate method: alt-syscall table from chromium https://gist.github.com/fcicq/1424f74bb1d26628d8af9f3d7a6df47f

## AppArmor

## Linux Capabilities

# Storage
ZFS?  
AUFS + ext4  
overlayfs + ext4  
btrfs

# cgroups & cgroup subsystems

## CGroup v2 issues (required for cgroup writeback)

Filesystem support: wbc_init_bio & wbc_account_io
