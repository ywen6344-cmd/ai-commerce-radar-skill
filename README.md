# AI Commerce Radar Skill

面向 AI、科技与跨境电商研究的 Agent Skill，用于追踪一手信息源、评估信息价值，并把高价值信号转化为可验证的业务机会。

## 这个项目是什么

`ai-commerce-radar` 是一个可复用的 Agent Skill，适合用于生成：

- AI + 跨境电商每日简报
- 跨境电商每周信息速递
- 重大平台/政策更新快讯
- 信息源审计
- 业务机会假设
- AI 电商趋势判断

它不是普通新闻聚合器，而是一套“信息筛选 + 可信度判断 + 业务机会提炼”的工作流。

核心目标是：

```text
更早发现 AI、平台规则、跨境政策、广告流量、商品目录、合规变化中蕴含的业务机会。
```

## 适合谁用

这个 skill 适合：

- 跨境电商卖家
- 独立站运营者
- AI 工具创业者
- 行业研究员
- 跨境服务商
- 关注 AI + 电商机会的人

尤其适合想长期追踪这些方向的人：

```text
AI 购物
Agentic Commerce
Amazon / Shopify / TikTok Shop
Google Merchant Center
YouTube Shopping
平台规则变化
关税、VAT、海关、合规
AI 商品内容生成
AI 商品目录与 feed 优化
跨境卖家运营自动化
```

## 它能做什么

这个 skill 会帮助 agent：

1. 优先使用一手信息源  
   包括官方 changelog、平台公告、API 文档、政策文件、投资者关系页面、监管机构页面等。

2. 给每条信息打分  
   按相关性、来源可信度、新鲜度、业务影响、可验证性进行评分。

3. 区分事实和线索  
   社交媒体、社区讨论、转述内容只能作为线索，不能直接写成结论。

4. 输出结构化简报  
   包括每日简报、每周信息速递、快讯、源池审计等。

5. 沉淀业务假设  
   把高价值信号转化为可验证的业务方向，比如 MVP、目标用户、痛点、验证方式等。

## 仓库结构

```text
ai-commerce-radar-skill/
  README.md
  USAGE.md
  CHANGELOG.md
  .gitignore
  ai-commerce-radar/
    SKILL.md
    agents/
      openai.yaml
    references/
      source-map.md
      scoring-rules.md
      report-templates.md
      business-hypothesis-template.md
```

## 安装到 Hermes

将 `ai-commerce-radar` 文件夹复制到 Hermes 的用户 skills 目录。

Windows 示例：

```powershell
Copy-Item -Recurse -Force .\ai-commerce-radar "$env:LOCALAPPDATA\hermes\skills\research\ai-commerce-radar"
```

然后验证：

```powershell
hermes skills list
```

如果安装成功，你应该能看到类似结果：

```text
ai-commerce-radar | research | local | local | enabled
```

启动 Hermes 时也可以显式预加载：

```powershell
hermes -s ai-commerce-radar
```

## 安装到 Codex

将 `ai-commerce-radar` 文件夹复制到 Codex skills 目录。

Windows 示例：

```powershell
Copy-Item -Recurse -Force .\ai-commerce-radar "$env:USERPROFILE\.codex\skills\ai-commerce-radar"
```

复制后建议新开一个 Codex 会话，让 skill 列表刷新。

## 使用示例

生成每日简报：

```text
使用 ai-commerce-radar，生成今天的 AI + 跨境电商日报。
```

生成每周信息速递：

```text
使用 ai-commerce-radar，基于过去一周信息生成跨境电商每周信息速递，并输出 3 个可验证业务机会。
```

生成快讯：

```text
使用 ai-commerce-radar，判断这条 TikTok Shop 政策更新是否需要生成快讯，并说明对卖家的影响。
```

审计信息源：

```text
使用 ai-commerce-radar，审计我的信息源池，指出 AI、跨境平台、政策合规、市场信号各自缺哪些一手源。
```

转化为业务假设：

```text
使用 ai-commerce-radar，把这条 Shopify / Amazon / TikTok Shop 更新转成一个可验证的业务假设。
```

## 信息评分逻辑

每条信息满分 100 分：

```text
相关性：0-25
来源可信度：0-25
新鲜度：0-20
业务影响：0-20
可验证性：0-10
```

进入规则：

```text
90-100：快讯或业务假设候选
80-89：进入每日简报
60-79：入库，周度复盘
60 以下：忽略或仅保留为线索
```

## 可信度分级

```text
S 级：官方原文
政策文件、平台公告、API changelog、财报、监管文件、法院/海关/税务文件。

A 级：直接当事人
公司高管、产品负责人、开源维护者、卖家后台通知截图、平台员工公开说明。

B 级：高质量二手源
研究机构、垂直媒体、专业分析师、行业报告。

C 级：社媒与社区线索
X/Twitter、Reddit、微信群、公众号、短视频、群聊转述。
```

规则：C 级信息只能作为线索，不能直接进入结论。重要判断必须回溯到 S/A 级来源。

## 推荐工作流

每日：

```text
1. 收集新增信息
2. 去重
3. 按可信度和业务影响评分
4. 生成 5-10 条简报
5. 将高价值信息转成业务假设
```

每周：

```text
1. 复盘过去一周高分信号
2. 找出重复出现的主题
3. 更新趋势判断
4. 更新业务假设库
5. 选择 1 个方向做验证
```

每月：

```text
1. 输出趋势判断
2. 选择 1-2 个业务方向
3. 做访谈、落地页、手工服务或小工具验证
```

## 更新维护

建议定期维护这些文件：

```text
references/source-map.md
新增或删除信息源。

references/scoring-rules.md
调整评分权重和进入门槛。

references/report-templates.md
优化日报、周报、快讯格式。

references/business-hypothesis-template.md
新增、强化或删除业务假设。
```

## 隐私注意事项

请不要把以下内容提交到仓库：

```text
API keys
cookies
tokens
auth.json
.env
付费数据库账号
私人卖家后台截图
未公开商业计划
```

如果后续接入 Notion、Telegram、邮箱、数据库或模型 API，请把密钥放在本地配置或环境变量中，不要写进仓库。

## 当前版本

```text
0.1.0
```

初始版本包含：

- 信息源地图
- 可信度分级
- 100 分评分规则
- 日报 / 每周信息速递 / 快讯模板
- 业务假设模板
- 初始 AI + 跨境电商机会方向
