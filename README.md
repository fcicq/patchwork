# fcicq's patchwork
patch (including others' work) for opensource projects.

## 4.14 patches by me
* lz4-zram/zswap Use lz4 for zram/zswap
* memfd-noexec make memfd_create safer by nodev/noexec/nosuid
* proc-hidepid use hidepid=2 by default
* kconfig-x86-removecompression reduce kernel size
* limit-tiocsti disable ioctl TIOCSTI unless CAP_SYS_ADMIN, prevent some sandbox escape
* ptrace-allow-poke-only-for-admin disable ptrace PTRACE_POKETEXT/PTRACE_POKEDATA unless CAP_SYS_ADMIN
* proc-pid-net-perm deny /proc/net access unless CAP_NET_ADMIN
* v2-protect-proc-pid-ns deny /proc/pid/ns access unless CAP_SYS_ADMIN
* v2-fs-exec-root-ro deny exec world writable binary under CAP_SYS_ADMIN or by kthread, the executable must be owned by root
* disable-unix-socket-ebpf disable SO_ATTACH_BPF / SO_ATTACH_REUSEPORT_EBPF for unix socket.  
Note: sadly we cant disable sk_peer_cred usage, will break systemd.

* clang-sched-core-warning (clang only) fix warning: use of logical '&&' with constant operand
* v2-link-warning-cgroup-clang (clang only) fix struct cgroup warning, see also https://lkml.org/lkml/2017/10/17/66  
warning: field 'cgrp' with variable sized type 'struct cgroup' not at the end of a struct  
     or class is a GNU extension \[-Wgnu-variable-sized-type-not-at-end\]

## 4.14 patches ported by me
* 20180404-bvt Borrowed Virtual Time for 4.14, original for 3.5 from https://gist.github.com/leverich/5913713
* altsyscall-v2 CHROMIUM: x86: create alt-syscall infrastructure from chromiumos kernel.  
removed nr_syscall, adapted for kpti (required after "x86/entry/64: Remove the SYSCALL64 fast path" applied).

## picked from mainline (4.14+)
* 9934049 mm,page_alloc: don't call \_\_node_reclaim() without scoped allocation constraints.
* 10027975 mm: don't warn about allocations which stall for too long
* 10122749 sched: Only immediately migrate tasks due to interrupts if prev and target CPUs share cache
* 10292559 mm: Allow to kill tasks doing pcpu_alloc() and waiting for pcpu_balance_workfn()
* 10376507 sched/core: Don't schedule threads on pre-empted vcpus
* (upstream 9092c71b) mm: use sc->priority for slab shrink targets

## picked from random sources
* 9249919 sysctl_perf_event_paranoid = 3, disallow all unpriv perf event use
* 10388171,10393297 (fixed) crashes/hung tasks with z3pool under memory pressure (10347561 included in 4.14 mainline)
* 10413763 rcu: Speed up calling of RCU tasks callbacks

## known rejected by upstream maintainer
* 8151021 sysctl: allow CLONE_NEWUSER to be disabled
* 1776151 devtmpfs: mount with noexec and nosuid (Note: systemd mounts with nosuid by default, noexec may break some app)
* 2212521 tcp: sysctl to disable TCP simultaneous connect
* 79014 Make INET_LHTABLE_SIZE a compile-time tunable

## other
* bugzilla-194091-lld-rebased fix arch/x86/realmode/rm/header.o is incompatible with elf_x86_64 for llvm lld  
from https://bugzilla.kernel.org/show_bug.cgi?id=194091
* 10283019 vhost: fix vhost ioctl signature to build with clang
* 10418483 x86/paravirt: Mark native_save_fl() with \_\_nostackprotector attribute (requires clang-\_\_nostackprotector-definition)
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
