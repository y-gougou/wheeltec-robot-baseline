# WHEELTEC 机器人基线

本仓库原名 `WHEELTEC_C50X_2026_0418`，保留接手 WHEELTEC R550PLUS 三全向轮机器人时的 ROS 控制、数据采集与底盘固件工程。

本仓库 fork 自 [clolckliang/WHEELTEC_C50X_2025.10.17](https://github.com/clolckliang/WHEELTEC_C50X_2025.10.17)。原上游来源、Git 提交作者及源码内的版权和许可声明均保留；各部分代码的使用条件以原文件及上游说明为准。

## 项目入口

| 路径 | 内容 |
|---|---|
| [turn_on_wheeltec_robot/](turn_on_wheeltec_robot/) | ROS1 catkin 包：底盘串口通信、里程计、IMU、电流读取、CSV 采集和 Web 控制 |
| [turn_on_wheeltec_robot/README.md](turn_on_wheeltec_robot/README.md) | ROS 包使用说明及接口约定 |
| [turn_on_wheeltec_robot/launch/](turn_on_wheeltec_robot/launch/) | 底盘、数据采集、Web 控制、建图和导航启动文件 |
| [turn_on_wheeltec_robot/scripts/](turn_on_wheeltec_robot/scripts/) | 采集与控制 Python 脚本 |
| [turn_on_wheeltec_robot/web/](turn_on_wheeltec_robot/web/) / [webapp/](turn_on_wheeltec_robot/webapp/) | 历史 Web 界面工程 |
| [omi_car/](omi_car/) | 底盘嵌入式工程，包含 `USER/`、`BALANCE/`、外设驱动、FreeRTOS 和 EIDE 配置 |
| [docs/](docs/) | 开发记录 |
| [源码工程使用指南.pdf](源码工程使用指南.pdf) | 原工程使用指南 |

ROS 入口文件包括 `turn_on_wheeltec_robot.launch`、`data_collector.launch` 和 `web_control.launch`。串口约定与启动组合在两个分支之间存在差异，复现时应先阅读目标分支内的 README 和 launch 文件。

## 保留的独立分支

以下记录的是本次整理前的代码状态：

| 分支 | 原代码提交数 | 代码快照 |
|---|---:|---|
| [main](https://github.com/y-gougou/wheeltec-robot-baseline/tree/main)（默认） | 14 | [8fca08969a3f1916c9eb187f5f841e194e5fd982](https://github.com/y-gougou/wheeltec-robot-baseline/tree/8fca08969a3f1916c9eb187f5f841e194e5fd982) |
| [yp-dev](https://github.com/y-gougou/wheeltec-robot-baseline/tree/yp-dev) | 13 | [131fc551fd4fd35eaf9313fcc33e1ef454f85a6f](https://github.com/y-gougou/wheeltec-robot-baseline/tree/131fc551fd4fd35eaf9313fcc33e1ef454f85a6f) |

两个分支从 `c56984cc9dfc4a916521ec5a23fffeaf300ee28d` 分叉。整理前 `main` 有 4 个独有提交，`yp-dev` 有 3 个独有提交，后者包含采集 launch 命名空间、传感器串口和文档的调整。因此保留两条开发路线，没有将其中一条覆盖为另一条。新增根 README 会使 `main` 的提交数增加。

本 fork 的 Git 历史与后续数据采集历史仓库不同，保留为独立基线。

## 后续项目

- [wheeltec-robot-platform](https://github.com/y-gougou/wheeltec-robot-platform)：当前机器人平台入口。
- [robot-fault-diagnosis-thesis](https://github.com/y-gougou/robot-fault-diagnosis-thesis)：完整毕业设计工程与故障诊断研究。
- [wheeltec-development-history](https://github.com/y-gougou/wheeltec-development-history)：后续数据采集代码的连续开发历史。
- [project-index](https://github.com/y-gougou/project-index)：项目导航。

本次整理仅新增根 README，两个分支均保留；未修改源码或固件，也未执行 ROS 构建、固件烧录或机器人硬件测试。
