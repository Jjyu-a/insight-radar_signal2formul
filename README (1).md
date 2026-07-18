# 灵感雷达 · Linggan Radar

> 把直觉变成证据，把证据变成配方。

2026 AI 先锋未来人才大赛 · 珀莱雅美妆科研实验室命题方案。

---

## 项目背景

珀莱雅命题：**"如果你加入珀莱雅的美妆科研实验室，你会如何借助 AI 找到下一款功效护肤产品的灵感？"**

**灵感雷达**的切入点：在智能配方师生成方案之前，先解决研发最上游的灵感发现问题——用 AI 从海量碎片化信号中识别"弱信号"，预测需求趋势，生成可验证的科研假设，并将验证结果回流学习形成闭环。

---

## 四模块架构

```
弱信号识别 → 未来需求预测 → 科研假设生成 → [智能配方系统（现有工具）] → 验证学习 ↻
```

| 模块 | 说明 |
|------|------|
| ① 弱信号识别 | 整合小红书、电商评论、客服反馈、学术论文、专利、海外社区，识别未成热点但持续增长的信号 |
| ② 未来需求预测 | 预测未来 1–2 年增长潜力方向，输出增长评分与时间窗口 |
| ③ 科研假设生成 | 结合皮肤机理 + 企业知识库 + 科研文献，生成可验证假设，衔接智能配方师 |
| ④ 验证学习 | 实验结果 + 市场反馈回流优化模型，知识沉淀而非一次性产出 |

---

## 文件结构

```
linggan-radar/
├── index.html        # 主入口导航页
├── overview.html     # 方案总览（四模块架构说明）
├── demo.html         # 互动 Demo（实时调用 Claude API）
├── tests.html        # 测试套件（5 条预置用例，支持批量运行）
└── README.md
```

---

## 测试用例（tests.html）

| # | 信号类型 | 核心信号 |
|---|---------|---------|
| T01 | 小红书用户帖 | 壬二酸 + 玻色因搭配诉求 |
| T02 | 学术文献摘要 | 皮肤微生物组与后生元潜力 |
| T03 | 专利摘要 | β-葡聚糖 + 神经酰胺前体 TLR2 通路 |
| T04 | 客服反馈 | 夏季精华灼热感集中反馈（华南/华东，37条） |
| T05 | 海外社区 | Bakuchiol 作为温和视黄醇替代物（EU/AU 趋势）|

支持单条运行 / 一键批量运行对比结果。

---

## 技术说明

- **前端**：纯 HTML + CSS + Vanilla JS，无框架依赖，零构建步骤
- **AI 驱动**：调用 Anthropic Claude API（`claude-sonnet-4-6`）
- **部署**：直接 Netlify Drop 拖拽 / GitHub Pages 部署，无需服务器
- **字体**：IBM Plex Sans + IBM Plex Mono（Google Fonts CDN）

---

## 本地运行

```bash
# 直接用浏览器打开 index.html 即可（需有网络加载字体和 API）
open index.html

# 或起一个本地服务器（避免某些浏览器的 CORS 限制）
python3 -m http.server 8080
```

---

## 部署到 GitHub Pages

```bash
git init
git add .
git commit -m "init: 灵感雷达 v1.0"
git remote add origin https://github.com/yourusername/linggan-radar.git
git push -u origin main
# 然后在 GitHub 仓库 Settings → Pages → Source 选 main 分支即可
```

---

*2026 AI 先锋未来人才大赛 · 珀莱雅命题*
