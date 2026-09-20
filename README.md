# OpenWrt NetBird

[![检查并发布](https://github.com/tbc0309/openwrt-netbird/actions/workflows/build.yml/badge.svg)](https://github.com/tbc0309/openwrt-netbird/actions/workflows/build.yml)
[![BSD-3-Clause](https://img.shields.io/badge/license-BSD--3--Clause-blue.svg)](LICENSE)

用于 OpenWrt 的 [NetBird](https://github.com/netbirdio/netbird) 软件包。本仓库派生自 [messense/openwrt-netbird](https://github.com/messense/openwrt-netbird)，并通过 GitHub Actions 定期检查 NetBird 新版本、交叉编译多个 OpenWrt 架构并发布 IPK 软件包。

## 支持架构

- `aarch64_generic`
- `aarch64_cortex-a53`
- `aarch64_cortex-a72`
- `arm_cortex-a7_neon-vfpv4`
- `arm_cortex-a9`
- `arm_cortex-a15`
- `x86_64`
- `i386_pentium4`
- `mips_74kc`
- `mipsel_24kc`

构建产物可从仓库的 [Releases](https://github.com/tbc0309/openwrt-netbird/releases) 页面下载。

## 使用方法

安装与设备架构匹配的 IPK 后，使用 Setup Key 登录：

```bash
netbird login --setup-key <SETUP_KEY>
```

启用并启动 NetBird 服务：

```bash
/etc/init.d/netbird enable
/etc/init.d/netbird start
```

查看服务状态：

```bash
netbird status
```

## 自动构建

工作流每天检查一次 NetBird 官方最新 Release。发现版本变化或缺少对应 Release 时，将更新软件包元数据，使用 OpenWrt SDK 编译各架构软件包并发布；也可在 Actions 页面手动触发。

## 许可证

本仓库沿用上游项目的 [BSD 3-Clause License](LICENSE)。NetBird 本体及构建过程中取得的第三方组件分别遵循其各自许可证。
