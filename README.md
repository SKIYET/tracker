# BitTorrent Tracker 聚合项目

[![更新状态](https://github.com/adysec/tracker/workflows/Daily%20Update%20Tracker/badge.svg)](https://github.com/adysec/tracker/actions)
[![许可证](https://img.shields.io/github/license/adysec/tracker)](LICENSE)

## 📖 项目简介

本项目自动收集、测试和维护高质量的 BitTorrent Tracker 服务器列表。通过每日自动化流程，从多个开源项目聚合 Tracker 数据，进行连通性测试，并提供按协议分类的优选列表。

### ✨ 核心特性

- 🛡️ **安全可靠**：集成威胁情报，自动过滤恶意 IP 地址
- 🔄 **实时更新**：每日自动更新，确保 Tracker 列表时效性
- 📊 **协议分类**：支持 HTTP、HTTPS、UDP、WSS 四种协议分类
- 🚀 **高可用性**：仅保留经过连通性测试的可用 Tracker
- 🌐 **多源聚合**：整合十余个知名开源项目的 Tracker 资源

## 📋 Tracker 列表

### 全量 Tracker 列表

包含所有聚合的 Tracker 服务器（未经可用性筛选）：

```
https://down.adysec.com/trackers_all.txt
https://raw.githubusercontent.com/adysec/tracker/main/trackers_all.txt
```

### 优选 Tracker 列表

经过连通性测试的高质量 Tracker 服务器：

**综合列表（推荐）**
```
https://down.adysec.com/trackers_best.txt
https://raw.githubusercontent.com/adysec/tracker/main/trackers_best.txt
```

**按协议分类**

| 协议 | 下载链接 |
|------|----------|
| HTTP | [`trackers_best_http.txt`](https://down.adysec.com/trackers_best_http.txt) \| [`GitHub`](https://raw.githubusercontent.com/adysec/tracker/main/trackers_best_http.txt) |
| HTTPS | [`trackers_best_https.txt`](https://down.adysec.com/trackers_best_https.txt) \| [`GitHub`](https://raw.githubusercontent.com/adysec/tracker/main/trackers_best_https.txt) |
| UDP | [`trackers_best_udp.txt`](https://down.adysec.com/trackers_best_udp.txt) \| [`GitHub`](https://raw.githubusercontent.com/adysec/tracker/main/trackers_best_udp.txt) |
| WSS | [`trackers_best_wss.txt`](https://down.adysec.com/trackers_best_wss.txt) \| [`GitHub`](https://raw.githubusercontent.com/adysec/tracker/main/trackers_best_wss.txt) |

## 🔧 使用方法

### BitTorrent 客户端配置

1. **qBittorrent**：选项 → BitTorrent → 自动添加以下 Tracker → 粘贴列表 URL
2. **Transmission**：编辑首选项 → Tracker → 添加 Tracker URL
3. **其他客户端**：在 Tracker 设置中添加上述任一 URL

### 命令行使用

```bash
# 获取最新 Tracker 列表
curl -s https://down.adysec.com/trackers_best.txt

# 获取特定协议的 Tracker
curl -s https://down.adysec.com/trackers_best_udp.txt
```

## 🛠️ 本地部署

### 环境要求

- Linux/macOS 系统
- Bash 4.0+
- curl、nc、wscat 工具

### 快速开始

```bash
# 1. 克隆项目
git clone https://github.com/adysec/tracker.git
cd tracker

# 2. 格式化 Tracker 列表
bash format.sh trackers_all.txt

# 3. 测试 Tracker 可用性
bash test_trackers.sh trackers_all.txt
```

### 自定义配置

创建 `blackstr.txt` 文件来过滤特定的 IP 地址或域名：

```bash
# 示例：过滤恶意 IP
echo "192.168.1.100" >> blackstr.txt
echo "malicious-tracker.com" >> blackstr.txt
```

## 📊 数据来源

本项目聚合以下优质开源项目的 Tracker 资源：

- [ngosang/trackerslist](https://github.com/ngosang/trackerslist)
- [XIU2/TrackersListCollection](https://github.com/XIU2/TrackersListCollection)
- [chenjia404/CnTrackersList](https://github.com/chenjia404/CnTrackersList)
- [hezhijie0327/Trackerslist](https://github.com/hezhijie0327/Trackerslist)
- [DeSireFire/animeTrackerList](https://github.com/DeSireFire/animeTrackerList)
- [NewTrackon](https://newtrackon.com/)
- 以及其他多个社区维护的项目

## 🤝 贡献指南

欢迎提交 Issue 和 Pull Request！

### 如何贡献

1. Fork 本项目
2. 创建特性分支：`git checkout -b feature/amazing-feature`
3. 提交更改：`git commit -m 'Add amazing feature'`
4. 推送分支：`git push origin feature/amazing-feature`
5. 提交 Pull Request

### 报告问题

- 发现无效的 Tracker？请提交 Issue
- 建议新的数据源？欢迎讨论
- 功能建议？我们很乐意听取

## 📄 许可证

本项目采用 [MIT 许可证](LICENSE) 开源。

## ⭐ Star History

如果这个项目对您有帮助，请给我们一个 Star！

---

<div align="center">

**[🏠 主页](https://github.com/adysec/tracker)** • 
**[📥 下载](https://down.adysec.com/)** • 
**[❓ 问题反馈](https://github.com/adysec/tracker/issues)**

</div>
