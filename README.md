# fcicq's patchwork
patch (including others' work) for opensource projects.

# 4.14 patches by me
* lz4-zram/zswap Use lz4 for zram/zswap
* memfd-noexec make memfd_create safer by nodev/noexec/nosuid
* proc-hidepid use hidepid=2 by default
* kconfig-x86-removecompression reduce kernel size

# 4.14 patches ported
* 20180404-bvt Borrowed Virtual Time for 4.14, original for 3.5 from https://gist.github.com/leverich/5913713

# other patches picked
* 9934049 mm,page_alloc: don't call \_\_node_reclaim() without scoped allocation constraints.
* 10027975 mm: don't warn about allocations which stall for too long
* 1776151 devtmpfs: mount with noexec and nosuid (Note: systemd mounts with nosuid by default, noexec may break some app)
* 2212521 tcp: sysctl to disable TCP simultaneous connect
* 79014 Make INET_LHTABLE_SIZE a compile-time tunable

# Resources
## Android Kernel
https://android.googlesource.com/kernel/common/+/android-4.14 [(log)](https://android.googlesource.com/kernel/common/+log/android-4.14)  
https://android.googlesource.com/kernel/common/+/android-4.9 [(log)](https://android.googlesource.com/kernel/common/+log/android-4.9)  
https://android.googlesource.com/kernel/common/+/android-4.4 [(log)](https://android.googlesource.com/kernel/common/+log/android-4.4)  
https://android.googlesource.com/kernel/common/+/android-3.18 [(log)](https://android.googlesource.com/kernel/common/+log/android-3.18)  

(TODO: describe important modules/subsystems which are not in mainline.)

## Patchwork
[netdev](https://patchwork.ozlabs.org/project/netdev/list/?state=%2a)  
[linux-fsdevel](https://patchwork.kernel.org/project/linux-fsdevel/list/?state=%2a)  

## DKMS
(TODO)

## Uncategorized
[LWN Kernel Index](https://lwn.net/Kernel/Index/)  
[LWN Kernel Patches](https://lwn.net/Kernel/Patches)  
https://kernelnewbies.org/LinuxChanges  
