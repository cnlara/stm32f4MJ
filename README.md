# stm32f4MJ · STM32F4 计分麻将

用 STM32F4 读取「磁性点棒」的实时点数，记录对局结果，同步到 GitHub 并生成对局统计看板。

- **读取**：4 位玩家点棒盘 + 磁感应槽位 → STM32F4 读各家点数
- **记录**：每局结算写入 `data/matches.jsonl`（含 before/after/delta/winner）
- **同步**：PC 同步器把增量对局推送到本仓库
- **看板**：GitHub Pages 静态页展示对局统计（`site/`）

目录：
```
firmware/   STM32F4 固件（读取/结算/记录）
sync/       PC 端同步器与统计生成脚本
data/       对局原始数据（matches.jsonl 与 stats）
site/       GitHub Pages 看板
```

详细设计见 [DESIGN.md](DESIGN.md)。