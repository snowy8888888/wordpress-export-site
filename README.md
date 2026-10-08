# WordPress 外贸官网建站 Skill

面向外贸人和建站助手的可复用工作流程：用 **WordPress + Elementor** 制作产品展示、公司介绍和询盘官网，支持 Elementor 免费版。

A reusable AI skill for building editable WordPress export-business websites with Elementor, product pages, inquiry forms, catalog downloads and SEO checks.

## 下载

- **[下载可安装 Skill ZIP](wordpress-export-site-skill.zip?raw=1)**：解压后得到 `wordpress-export-site` 文件夹。
- 完整仓库：点击本页绿色 **Code → Download ZIP**。
- **[先看初始 Prompt 与问题清单](wordpress-export-site/references/starter-prompts.md)**。

## 适合谁

希望面向海外客户展示产品、介绍公司、收集询盘的外贸企业、OEM/ODM 供应商、批发商及建站服务人员。品牌、产品、市场、语言、邮箱、WhatsApp、域名和认证均使用每个项目自己的资料。

## 包含哪些流程

- 需求收集、页面结构、素材与产品目录整理。
- WordPress/Elementor MCP 连接验证和凭据处理。
- Elementor 原生可编辑页面、产品详情、可 Save as Template 的页眉页脚。
- 产品原图与安装/使用场景图的选择，产品外形和比例检查。
- 询盘表单、业务收件邮箱、WhatsApp、型号预填和目录 PDF 下载。
- 邮箱来源排查，分别验证表单成功、询盘保存与实际收到邮件。
- SEO 标题、描述、canonical、分享图、结构化数据、sitemap 与收录设置。
- 桌面和手机检查、正式发布验证、缓存、备份与维护交付。

## 在 Codex 中安装

1. 下载并解压 Skill ZIP。
2. 将整个 `wordpress-export-site` 文件夹放入你的技能目录：
   - macOS / Linux：`~/.codex/skills/wordpress-export-site/`
   - Windows：`%USERPROFILE%\.codex\skills\wordpress-export-site\`
   - 自定义 `CODEX_HOME` 的用户：`$CODEX_HOME/skills/wordpress-export-site/`
3. 确认 `SKILL.md` 直接位于该文件夹中，不要多套一层同名目录。
4. 在下一轮对话使用 `$wordpress-export-site`。若客户端仍未识别，重新打开会话并检查技能目录。

也可以把本仓库中 `wordpress-export-site` 文件夹的 GitHub 链接交给 Codex，要求安装这个 skill。

## 最初始 Prompt

复制下面内容开始。AI 会根据已知资料补问关键问题，不需要先知道所有建站术语。

```text
我在做外贸，想做一个面向海外客户的官网，用来展示产品、介绍公司和收集询盘。

请使用 $wordpress-export-site 帮我完成建站。网站使用 WordPress，页面要能用 Elementor 编辑器继续修改；我的 Elementor 版本如果不清楚，请先问我。不要默认购买 Pro 或加入购物结账。

先根据我已有的信息问必要问题，帮助我明确品牌、产品、目标市场、客户、网站语言、合作方式、联系方式和素材。可以把问题分成少量几组，用我容易理解的中文询问，告诉我哪些可以稍后补充。

得到基本资料后，请先整理网站需求和页面结构，再实际制作可编辑页面、产品详情、询盘表单、WhatsApp、目录下载及基础 SEO。需要连接网站时告诉我应该提供什么访问方式；账号密码通过安全连接配置处理，不写进网站内容、报告或这个 skill。

完成后测试桌面和手机、正式页面链接、表单与目录下载，交付编辑入口、维护说明和备份。不要虚构产品参数、认证、客户案例、价格、工厂规模或 SEO 收录结果。我的联系方式必须使用我本次提供的资料。
```

已有公司资料时，用 **[可填写的完整 Prompt](wordpress-export-site/references/starter-prompts.md)**；同一文件还提供分阶段需求问题。

## 用在其他 AI 工具

如果工具不支持安装 Codex skills，可把 [SKILL.md](wordpress-export-site/SKILL.md) 和所需 `references` 文件提供给它，并把开场句改成“请作为 WordPress 外贸官网建站助手帮我完成下面任务”。工具需要自己具备 WordPress 访问、页面编辑及所需图像处理能力。

这个下载包提供工作流程和提示词。WordPress 网站、Elementor、MCP 服务端及业务邮箱由每位使用者配置；下载 skill 不会自动连接网站、安装插件或获得账户权限。Elementor 免费版保存后插入的模板通常是副本，后续是否同步取决于网站采用的模板机制。

## 文件导航

| 文件 | 用途 |
| --- | --- |
| [SKILL.md](wordpress-export-site/SKILL.md) | 技能入口、实施原则与交付要求 |
| [build-workflow.md](wordpress-export-site/references/build-workflow.md) | 从需求到上线的完整流程 |
| [elementor-mcp.md](wordpress-export-site/references/elementor-mcp.md) | 连接、免费版模板、编辑、缓存与恢复 |
| [inquiries-seo.md](wordpress-export-site/references/inquiries-seo.md) | 询盘投递排查和 SEO 验收 |
| [starter-prompts.md](wordpress-export-site/references/starter-prompts.md) | 最初始 Prompt、填写模板和需求问题 |
| [agents/openai.yaml](wordpress-export-site/agents/openai.yaml) | Codex 技能显示信息 |

分享版全部使用通用参数。请通过自己的安全连接提供账号凭据，不要将客户资料、真实密码、私有询盘记录放到公开仓库或 Issues。
