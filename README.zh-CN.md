# FallingSound（坠音）

[English](README.md)

一款基于 **Kotlin Multiplatform + Compose Multiplatform** 的跨平台音乐播放器，支持 **Android / iOS / Desktop**（Windows / macOS / Linux）三端。通过 JS 插件系统聚合多音源，提供统一的搜索、播放、歌单、歌词、评论体验，并支持本地音乐、WebDAV 多设备同步与播放统计。

## 功能特性

- **播放功能** — 全平台统一播放体验：Android 使用 Media3 ExoPlayer（前台 Service + 通知栏控制、音频焦点管理），iOS 使用 AVPlayer（后台播放、来电中断处理），Desktop 使用 JavaFX Media（窗口最小化继续播放）
- **插件系统** — 基于 QuickJS 的 JS 音源插件，支持 URL 与本地文件加载；一次搜索并行请求多个插件，按相似度评分排序并去重；主音源失效时自动跨插件回退到替代音源
- **搜索与发现** — 多音源聚合搜索，结果评分排序、去重
- **歌词与评论** — 跨音源统一的歌词与评论体验
- **本地音乐** — 播放本地音乐，内置 ID3v2.3 元数据解析 / 写入
- **下载缓存** — 离线下载与本地缓存
- **备份同步** — 基于 WebDAV 的多设备同步
- **播放统计** — 记录收听历史与播放数据
- **UI / 个性化** — Material 3 设计，封面调色动态主题

## 支持平台

| 平台 | 播放依赖 | 说明 |
|------|---------|------|
| Android (API 24+) | Media3 ExoPlayer | 前台 Service + 通知栏控制、音频焦点管理 |
| iOS (15.0+) | AVPlayer | AVAudioSession 后台播放、KVO 播放状态监听、来电中断处理 |
| Desktop (Windows / macOS / Linux) | JavaFX Media | 窗口最小化继续播放 |

## 下载

从 [Releases](../../releases) 页面下载对应平台的最新构件。

| 平台 | 构件格式 |
|------|---------|
| Android | APK |
| iOS | IPA（未签名） |
| Windows | EXE 安装包 |
| macOS | DMG（未签名） |
| Linux | DEB 安装包 |

> **注意**：iOS IPA 与 macOS DMG 为未签名构建，仅用于开发调试，无法通过 App Store 或 sideload 安装到未越狱设备。

## 截图

<!-- 在此处添加应用截图，例如：
![Android](screenshots/android_main.png)
![iOS](screenshots/ios_main.png)
![Desktop](screenshots/desktop_main.png)
-->

*截图待添加。*

## 技术栈

- **语言 / UI** — Kotlin、Compose Multiplatform、Material 3
- **网络** — Ktor（OkHttp / Darwin 引擎）、Okio
- **数据库** — Room (KMP) + SQLite
- **DI** — Kodein DI
- **图片加载 / 主题** — Coil 3、kmpalette
- **序列化 / 数据流** — kotlinx.serialization、Store5
- **插件引擎** — QuickJS（JS 音源插件）
- **文件 / 同步** — FileKit、WebDAV client KMP
- **元数据** — 自研 ID3v2.3 解析 / 写入模块
- **日志** — Napier + 本地文件日志（含崩溃捕获）

## 免责声明

本项目仅用于学习与技术交流。音源插件提供的歌曲内容版权归各版权方所有，请勿用于商业用途。
