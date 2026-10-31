# ESP32 嵌入式开发 · 开发日志

记录一块 **微雪 Waveshare ESP32-S3-LCD-2**（ESP32-S3R8 / 8 MB PSRAM / 16 MB Flash / 2 寸 IPS 240×320）从零开始的嵌入式开发过程。

[![日志](https://img.shields.io/badge/devlog-daily-informational)](2026-10-31/日志.md)

> 这是**日志仓库**，只放"过程记录"（文字 + 照片 + 命令输出 + 决策）。
> 代码、工程配置、固件另存**项目仓库**，两者独立提交、独立推送。
> 当前状态：**硬件已确认、已连通，开发方案未定**。

仓库地址：<https://github.com/papercatno1/esp32-embedded-devlog>

## 目录

| 日期 | 主题 | 关键结论 | 记录 |
| --- | --- | --- | --- |
| 2026-10-31 | 设备到货 · 首次开机确认 | 认板为 ESP32-S3-LCD-2；`COM16` 连通，esptool 可读写 Flash；出厂固件为微雪 `01_factory` 演示 | [日志](2026-10-31/日志.md) |

## 仓库结构

```
README.md                  本文件：索引 + 项目现状
记录规范.md                 记录规则（颗粒度 / 命名 / 提交 / 推送）
templates/每日日志模板.md    新一天开篇用的骨架
YYYY-MM-DD/
  ├─ 日志.md               当天的完整记录（按"回合"追加）
  └─ 图片/                 当天用到的照片、截图、实物图
```

## 硬件速查

| 项目 | 参数 |
| --- | --- |
| 开发板 | 微雪 Waveshare ESP32-S3-LCD-2（2 inch） |
| 主控 | ESP32-S3（QFN56）rev v0.2，双核 LX7 + LP 核，240 MHz |
| 内存 | 8 MB PSRAM（内封，ESP32-S3R8） |
| Flash | 16 MB，quad，3.3 V |
| 无线 | Wi-Fi 2.4 GHz + BLE 5 |
| 屏幕 | 2.0″ IPS 240×320，262K 色，40pin FPC |
| 摄像头 | OV5640 500 万像素（SKU 29456），24pin FPC |
| 存储 | TF / microSD（SDMMC 4 线）+ 板载 10 MB FAT 分区 |
| 其他 | USB-C、原生 USB-Serial/JTAG、BAT 电池座、U.FL 天线座、BOOT/RST、双排排针 |
| MAC | `b8:1f:3f:c8:25:24` |
| 串口 | `COM16`（115200 默认），无需 CH340 驱动 |

## 当前进度

- [x] 硬件识别与连通性验证
- [x] 出厂固件取证（分区表 / app 描述符 / 关键字符串）
- [ ] 整片 16 MB Flash 备份（刷机前置动作，必做）
- [ ] 屏幕点亮（LVGL 点屏）
- [ ] 摄像头出图（OV5640 拍照 / 图传）
- [ ] 开发方案定稿 → 建项目仓库

## 相关链接

- GitHub 主页：<https://github.com/papercatno1>
- 微雪产品页：<https://www.waveshare.com/wiki/ESP32-S3-LCD-2>
