# KaiwetLab

KaiwetLab 是面向 macOS 的 USB/蓝牙测试设备管理与数据分析工具，支持实时遥测、曲线记录、PD 报文分析和设备固件升级。

> 此仓库用于发布编译版本和应用更新元数据，不包含 KaiwetLab 源代码。

## 主要功能

- 连接 WITRN K2 系列、POWER-Z KM003C 及兼容的 WITRN 蓝牙风扇设备
- 实时显示电压、电流、功率、电量等数据，并绘制可缩放曲线
- 记录、导入和导出 CSV/数据库曲线数据
- USB PD 报文解析与导出
- 设备固件升级及型号兼容性检查
- 中英文界面
- 通过 Sparkle 2 自动检查和安装签名更新

## 系统要求

- macOS 14.0 或更高版本
- Apple Silicon Mac（仅支持 `arm64`）
- 使用 USB 设备时，需要允许应用访问相应设备
- 使用蓝牙风扇功能时，需要授予蓝牙权限

Intel Mac（`x86_64`）不受支持。

## 下载与安装

前往 [Releases](https://github.com/KaiwetN/KaiwetLab/releases/latest) 下载最新版。当前版本可直接下载：

- [KaiwetLab 1.1.0 arm64 DMG](https://github.com/KaiwetN/KaiwetLab/releases/download/v1.1.0/KaiwetLab-1.1.0-arm64.dmg)

打开 DMG 后，将 `KaiwetLab.app` 拖到“应用程序”文件夹。

### 首次启动

当前版本采用 ad-hoc 签名并启用了 Hardened Runtime，未经过 Apple 公证。macOS 可能提示无法验证开发者：

1. 在 Finder 中右键 `KaiwetLab.app`，选择“打开”。
2. 如果仍被阻止，打开“系统设置 → 隐私与安全性”。
3. 找到 KaiwetLab 的拦截提示并选择“仍要打开”。

只应从本仓库的 Releases 页面下载安装包。

## 应用更新

KaiwetLab 使用 Sparkle 2 获取签名更新：

- 应用会定期在后台检查更新。
- 可通过菜单“`KaiwetLab → 检查更新…`”立即检查。
- 更新可在后台下载，并在应用退出时安装。
- 当前已是最新版本时，会显示相应提示。

## 固件升级注意事项

- 确认设备型号和固件目标型号一致。
- 升级过程中不要拔出 USB、关闭蓝牙或强制退出应用。
- 确保 Mac 和设备供电稳定。
- 固件升级存在设备无法启动的风险，请自行确认固件来源可靠。

## 文件完整性

KaiwetLab 1.1.0 arm64 DMG：

```text
SHA-256  fd0801324ba092a4c8401f9e3edb913cc43b79948cde834a89eb24cc9ef4dfa5
```

Sparkle 更新包还使用 EdDSA 签名验证，应用不会安装签名不匹配的更新。

## 问题反馈

如遇到连接、记录、曲线或更新问题，请在 [Issues](https://github.com/KaiwetN/KaiwetLab/issues) 中提交，并附上：

- macOS 版本和 Mac 型号
- KaiwetLab 版本
- 设备型号与固件版本
- 可复现步骤及相关日志
