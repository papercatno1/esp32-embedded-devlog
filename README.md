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
| 2026-10-31 | 设备到货 · 首次开机确认 · 备份与装机 | 认板为 ESP32-S3-LCD-2；`COM16` 连通；出厂固件为微雪 `01_factory` 演示；整片 16 MB 已备份校验；屏幕点亮正常；摄像头已装待功能验证 | [日志](2026-10-31/日志.md) |

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
| 屏幕 | 2.0″ IPS 240×320，262K 色，40pin FPC，**无触摸** |
| 摄像头 | OV5640 500 万像素（SKU 29456），24pin FPC |
| 传感器 | QMI8658 六轴 IMU（出厂 demo 左栏可见，固件含 `qmi8658_task`） |
| 存储 | TF / microSD（SDMMC 4 线）+ 板载 10 MB FAT 分区 |
| 其他 | USB-C、原生 USB-Serial/JTAG、BAT 电池座、U.FL 天线座、BOOT/RST、双排排针 |
| MAC | `b8:1f:3f:c8:25:24` |
| 串口 | `COM16`（115200 默认），无需 CH340 驱动 |

## 当前进度

- [x] 硬件识别与连通性验证
- [x] 出厂固件取证（分区表 / app 描述符 / 关键字符串）
- [x] 整片 16 MB Flash 备份 + 三重校验（13:51）
- [x] 屏幕点亮（40pin FPC，出厂 demo 正常显示 System 页）
- [x] 摄像头安装（OV5640 插入 24pin 座，锁扣已压平）
- [x] 工具链方案规划（PlatformIO + Arduino，含环境体检与里程碑）
- [ ] 摄像头功能验证（M2 自检固件；出厂 demo 的 Camera 页在本机无触摸下点不动）
- [ ] 开发方案定稿 → 建项目仓库

## 相关链接

- GitHub 主页：<https://github.com/papercatno1>
- 微雪产品页：<https://www.waveshare.com/wiki/ESP32-S3-LCD-2>
