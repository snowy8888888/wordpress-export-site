# 询盘、邮件来源与 SEO 验收

## 询盘配置

Elementor 免费版可用 Contact Form 7：姓名、邮箱、国家/地区、公司、电话/WhatsApp、型号、预计数量、合作类型和需求。必填数量适度，接受同意文字与实际用途一致。详情页 Request a Quote 通过查询参数预填型号，必要时保存来源页；Thank You noindex，并保留继续查看产品或 WhatsApp 的入口。

Contact Form 7 负责收集字段、验证并调用 WordPress 邮件发送。Flamingo 保存询盘供后台查看/导出；它不是发信邮箱，也不保证邮件投递。Elementor 是页面编辑器，WordPress/Elementor MCP 是建站操作通道；它们不自动赋予访问 Gmail、Outlook 或其他邮箱的权限。

明确记录地址来源：

| 配置 | 作用 | 需核对 |
|---|---|---|
| Mail To / recipient | 业务收到询盘的目标 | 采用用户指定业务邮箱；检查是否仍是 `[_site_admin_email]` |
| Mail From / sender | 发件身份 | 采用站点域名允许的身份，与实际邮件服务一致 |
| Reply-To | 回复客户的地址 | 采用已验证的访客邮箱字段，不把客户地址伪造成 From |
| Mail (2) | 可选的访客自动回复 | 无需求则不启用，避免额外投递 |
| WordPress admin_email | 网站原有管理通知地址 | 可能与业务邮箱不同，不能悄悄当作新询盘收件人 |
| 邮箱别名/转发规则 | 决定最终投递位置 | 不可仅从 WordPress 配置推断已存在或已开启 |

WhatsApp 使用 `https://wa.me/国家码加号码`，不含 `+` 或空格。可预填型号与简单英文消息，不在 URL 放客户个人信息。

## 用户收到意外邮箱邮件时

先承认具体问题，检查当前及旧表单收件人、Mail (2)、WordPress 管理员邮箱、已安装 SMTP/转发插件，以及已存在的测试记录。只读必要配置，遮住私有邮箱。不要由本机目录 `/Users/某名字`、账号名称或邮箱显示名推断邮箱地址。

需要追溯一封邮件时请用户提供主题、发件人、To，以及必要的原始邮件头。`To` 是可见收件字段，最终投递可由转发、别名、BCC 或主机中继改变；用 Delivered-To、X-Original-To、Received、Message-ID 及主机日志交叉判断。没有这些证据时报告配置事实与未知项，不说“肯定是转发”。不要未经授权登录用户邮箱、发送新测试或修改 Gmail/Outlook 规则。

验收分三层：表单验证正确；CF7 返回 mail_sent 且 Flamingo 有记录；用户目标邮箱实际收到并可回复。前两层通过仍不能证明第三层。SMTP 凭据必须真实授权，不猜测密码；需要稳定投递时根据实际邮件服务的官方设置配置 SMTP，并检查相关 SPF/DKIM/DMARC，但不为了修表单擅改整个域名 DNS。

## SEO 实施

1. 正式域名/HTTPS、静态首页、语言、友好链接、robots 与 WordPress `blog_public`。未登录访问不能全站 noindex，临时预览的 noindex 正常。
2. 每个可索引页面有独立 title、描述、正式 canonical、准确 H1、分享标题/图。产品名称与型号明确，描述自然，不堆叠关键词。图片 alt 说明对象，装饰图片按用途留空。
3. 链接不残留 preview/token/nonce；导航、卡片、询盘查询参数、目录 PDF 均可访问。公开产品卡片不指向草稿 404。
4. 用已有 SEO 插件生成 WebSite/Organization/WebPage/Breadcrumb 等支持的结构。Product 可补充真实型号、品牌、图片与描述；不编造 offers、价格、库存或评价以追求富媒体结果。用 JSON 解析检查 schema 语法，避免重复矛盾信息。
5. Sitemap 仅包含适合索引的公开内容。感谢页、空模板、无内容的分类/作者档案及不相关默认页面可 noindex。不要为了清 sitemap 就批量删除、退回草稿或改 slug；先检查是否在使用，以及插件的 noindex 排除机制。页面 noindex 与 robots disallow 不等价。
6. 未确认/隐藏型号维持草稿或已有授权的隐藏状态，清除公开卡片与索引路径。不同型号的认证不能无依据互相继承。
7. 大图保留比例并压缩，LCP 首屏图不滥用 lazy load；其他图片按需加载。根据 PageSpeed 的实际建议优化缓存、字体、CSS/JS，功能回归通过后再接受新设置。
8. 分别记录 PageSpeed 手机/桌面分数、关键指标、测试时间和报告链接。实验室高分不等于真实用户 Core Web Vitals 已通过；没有 CrUX 数据就注明。API 无配额可使用官方 UI，不虚构结果。

## 站长工具与交付边界

Google Search Console 需要用户可用的 Google 账号及网站所有权验证。可先完成网站内 SEO、准备 sitemap，再让用户登录或提供 HTML 验证标签/DNS 记录。优先匹配当前用户选定域名；未完成验证/提交就不声称已提交或已收录，提交也不保证收录时间和排名。

交付核验表至少包含：公开页面 HTTP 状态、title/description/canonical、H1 数量、robots/noindex、分享图、schema 解析、坏链数量、sitemap 实际 URL 集、要求隐藏的型号是否泄漏、表单/WhatsApp/PDF 功能、响应式截图、性能前后结果、Google/隐私/邮箱剩余事项。

技术行为需核实当时安装的版本与官方文档，不把这里的产品版本当作最新版本：

- [Contact Form 7 邮件设置](https://contactform7.com/setting-up-mail/)
- [Flamingo 保存消息](https://contactform7.com/save-submitted-messages-with-flamingo/)
- [Slim SEO Sitemap](https://docs.wpslimseo.com/slim-seo/xml-sitemap/)
- [Google Sitemap 提交](https://developers.google.com/search/docs/crawling-indexing/sitemaps/build-sitemap)
- [Google noindex](https://developers.google.com/search/docs/crawling-indexing/block-indexing)
