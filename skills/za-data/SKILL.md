---
name: za-data
description: 数据处理阶段 —— 数据发现与质量评估。当用户要「找数据」「评估数据集」「确定用什么数据」或提到 CRSP/Compustat/WRDS/French/AQR/OSAP/FRED 等数据源时使用。
whenToUse: 数据发现、数据集质量评估、可行性分级。
---

# 数据处理阶段

为研究问题寻找并评估数据集。本 skill 附带两个角色定义，派发时读取并**完整采纳其角色设定**：
- `references/agents/explorer.md` — 数据寻找者
- `references/agents/explorer-critic.md` — 数据质量评审者

## 工作流

1. 读研究规格 + 策略备忘（若存在）
2. 读 `references/domain/domain-profile.md` 的 Common Data Sources（CRSP/Compustat/French/Open Source Asset Pricing/AQR/FRED/OptionMetrics/TAQ/文本另类数据）
3. 明确需要哪些变量（因子/结果收益/控制/时间区间/地理）
4. 派发 Explorer 检索数据源类别，每数据集报告：名称、提供者、访问级别、关键变量、覆盖度、**feasibility grade**（A 立即可用 / B 需努力 / C 受限可获 / D 极难）、优势局限
5. 派发 explorer-critic 用 5-point 评估：measurement validity、sample selection（survivorship bias?）、external validity、identification compatibility、known issues
6. 保存 `quality_reports/data_exploration_[topic].md`，附被拒数据集表

## 原则
- 拿不到的数据再完美也没用，始终赋 A/B/C/D
- 5-point 永不跳过；Explorer + explorer-critic 永不跳过 critic
- 先读 domain-profile
