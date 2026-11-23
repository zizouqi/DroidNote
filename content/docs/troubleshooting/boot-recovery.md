---
title: 变砖自救与模块冲突恢复
weight: 2
---

如果设备在安装系统更新、刷入模块或修改系统文件后卡在开机动画（Bootloop），请保持冷静，不要急着盲目清空全部数据（`Format Data`）。

## 分级恢复步骤

{{% steps %}}

### 尝试进入安全模式或等待自动回滚

- 长按电源键强制重启，在进入开机动画阶段尝试连续多次重启或按住“音量下”触发系统安全模式；现代 Root 管理器（如 Magisk / KernelSU）在检测到安全模式时会自动禁用所有模块。
- 对于 A/B 分区设备，部分系统在连续启动失败数次后会自动回退到上一个可用槽位（slot）。

### 通过 ADB 移除冲突模块（若开机阶段已启 ADB）

在系统尚可响应 ADB 时，可执行安全模式清理命令（具体路径以所用管理器文档为准），例如 Magisk：

```bash
adb wait-for-device shell magisk --remove-modules
```

### 通过 Fastboot 刷回官方原版镜像

若无法进入系统但能进入 Bootloader（Fastboot 模式），在电脑端使用事先备份好的**同版本**官方 `boot.img` / `init_boot.img` 临时启动或刷回：

```bash
fastboot flash init_boot stock_init_boot.img
fastboot reboot
```

### 厂商官方线刷包救砖

若系统关键分区损坏且 Fastboot 单刷原版镜像仍无法启动，使用对应机型的官方全量线刷工具或官方 Recovery 刷入全量包修复系统分区。

{{% /steps %}}
