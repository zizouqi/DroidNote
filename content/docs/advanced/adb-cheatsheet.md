---
title: ADB / Fastboot 常用命令速查
weight: 1
---

## ADB 常用命令

```bash
# 查看已连接设备与状态
adb devices -l

# 重启至正常系统 / Bootloader / Recovery
adb reboot
adb reboot bootloader
adb reboot recovery

# 安装 APK（-r 覆盖安装，-d 允许降级，-t 允许测试包）
adb install -r app.apk

# 列出第三方应用包名
adb shell pm list packages -3

# 仅禁用/启用指定包（比直接 uninstall 更安全，可随时恢复）
adb shell pm disable-user --user 0 com.example.app
adb shell pm enable com.example.app

# 查看当前前台 Activity（定位弹窗/广告来源非常有用）
adb shell dumpsys window | grep -E "mCurrentFocus|mFocusedApp"

# 抓取错误级别日志
adb logcat *:E
```

## Fastboot 常用命令

```bash
# 检查 Fastboot 连接
fastboot devices

# 查看当前活动槽位（A/B 分区设备）
fastboot getvar current-slot

# 临时启动镜像（不写入闪存，测试内核/Recovery 最安全）
fastboot boot init_boot.img

# 刷入 boot 或 init_boot 分区（务必确认当前机型与系统版本完全匹配）
fastboot flash init_boot patched_init_boot.img
```

{{< callout type="warning" >}}
`fastboot flash` 前务必确认设备型号、系统小版本号与目标分区（`boot` 还是 `init_boot`）完全一致，并始终在电脑上保留一份未修改的官方原版镜像用于急救恢复。
{{< /callout >}}
