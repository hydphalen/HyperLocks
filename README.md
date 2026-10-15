# HyperLocks






**面向 HyperOS 的个性化 LSPosed 模块**，集中管理锁屏、密码界面、状态栏、控制中心与系统设置界面的深度定制功能。

**作者**：雪子 × 晚晚  
**快速导航**：[版本发布 (Releases)](https://www.google.com/search?q=https%3A%2F%2Fgithub.com%2Fhydphalen%2FHyperLocks%2Freleases) · [更新日志 (CHANGELOG.md)](https://www.google.com/search?q=.%2FCHANGELOG.md) · [校验文件 (SHA256SUMS)](https://www.google.com/search?q=.%2FSHA256SUMS) · [第三方声明 (THIRD\_PARTY\_NOTICES.md)](https://www.google.com/search?q=.%2FTHIRD_PARTY_NOTICES.md) · [开源协议 (LICENSE-HyperTweak.txt)](https://www.google.com/search?q=.%2FLICENSE-HyperTweak.txt)

## 功能模块概览

| 功能模块 | 核心定制方向 | 详细能力说明 |
| :--- | :--- | :--- |
| **锁屏定制** | 小组件、卡片与息屏控制 | 支持锁屏小组件与样式调整、卡片与布局管理、息屏显示（AOD）及其它锁屏显示项控制 |
| **锁屏密码界面** | 数字圆环与键盘美化 | 提供锁屏密码数字圆环样式及输入键盘外观的个性化定制 |
| **状态栏与控制中心** | 顶栏、高斯模糊与通知卡片 | 支持控制中心顶栏布局与异形修饰、背景模糊、通知卡片圆角/描边与半透明视觉效果 |
| **系统设置增强** | 界面开关与二级页面定制 | 提供特定系统设置界面的快捷开关控制与二级页面布局定制 |
| **日志与管理** | 运行状态诊断与导出 | 内置运行日志导出功能，自动记录模块版本、设备型号及导出时间等诊断信息 |

## 实机效果展示

> [!NOTE]
> 以下实机截图由作者在不同开发阶段提供，仅按功能与视觉效果分类展示；历史开发阶段截图不作为 `1.6.0` 版本的完整真机验证记录。

### 控制中心与密码界面

| 控制中心 · 整机搭配 | 锁屏密码 · 数字圆环 |
| :-: | :-: |
|  |  |
| **整机搭配参考**：包含系统主题及其他美化组件，图中全部外观并非均由 HyperLocks 单一模块提供。 | **密码圆环效果**：独立模块开发阶段的锁屏数字密码圆环视觉样式。 |

### 通知中心视觉定制

| 通知卡片样式 | 日期、大时钟与背景 |
| :-: | :-: |
|  |  |
| **通知卡片细节**：展示通知卡片的圆角弧度、细微描边与半透明层级效果。 | **无通知状态布局**：展示顶部日期、大时钟排版及圆角模糊背景效果。 |

### 控制中心顶栏细节

| 控制中心顶栏组合效果 |
| :-: |
|  |
| **顶栏整体组合效果**：包含模糊背景、异形修饰框、时间/网络/电量状态组件以及快捷功能按钮布局。 |

## 兼容性与环境要求

| 环境维度 | 要求与版本信息 |
| :--- | :--- |
| **操作系统** | Xiaomi HyperOS（基于 Android） |
| **框架要求** | LSPosed / Xposed 兼容框架 |
| **当前版本** | `v1.6.0` · 界面升级公开测试版（完整版本号 `20261015.1.6.0`，Version Code `52`） |
| **基准版本** | 适配并基于 `1.5.2` / `1.6.0` 构建 |

## 获取与安装说明

1. **下载安装包**：前往本仓库 [Releases 页面](https://www.google.com/search?q=https%3A%2F%2Fgithub.com%2Fhydphalen%2FHyperLocks%2Freleases%2Ftag%2Fv1.6.0) 下载最新发布的 `.apk` 安装包。
2. **校验文件完整性**：安装前建议对比根目录或 Release 附件中的 [SHA256SUMS](https://www.google.com/search?q=.%2FSHA256SUMS) 校验值，确保安装包与源码补丁完整无篡改。
3. **激活模块**：安装 APK 后，在 **LSPosed 管理器**中启用 `HyperLocks` 模块，勾选对应系统作用域并重启相关作用域进程或设备。
4. **问题排查**：如遇功能异常，可通过模块内置的**日志与管理**功能导出运行日志（含版本号、设备信息与时间戳）以便定位问题。

## 源码与构建说明

> [!IMPORTANT]
> 本仓库当前尚未在根目录整合完整的独立 Gradle 源码工程，请仔细阅读以下构建与产物说明：

- **增量源码包 (`source-patch.zip`)**：[Releases](https://www.google.com/search?q=https%3A%2F%2Fgithub.com%2Fhydphalen%2FHyperLocks%2Freleases%2Ftag%2Fv1.6.0) 附件中的 `source-patch.zip` 包含了 `1.6.0` 界面升级的 Kotlin 增量源码、编译支持文件、验证工具及增量打包资料。该增量包基于 `1.5.2` 版本制作，本身**不是**完整的独立 Gradle 工程。
- **编译桩文件限制**：增量包中仅供编译期通过的桩文件（Stub files）**严禁打入最终 APK**。
- **非界面实现与隐私边界**：`1.6.0` 版本 APK 保留了 `1.5.2` 的非界面底层实现；公开的发布资料不包含签名私钥、个人用户配置或本地完整构建环境。
- **切勿误用默认源码包**：请勿将 GitHub Release 自动生成的 `Source code (zip)` / `Source code (tar.gz)` 当作完整可编译工程使用。

## 仓库目录结构

```text
HyperLocks/
├── CHANGELOG.md                   # 版本演进与更新日志
├── LICENSE-HyperTweak.txt         # GPL-3.0 开源许可协议文本
├── README.md                      # 项目说明文档
├── SHA256SUMS                     # 发布产物 SHA-256 哈希校验清单
├── THIRD_PARTY_NOTICES.md         # 第三方组件与致谢声明
├── showcase-control-center.jpg    # 实机展示：控制中心整机搭配
├── showcase-control-header.jpg    # 实机展示：控制中心顶栏细节
├── showcase-notification-cards.jpg# 实机展示：通知中心卡片效果
├── showcase-notification-clock.jpg# 实机展示：通知中心日期与大时钟
└── showcase-password-rings.jpg    # 实机展示：锁屏密码数字圆环
```

## 致谢与许可协议

- **开源许可协议**：本项目遵循 [GPL-3.0 License](https://www.google.com/search?q=.%2FLICENSE-HyperTweak.txt) 开源许可协议。
- **第三方声明与致谢**：关于上游基础与第三方开源组件声明，请参阅仓库中的 [THIRD\_PARTY\_NOTICES.md](https://www.google.com/search?q=.%2FTHIRD_PARTY_NOTICES.md) 及 [LICENSE-HyperTweak.txt](https://www.google.com/search?q=.%2FLICENSE-HyperTweak.txt)。
