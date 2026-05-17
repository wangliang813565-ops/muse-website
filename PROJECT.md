---
project: MUSE 官网 (Hugo)
status: active
priority: P1
last_updated: 2026-05-18
type: project_entry
---

# MUSE 官网（Hugo 双语 + GEO SEO）— 场景入口

> 给 Claude Code 进入项目时自动加载场景上下文。
> 跨平台身份单源：`~/cowork/knowledge-vault/_MERIDIAN/01-IDENTITY.md`

## 目标

MUSE 在迪拜的对外官网 `musetrendytoy.com`，承接潮玩（Designer Toys）+ 企业礼品业务的 UAE / GCC / MENA 市场曝光。
双语（English / العربية RTL）+ GEO（Generative Engine Optimization，面向 AI 爬虫 + 传统 SEO）双优化，
覆盖 Hala IP、产品页、博客内容营销、GCC 5 国着陆页。

## 当前阶段

- **阶段**：内容运营 + GEO SEO 迭代中
- **进度**：GEO Phase 2+3 已落地（博客扩充 2900+ 字 + GCC 5 国着陆页 + llms.txt 更新）；robots.txt 已扩展到 40+ AI 爬虫覆盖全平台
- **下一里程碑**：博客持续填充 + Arabic 内容扩展 + 性能与 schema 持续打磨

## 工具栈

- **静态站生成**：Hugo（`hugo.toml`，双语 contentDir `content/en` + `content/ar` RTL）
- **部署**：GitHub Actions（`.github/workflows/deploy.yml`）→ 推测发布到 Pages / Vercel / Netlify（看 workflow 详情）
- **域名 / 邮箱**：`musetrendytoy.com` / `musetrendytoy@gmail.com` / WhatsApp `+971 55 567 1672`
- **关键 skill**：`agent-browser`（页面验证）/ `image-generation`（OG 图 + Hero 图）/ `lark-cli`（飞书同步素材）
- **语言/扩展**：Markdown + Goldmark（unsafe HTML）+ Hugo templates；输出 HTML + RSS；taxonomy = categories / tags

## 关键文件

| 类别 | 路径 | 用途 |
|------|------|------|
| 配置 | `hugo.toml` | 双语 + sitemap + permalinks + outputs |
| 内容 | `content/en/`、`content/ar/` | 英文 + 阿拉伯文页面源（products / blog / hala / collaboration / custom） |
| 模板 | `layouts/_default/`、`layouts/blog/`、`layouts/products/`、`layouts/hala/` | Hugo 模板 |
| 部分页 | `layouts/partials/` | Header / Footer / SEO meta / hreflang |
| 静态资源 | `static/` | 图片 / robots.txt / 字体 |
| 部署 | `.github/workflows/deploy.yml` | GitHub Actions 构建 + 发布 |
| 合同档 | `contracts/MUSE-PO-2026-001-采购合同-草稿.docx` | 采购合同（未提交，需评估去向） |

## 下一步 todo

- [ ] 决定 `contracts/` 目录是否纳入 git（当前为草稿合同，可能属敏感文档应保留本地）
- [ ] 阿拉伯文博客持续翻译（当前 5 篇已 commit `b8f206e`）
- [ ] 跟进 GEO 效果（AI 爬虫覆盖 + llms.txt + schema）
- [ ] 持续填充 GCC 5 国着陆页内容（沙特 / 卡塔尔 / 巴林 / 阿曼 / 科威特）
- [ ] 与 openclaw 机器人内容 pipeline 联动：社媒帖子引流到对应 blog 详情页

## 协作

- **业务区文档**：`[[01-muse-project/muse_web_system]]`（官网+后台系统链接、架构、部署）
- **关联 agent**：Claude（人工编辑 + 设计）/ openclaw 机器人（内容生产 + 引流）
- **关联铁律**：
  - 🚨 P0：[[feedback_hugo_seo_rules]] — YAML 引号转义 / SERP 只数 http / 新建站必须 robots.txt
  - 🚨 P0：MEMORY 设计铁律 — 任何视觉/排版任务必须先读 `design_mideast_luxury_aesthetic.md`
- **关联 PROJECT 上下游**：
  - 上游内容素材：`~/cowork/openclaw 机器人/内容素材/`（产品白底图 + 品牌资产）
  - 上游业务 IP：`~/cowork/hala 素材资产/`（Hala IP 素材库）
  - 下游营销：`~/cowork/openclaw 机器人/`（社媒帖子引流回官网）
  - 客户工具入口：`~/cowork/brand-bible-engine/`（品牌问卷调研，挂在官网某入口）
