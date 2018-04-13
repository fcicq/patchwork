# fcicq's patchwork
patch (including others' work) for opensource projects.

## 4.14 patches by me
* lz4-zram/zswap Use lz4 for zram/zswap
* memfd-noexec make memfd_create safer by nodev/noexec/nosuid
* proc-hidepid use hidepid=2 by default
* kconfig-x86-removecompression reduce kernel size
* proc-pid-net-perm deny /proc/net access unless CAP_NET_ADMIN

* clang-sched-core-warning (clang only) fix warning: use of logical '&&' with constant operand
* kaslr-link-warning-cgroup (clang only) fix struct cgroup warning, see also https://lkml.org/lkml/2017/10/17/66  
warning: field 'cgrp' with variable sized type 'struct cgroup' not at the end of a struct  
     or class is a GNU extension \[-Wgnu-variable-sized-type-not-at-end\]

## 4.14 patches ported by me
* 20180404-bvt Borrowed Virtual Time for 4.14, original for 3.5 from https://gist.github.com/leverich/5913713

## picked from mainline (4.14+)
* 9934049 mm,page_alloc: don't call \_\_node_reclaim() without scoped allocation constraints.
* 10027975 mm: don't warn about allocations which stall for too long
* 10122749 sched: Only immediately migrate tasks due to interrupts if prev and target CPUs share cache

## known rejected by upstream maintainer
* 1776151 devtmpfs: mount with noexec and nosuid (Note: systemd mounts with nosuid by default, noexec may break some app)
* 2212521 tcp: sysctl to disable TCP simultaneous connect
* 79014 Make INET_LHTABLE_SIZE a compile-time tunable

## other
* bugzilla-194091-lld-rebased fix arch/x86/realmode/rm/header.o is incompatible with elf_x86_64 for llvm lld  
from https://bugzilla.kernel.org/show_bug.cgi?id=194091
* clearlinux-spinfaster from clear linux, tweak rwsem owner spinning a bit

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
