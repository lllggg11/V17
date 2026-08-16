# V18 数据库 CSV 导出 (2026-08-16)

## 📦 包含文件 (37 个)

### 35 张核心表 CSV
- `league_predictions.csv` (3219 行 × 277 列) - 主预测表
- `league_outcomes.csv` (7465) - 真值
- `league_standings.csv` (222) - 积分榜
- `team_features.csv` (739) - 球队画像
- `fixtures.csv` (5188) - 比赛
- `league_events_summary.csv` (2897) - 事件摘要
- `league_events_roster.csv` (5020) - 阵容
- `match_odds.csv` (7896) - 赔率
- `league_multi_season.csv` (18618) - 多季
- `weather_history.csv` (32828) - 天气
- `fc26_player_ratings.csv` (10707) - FC26
- `fc26_eafchub.csv` (18405) - 球员
- `fc26_player_ratings_agg.csv` (2641) - 聚合
- `fc26_injury_impact.csv` (216) - 伤停
- `ea_fc26_official.csv` (5004) - EA 官方
- `players.csv` (2651) - 球员
- `player_match_stats.csv` (4333) - 球员数据
- `team_players.csv` (2496) - 队球员
- `team_value_dims_v18.csv` (775) - 队值
- `team_xg_rates.csv` (172) - xG
- `venue_coords.csv` (160) - 球场
- `referee_stats.csv` (254) - 裁判
- `league_top_scores.csv` (90) - 联赛最高
- `league_style_profile.csv` (16) - 风格
- `kelly_backtest.csv` (200) - Kelly 回测
- `regression_results.csv` (94) - 回归
- `regression_results_v18skill.csv` (94) - V18
- `prediction_evaluations.csv` (140) - 评估
- `prediction_orders.csv` (68) - 订单
- `prediction_runs.csv` (9672) - 运行
- `reviews.csv` (195) - 复盘
- `ledger_settlements.csv` (24) - 结算
- `strategy_config.csv` (6) - 策略
- `fixture_distance.csv` (102) - 距离
- `fixture_weather.csv` (102) - 比赛天气

### 模型 (4 个 JSON)
- `models/baseline_81d_v3_22f.json` (22 特征 + warfare)
- `models/baseline_81d_v4_23f.json` (23 特征 + injury ⭐ 最佳)
- `models/baseline_81d_v5_24f.json` (24 特征 + impact)
- `models/baseline_81d_v6_27f.json` (25 特征 + morale)

### 知识库
- `league_rules_warfare.md` - 19 联赛规则
- `injury_v2_normalized.json` - 188 队 FotMob 伤停

## 📊 关键统计

| 维度 | 覆盖率 |
|------|--------|
| 双方真 ELO | 82.9% |
| 双方 gf_pg | 98.0% |
| 任意 odds | 86.7% |
| D45 fair | 77.7% |
| 伤停 | 22.3% (110 双方真值) |
| warfare | 22.3% |
| team_features | 38 联赛 738 队 |

## 🏆 Brier 排名 (n=655)

| 模型 | Brier | vs Market |
|------|-------|-----------|
| **LR v4** | **0.1800** | **-19.46%** ⭐ |
| LR v5 | 0.1807 | -19.16% |
| LR v3 | 0.1808 | -19.12% |
| LR v6 | 0.1812 | -18.92% |
| Market D45 | 0.2235 | 0% |

## 🔧 数据还原

```bash
# 解压
unzip v18_csv_export.zip

# Excel / Pandas 直接打开
import pandas as pd
df = pd.read_csv('league_predictions.csv')
```

## 🚫 排除

- dim81_match_values (389k) - dim81 长表冗余
- prediction_dimensions (467k) - 模型中间产物
- 系统表 (sqlite_*)
- 历史备份
