# 网络安全 AI 分析 Agent（基于 Claude Code 构建）

![Claude Code](https://img.shields.io/badge/Claude%20Code-3.5-blueviolet)
![License](https://img.shields.io/badge/license-MIT-green)

## 📖 项目简介

本项目是申请 **Xiaomi MiMo Orbit 百万亿 Token 创造者激励计划** 的演示仓库。

我们团队专注于网络安全产品开发。借助 **Claude Code** 的终端驱动开发能力，快速构建了一个具备长链推理与多 Agent 协作的自动化安全事件响应系统。

## 🛠️ 如何用 Claude Code 构建本项目

所有核心代码、提示词编排、工具调用逻辑均由 **Claude Code** 在终端中通过自然语言驱动生成：

- 使用 `/init` 初始化项目结构
- 使用 `/add` 引入威胁情报 API 文档
- 多轮对话迭代 Agent 的推理步骤与异常处理逻辑
- Claude Code 自动编写单元测试和集成测试

## ✨ 核心特性（与 Claude Code 协同实现）

| Agent | 功能 | Claude Code 贡献 |
|-------|------|------------------|
| **研判Agent** | 分析原始告警，调用威胁情报 API，输出置信度评分 | 自动生成 API 调用封装与重试机制 |
| **溯源Agent** | 重构攻击链，进行图推理定位失陷主机 | 协助设计多步推理提示词与数据关联逻辑 |
| **决策Agent** | 执行防火墙封禁、飞书通知、Jira 建单 | 生成幂等的原子动作脚本 |

## 🏗️ 系统核心逻辑流

> 更详细的流程可参考仓库中的 workflow.png。

## 📦 主要依赖与工具

- **模型底座**：Xiaomi MiMo API（申请中）、Claude API
- **威胁情报**：VirusTotal、Whois
- **持久化**：Redis（Agent 记忆）
- **通知**：飞书 / 企业微信机器人、Jira API

## 🔁 使用 Claude Code 的典型开发记录（示例）

```bash
$ claude
> /init 网络安全Agent
> 创建研判Agent，输入原始告警JSON，输出置信度0-100
> 增加VirusTotal查询工具，失败时重试3次
> 编写测试用例：断言低危告警置信度<30
申请 MiMo Token 的目的
降低推理成本：将研判 Agent 从 Claude API 迁移至 MiMo API

长上下文测试：一次性分析 1M token 的全周告警日志

免费开放：为 50 家初创安全团队提供 6 个月免费服务

开源回馈：将 Agent 框架及 Claude Code 最佳实践开源

📎 说明
本仓库为申请材料的一部分，不包含完整源码及内部配置

实际运行日志因安全合规要求无法公开，架构流程与代码结构均已在本地环境验证通过

