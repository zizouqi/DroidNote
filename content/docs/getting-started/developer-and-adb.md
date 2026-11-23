---
title: 开发者选项与 ADB 基础配置
weight: 3
---

开启开发者选项并配好电脑端 ADB（Android Debug Bridge），是查看日志、免 Root 授权（如 Shizuku）及排查系统故障的基础能力。

## 安装 Platform Tools

从 Android 官方页面下载最新的 `platform-tools` 压缩包并解压到本地固定目录，然后把该目录加入系统 `PATH`。

{{< tabs >}}

{{< tab name="Windows (PowerShell)" >}}
```powershell
# 验证 adb 是否可用
adb version

# 查看已连接设备
adb devices
```
{{< /tab >}}

{{< tab name="macOS / Linux" >}}
```bash
# 验证 adb 是否可用
adb version

# 查看已连接设备
adb devices
```
{{< /tab >}}

{{< /tabs >}}

## 手机端开启调试

1. 进入 **设置 → 关于本机 → 版本信息**，连续点击 **版本号** 7 次开启开发者模式。
2. 进入 **设置 → 系统与更新 / 其他设置 → 开发者选项**。
3. 开启 **USB 调试**（部分品牌如 OPPO/一加/vivo/小米还需要开启“停用权限监控”或“USB 调试（安全设置）”才能通过 ADB 授权或模拟输入）。
4. 用数据线连接电脑，手机弹窗询问“允许 USB 调试吗？”时，仅在自己信任的电脑上勾选 **一律允许使用这台计算机进行调试**。

{{< callout type="info" >}}
Android 11 及以上版本支持 **无线调试（Wireless Debugging）**，在同一局域网下无需数据线即可通过 `adb pair` 配对连接。日常不用调试时建议关闭 USB 调试与无线调试以降低攻击面。
{{< /callout >}}
