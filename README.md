# Swap and Memory Tuning (lite)

Free subset. The 2G disk-swap sysctl file and a short note on the two knobs. The full pack adds the 1G zram profile, the 4G profile, the read-only reporter, and the sizing rules.

## English

### Deliverables

- `deliverables/99-swap-tune.conf` — 2G VPS, disk swap file, `vm.swappiness = 10`, `vm.vfs_cache_pressure = 50`

`vm.swappiness` is a weight from 0 to 200, default 60. 10 keeps a disk swap quiet until the host is tight. It is the wrong value for a zram-only 1G host.

`vm.vfs_cache_pressure` defaults to 100. 50 keeps dentries and inodes a little longer. Do not set 0.

This file does not create the swap file. Copy it to `/etc/sysctl.d/99-swap-tune.conf` only after you have a 2G swap file and you have read the numbers.

```bash
grep -E '^[a-z]' deliverables/99-swap-tune.conf
```

The full guide covers zram versus a file, 384M zram on 1G, a 2G file on 4G, and `check_swap.sh`.

Full version: GUMROAD_URL

## 中文

免费子集：2G 磁盘交换用的 sysctl，外加两个参数的短说明。完整版另有 1G 的 zram 档、4G 档、只读检查脚本和容量规则。

### 交付物

- `deliverables/99-swap-tune.conf` — 2G VPS，磁盘交换文件，`vm.swappiness = 10`，`vm.vfs_cache_pressure = 50`

`vm.swappiness` 是 0 到 200 的权重，默认 60。10 让磁盘交换在内存还够时保持安静。只用 zram 的 1G 机器不该用这个值。

`vm.vfs_cache_pressure` 默认 100。50 会把目录项和 inode 多留一会儿。不要设成 0。

这个文件不会创建交换文件。先有 2G 交换文件，并看过这些数值，再拷到 `/etc/sysctl.d/99-swap-tune.conf`。

完整版说明 zram 和文件交换的差别、1G 上 384M zram、4G 上 2G 文件，以及 `check_swap.sh`。

Full version: GUMROAD_URL

## Delivery time / 交付时间

Delivery time: instant download after purchase
