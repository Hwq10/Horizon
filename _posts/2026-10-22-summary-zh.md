---
layout: default
title: "Horizon Summary: 2026-10-22 (ZH)"
date: 2026-10-22
lang: zh
---

> 从 37 条内容中筛选出 15 条重要资讯。

---

**科技新闻**
1. [David Harvey 分析新提出的 o\(n log n\) 整数乘法算法](#item-tech-news-1) ⭐️ 8.0/10
2. [PHP 8.x 紧急发布安全更新修复高危远程代码执行漏洞](#item-tech-news-2) ⭐️ 8.0/10
3. [SemiAnalysis 剖析华为升腾 950PR 与 DeepSeek 适配](#item-tech-news-3) ⭐️ 8.0/10
4. [公共递归解析服务 Quad9 宣布退出法国市场](#item-tech-news-4) ⭐️ 7.0/10
5. [eMudhra 宣布退出全球 SSL/TLS 证书业务](#item-tech-news-5) ⭐️ 7.0/10
6. [Anthropic 推出个人助手产品 Claude Duet](#item-tech-news-6) ⭐️ 7.0/10
7. [新型算法实现 489 毫秒三角剖分 370 万个地图多边形](#item-tech-news-7) ⭐️ 7.0/10
8. [趋势科技误将多项未修补 Linux 内核高危漏洞公开至 LKML](#item-tech-news-8) ⭐️ 7.0/10
9. [亚马逊威胁情报在公开披露前捕获 PHP2Shell 在野利用](#item-tech-news-9) ⭐️ 7.0/10
10. [Railway 发布安全通报：客户环境变量泄露并暂停部署构建](#item-tech-news-10) ⭐️ 7.0/10
11. [开源模型 Carbon-X 支持 DNA 与文本联合推理](#item-tech-news-11) ⭐️ 7.0/10
12. [澳洲法院裁定苹果须向第三方应用商店和侧载开放 iPhone](#item-tech-news-12) ⭐️ 7.0/10
13. [研究发现部分智能电视关闭自动内容识别后仍明文上报观看数据](#item-tech-news-13) ⭐️ 7.0/10
14. [米哈游联合清华大学等开源 GameScaling 游戏操作模型](#item-tech-news-14) ⭐️ 7.0/10
15. [甲骨文修复 Java SE 与 GraalVM 高危漏洞 CVE-2026-91403](#item-tech-news-15) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [David Harvey 分析新提出的 o\(n log n\) 整数乘法算法](https://web.maths.unsw.edu.au/~davidharvey/research/subnlogn.pdf) ⭐️ 8.0/10

数学家 David Harvey 发布研究论文，对近期提出的复杂度达 o\(n log n\) 的整数乘法算法进行了理论分析。该成果打破了此前普遍达到的 O\(n log n\) 渐近复杂度界限，将理论运算时间进一步推进至严格小于 n log n 的“小 o”量级。由于原始论证极其繁复，理论计算机与数学界正聚焦于验证其证明细节的完整性与边界条件。

hackernews · craigcitro · 10月22日 02:30 · [社区讨论](https://news.ycombinator.com/item?id=50190455)

**「研究背景」** 1971 年，Schönhage 与 Strassen 证明了整数乘法可在 $O\(n \\log n \\log \\log n\)$ 时间内完成，并猜想 $O\(n \\log n\)$ 才是真正的复杂度极限。2021 年，David Harvey 与 Joris van der Hoeven 在《数学年刊》正式发表论文，实现了 $O\(n \\log n\)$ 复杂度的整数乘法算法，确立了当时理论计算机科学界的最高纪录。

**「社区讨论」** 社区讨论中，研究者 jdb1729 表示已与协作者在 Lean 交互式定理证明器中完成了该结果的形式化验证，并正在开源仓库中持续改进指数常数。同时，读者也关注到作者在论文中提及人工难以快速消化原始推导、转而借助大语言模型辅助解析长篇数学证明的现象。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://hal.science/hal-02070778v2/file/nlogn.pdf">Integer multiplication in time O(n log n) - hal.science</a></li>
<li><a href="http://www.mmrc.iss.ac.cn/~xgao/cls2023/pap21-IntMult.pdf">Integer multiplication in time O(n log n) - mmrc.iss.ac.cn</a></li>

</ul>
</details>

**标签**: `#algorithms`, `#theoretical computer science`, `#computational complexity`, `#formal verification`

---

<a id="item-tech-news-2"></a>
### [PHP 8.x 紧急发布安全更新修复高危远程代码执行漏洞](https://simonwillison.net/2026/Oct/21/php-security-release/) ⭐️ 8.0/10

PHP 基金会针对整个 PHP 8.x 分支紧急推送安全修复补丁，解决两个实际 CVSS 评分为 9.2 的远程代码执行（RCE）高危漏洞。该漏洞由 Wiz Research 等机构发现，并已在 WordPress 与 Drupal 等环境下验证了未授权远程执行利用；由于披露流程中发生 CVE 信息泄露及安全机构误发概念验证（PoC）视频，促使利用代码加速扩散，官方遂将发布时间由原定的 10 月 22 日提前至 21 日。目前相关漏洞利用程序已在公开网络流传，官方建议所有运行 PHP 8.x 的生产环境立即完成版本升级。

rss · Simon Willison · 10月21日 18:41

**「背景」** Wiz Research 于 2026 年 8 月发现了影响 PHP 的远程代码执行漏洞，并在确认其可针对 WordPress 与 Drupal 等主流系统实现未授权利用后，向 PHP 安全团队提交了协调披露报告。按照原定计划，漏洞修补版本与安全公告应于 10 月下旬发布，但漏洞编号外泄以及安全机构误发概念验证（PoC）演示视频打乱了披露节奏，导致在官方发布补丁前利用代码已开始流传。

**「影响与应对」** 运行 PHP 8.x 的系统管理员与开发者需要立即升级至最新的安全修复版本。由于漏洞的概念验证利用代码已在公开流传，且已证实可在无需认证的情况下对 WordPress 和 Drupal 等主流应用实现远程代码执行，未修补的服务器面临被攻击者直接接管的高危风险。

**标签**: `#php`, `#security`, `#vulnerabilities`, `#remote-code-execution`

---

<a id="item-tech-news-3"></a>
### [SemiAnalysis 剖析华为升腾 950PR 与 DeepSeek 适配](https://newsletter.semianalysis.com/p/huawei-deepseek) ⭐️ 8.0/10

SemiAnalysis 发布了针对华为与 DeepSeek 技术协同生态的深度分析报告，公布了华为升腾 950PR（Ascend 950PR）加速器的微基准测试数据。该报告同时涵盖了对 DSv4.1 Flash 的架构分析，并系统评估了 DeepSeek 系列模型对升腾硬件平台的支持与适配情况。

rss · Semianalysis · 10月21日 17:34

**「背景」** DeepSeek 与华为在软硬件体系上保持深度协同，DeepSeek 直接向华为提供模型权重以实现 DeepSeek V4 及 V4.1 的首日优化适配。与此同时，升腾芯片特有的累加器硬件设计也促使开发团队对注意力机制等核心算子采取了专门的架构调整方案。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://newsletter.semianalysis.com/p/huawei-deepseek">The Huawei - DeepSeek Symbiosis</a></li>

</ul>
</details>

**标签**: `#AI Hardware`, `#Huawei Ascend`, `#DeepSeek`, `#Microbenchmarks`, `#Semiconductors`

---

<a id="item-tech-news-4"></a>
### [公共递归解析服务 Quad9 宣布退出法国市场](https://quad9.net/news/blog/au-revoir-france/) ⭐️ 7.0/10

公共 DNS 递归解析服务 Quad9 宣布计划退出法国市场，停止在法国境内的相关运营。该决定源于其在当地面临的持续法律诉讼以及法院强制执行的内容拦截禁令，使该非营利服务难以承受合规与法律责任负担。此举意味着法国境内的用户将无法直接依靠其本地节点使用 Quad9 的安全与隐私解析服务。

hackernews · farrokhi · 10月22日 14:32 · [社区讨论](https://news.ycombinator.com/item?id=50195959)

**「背景」** Quad9 是一家主打安全与隐私保护的非营利性公共递归 DNS 解析服务商。此前，法国广播公司 Canal+ 为打击体育赛事侵权直播，通过法国法院针对 Google、Cloudflare 以及 Quad9 等多家公共 DNS 服务商申请并推行了强制域名屏蔽禁令。

**「影响」** 法国境内的终端用户与网络管理员将无法继续依赖 Quad9 在当地的基础设施进行域名解析，需手动迁移至其他公共 DNS 解析器或当地受监管的解析服务。

**「社区讨论」** 社区讨论普遍批评针对 DNS 基础服务商的司法封锁要求过于严苛，指出即便服务商部署了基于地理位置的屏蔽措施，原告通过 VPN 绕过封锁依然导致解析商被判违规受罚。部分评论还提到，Quad9 的撤退与此前思科旗下 OpenDNS 因应对版权封锁禁令而退出法国市场的策略如出一辙。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://completemusicupdate.com/quad9-vows-to-fight-absurd-web-block-injunction-in-france/">Quad 9 vows to fight “absurd” web- block injunction in France</a></li>
<li><a href="https://quad9.net/">Quad 9 | A public and free DNS service for a better security and privacy</a></li>

</ul>
</details>

**标签**: `#DNS`, `#internet infrastructure`, `#networking`, `#tech policy`

---

<a id="item-tech-news-5"></a>
### [eMudhra 宣布退出全球 SSL/TLS 证书业务](https://emudhra.com/en/press-release/emudhra-to-exit-global-ssl-tls-certificate-business) ⭐️ 7.0/10

数字证书认证机构 eMudhra 正式宣布退出全球 SSL/TLS 证书业务。在此之前，该机构因私钥安全防护实践存在缺陷，面临着来自安全社区与各大主流浏览器厂商的信任调查及质询。eMudhra 在声明中表示其全球 SSL/TLS 基础设施与其它业务彼此隔离，并认为外界舆论对此事的关注程度已脱离该业务在其整体业务体系中的实际比重。

hackernews · bo0tzz · 10月22日 13:33 · [社区讨论](https://news.ycombinator.com/item?id=50195110)

**「背景」** eMudhra 是一家主营数字签名、电子签署及企业级公钥基础设施（PKI）解决方案的印度服务商，此前亦作为受信任的证书颁发机构（CA）运营全球 SSL/TLS 证书签发业务。在决定退出该业务之前，该公司因私钥安全隐患与相关漏洞遭到披露，并面临主流浏览器厂商针对其根证书信任资质的严格安全审查与公开质询。

**「影响」** 受私钥泄露以及 Chrome、Firefox 等主流浏览器紧急封锁相关证书的影响，持有 eMudhra 签发证书的网站及企业需要紧急迁移更换约 30,000 张数字证书，否则将在主流浏览器和依赖系统信任库的非浏览器客户端（如 Go、certifi 等）中面临连接失败与访问中断风险。

**「社区讨论」** 社区用户普遍批评 eMudhra 试图淡化事故严重性且未公开事故根本成因，同时讨论还指出了各大平台在吊销受影响中间证书时响应效率差距悬殊，有用户反映 Chrome 迅速完成处置，而部分移动端根证书库在事故披露数日后仍处于信任状态。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://emudhra.com/en/press-release/emudhra-to-exit-global-ssl-tls-certificate-business">eMudhra to Exit global SSL / TLS Certificate Business</a></li>
<li><a href="https://www.marketscreener.com/news/india-s-emudhra-to-exit-global-ssl-tls-certificate-business-ce785cdedb8af125">India&#x27;s eMudhra to exit global SSL / TLS certificate business</a></li>
<li><a href="https://cyberinsider.com/google-apple-mozilla-rush-to-block-compromised-emudhra-certificates/">Google, Apple, Mozilla rush to block compromised eMudhra ...</a></li>
<li><a href="https://www.rescana.com/post/emudhra-intermediate-ca-key-compromise-october-2026">eMudhra CA Key Compromise: Chrome and Firefox Have Blocked It ...</a></li>

</ul>
</details>

**标签**: `#cybersecurity`, `#pki`, `#ssl-tls`, `#web-infrastructure`, `#cryptography`

---

<a id="item-tech-news-6"></a>
### [Anthropic 推出个人助手产品 Claude Duet](https://claude.com/product/claude-duet) ⭐️ 7.0/10

Anthropic 上线了名为 Claude Duet 的个人助手产品页面并开放候补名单申请。该产品旨在利用前沿模型能力提供深度助理服务，但官方目前尚未公布完整的技术架构细节及正式面向所有用户的上线时间表。

hackernews · kuberwastaken · 10月21日 19:14 · [社区讨论](https://news.ycombinator.com/item?id=50186037)

**「背景」** Anthropic 推出的 Claude Duet 是一款主动型智能体应用，支持用户通过文字或语音交互并在连接的第三方应用中协同执行任务，针对发送消息、签署文件或支付等关键操作设计了主动确认机制。该研究预览版目前面向美国市场的 Pro 和 Max 订阅用户开放候补名单，被视为主流大模型厂商在个人 AI 助理领域的又一竞品布局。

**「社区讨论」** 社区用户对候补名单申请未能直接打通现有 Claude 账户体系的繁琐交互表达了不满。此外，有开发者讨论指出，个人助理的异步任务特性允许模型提供商采用低优先级批处理来调度算力，从而显著优化推理成本与利用率。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://claude.com/resources/articles/claude-duet">Introducing Claude Duet | Claude by Anthropic</a></li>
<li><a href="https://support.claude.com/en/articles/17631495-get-started-with-claude-duet">Get started with Claude Duet | Claude Help Center</a></li>
<li><a href="https://www.engadget.com/2293646/claude-duet-is-anthropics-answer-to-meta-muse-and-openai-dots/">Claude Duet is Anthropic&#x27;s answer to Meta Muse and OpenAI ...</a></li>

</ul>
</details>

**标签**: `#artificial intelligence`, `#anthropic`, `#claude`, `#ai assistants`, `#llms`

---

<a id="item-tech-news-7"></a>
### [新型算法实现 489 毫秒三角剖分 370 万个地图多边形](https://globus.software/blog/2026/10/16/cutting-map-polygons/) ⭐️ 7.0/10

Globus 团队公布了一项高吞吐的多边形三角剖分优化方案，测试显示其能够在 489 毫秒内完成 370 万个地图多边形的三角剖分，处理速度显著超越业界通用的开源库 Earcut。该方案主要针对大规模地理矢量数据的预处理与图形渲染管线进行优化，大幅降低了大规模面要素几何剖分的时间开销。不过，该算法实现目前更侧重处理速度，生成的三角形拓扑质量与极端几何形状仍是实际应用中需要权衡的因素。

hackernews · molind · 10月22日 09:31 · [社区讨论](https://news.ycombinator.com/item?id=50193170)

**「背景」** 在矢量地图渲染与计算机图形学中，将多边形快速剖分为三角形是供 GPU 进行栅格化显示的关键环节，轻量级开源算法库 Earcut 长期以来是该领域的通用基准方案。Globus Software 随后将其自研地图引擎的核心多边形三角剖分模块提取为独立库 earstrip，并采用与 Earcut 相同的 ISC 许可证开源。

**「性能与应用影响」** 对于需要在 WebAssembly 环境下处理海量地图多边形的开发者，earstrip 提供了更显著的跨平台性能优势：原生环境下 earcut.hpp 比 earstrip 慢 14%，而编译至 WebAssembly 并在 V8 引擎运行时，earstrip 仅损耗 23% 的性能，远低于 earcut.hpp 因耳切搜索循环瓶颈而导致的 67% 性能下降，能大幅减少浏览器端地理数据剖分的延迟 \[tool-2-1\]。

**「社区讨论」** Earcut 原作者在讨论中表示，Earcut 是为了控制 Web 端的打包体积（压缩后约 4.1 KB）而特意放弃了部分深度优化，并对新方案编译为 WebAssembly 后的体积表现表示好奇。同时有开发者指出，基准测试生成的网格中包含大量细长三角形，这类狭长图元在 GPU 光栅化阶段往往属于极低效的极端情况。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://globus.software/blog/2026/10/16/cutting-map-polygons/">Faster than earcut: triangulating 3 . 7 M map polygons in... | GLOBUS</a></li>
<li><a href="https://globus.software/blog/2026/10/16/cutting-map-polygons/">Faster than earcut : triangulating 3.7M map polygons in... | GLOBUS</a></li>

</ul>
</details>

**标签**: `#computational-geometry`, `#algorithms`, `#performance-optimization`, `#graphics-programming`

---

<a id="item-tech-news-8"></a>
### [趋势科技误将多项未修补 Linux 内核高危漏洞公开至 LKML](https://www.phoronix.com/news/LKML-New-Trend-Vulnerabilities) ⭐️ 7.0/10

趋势科技旗下的漏洞挖掘项目 Zero Day Initiative（ZDI）意外将多份未修补的 Linux 内核漏洞报告直接发送至公开的 Linux 内核邮件列表（LKML），而非保密的内核安全邮件渠道。泄露的报告涉及 CVSS 评分最高达 9.0 的高危缺陷，涵盖内核态 SMB 与 KSMBD 实现以及本地提权（LPE）漏洞。由于这些漏洞在补丁发布前即被全网公开，导致相关实现面临即时的零日漏洞暴露风险。

hackernews · mrkn1 · 10月22日 11:12 · [社区讨论](https://news.ycombinator.com/item?id=50193804)

**「背景」** 按照 Linux 内核社区的标准漏洞披露流程，未修补的安全漏洞通常需私下提交至专用的私密安全邮件列表，以便维护者在公开前协调修复方案。相比之下，Linux 内核邮件列表（LKML）是完全公开且被广泛镜像归档的通用开发渠道，任何发送至该列表的内容都会立即进入公众视野。

**「潜在影响」** 运行 Linux 内核内置 SMB 服务 KSMBD 的服务器在主线补丁发布前直接面临零日攻击风险，泄露报告中包含 CVSS 评分为 9.0 且无需网络认证即可触发的远程代码执行漏洞；在官方修复合入前，系统管理员需排查相关服务暴露面，并在必要时禁用 KSMBD 模块或限制外部网络访问。

**「社区讨论」** 社区讨论分析指出，本次泄露中危害最严重的漏洞主要集中在内核级 KSMBD 和 SMB 实现，未启用相关网络文件共享功能的系统风险相对较低。部分开发者还指出该披露行为暴露出提交流程管理不当的问题，并结合趋势科技近期的业务动态推测部分漏洞报告可能与 AI 辅助挖掘流程有关。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.phoronix.com/news/LKML-New-Trend-Vulnerabilities">Several Linux Kernel Vulnerabilities Accidentally ... - Phoronix</a></li>
<li><a href="https://thehackernews.com/2026/10/two-cvss-90-linux-ksmbd-rce-flaws.html">Two CVSS 9.0 Linux KSMBD RCE Flaws Disclosed on Public ...</a></li>

</ul>
</details>

**标签**: `#linux-kernel`, `#cybersecurity`, `#vulnerability`, `#open-source`

---

<a id="item-tech-news-9"></a>
### [亚马逊威胁情报在公开披露前捕获 PHP2Shell 在野利用](https://aws.amazon.com/blogs/security/amazon-threat-intelligence-identifies-php2shell-exploitation-prior-to-public-disclosure-in-madpot/) ⭐️ 7.0/10

亚马逊威胁情报团队（Amazon Threat Intelligence）发布报告称，其 MadPot 蜜网系统在 PHP2Shell 漏洞公开披露前的 10 月 17 日便检测到了针对该漏洞的利用尝试。该情报表明，在安全补丁和公众通报正式发布前，已有威胁行为者掌握了相关利用手法并在野外进行探测。

hackernews · cubefox · 10月22日 11:50 · [社区讨论](https://news.ycombinator.com/item?id=50194070)

**「背景」** PHP2Shell 是指影响 PHP 5.4 至 8.5 版本的两项高危漏洞（CVE-2026-109618 与 CVE-2026-109619），攻击者可借此实现远程代码执行。该漏洞相关信息于 2026 年 10 月 20 日正式公开发布。

**「社区讨论」** 社区讨论集中在这些活动究竟属于有效利用还是单纯的扫描探测，部分安全从业者指出蜜网与服务器日志中多见僵尸网络的盲目扫描尝试，缺乏确认成功的可运行漏洞利用案例；同时，这也引发了围绕漏洞披露时间线以及 Chainguard 和 PHP 官方团队之间禁运协议争议的进一步讨论。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/PHP2Shell">PHP 2 Shell - Wikipedia</a></li>
<li><a href="https://aws.amazon.com/blogs/security/amazon-threat-intelligence-identifies-php2shell-exploitation-prior-to-public-disclosure-in-madpot/">Amazon Threat Intelligence identifies PHP 2 Shell exploitation prior ...</a></li>

</ul>
</details>

**标签**: `#security`, `#vulnerabilities`, `#php`, `#threat-intelligence`

---

<a id="item-tech-news-10"></a>
### [Railway 发布安全通报：客户环境变量泄露并暂停部署构建](https://blog.railway.com/p/security-disclosure-wednesday-october-21st) ⭐️ 7.0/10

云部署平台 Railway 发布安全公告，披露了一起涉及客户环境变量密钥泄露的安全事件。官方在应对处置期间暂停了平台的构建与部署服务。根据公告说明，由于部署功能暂停，用户在官方恢复构建之前无法通过重新部署来让服务加载轮换后的新凭据。

hackernews · passenger · 10月21日 21:58 · [社区讨论](https://news.ycombinator.com/item?id=50188228)

**「背景」** Railway 是一家提供应用托管与快速部署的 PaaS 云基础设施平台，开发者通常在其控制台中集中存储和注入数据库凭证、API 密钥等敏感生产环境变量。在此类托管架构中，环境变量存储的隔离与加密机制直接决定了用户所连接的下游数据库及第三方系统安全。

**「影响与应对」** 使用 Railway 的开发者需要立即轮换存储在平台环境变量中的 API 密钥、数据库凭据等敏感信息并审查调用日志；但由于平台在排查期间暂停了服务构建与部署，用户在功能恢复前无法直接通过重新部署使更新后的凭证生效。

**「社区反馈」** 社区讨论中有用户指出其 Railway 凭据已被未授权第三方实际调用，推测攻击者已能够读取解密后的环境变量。同时有开发者反映，在部署暂停期间按照建议轮换密钥，导致线上服务因无法生效新配置而直接瘫痪。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://thecybersecguru.com/news/railway-security-breach-environment-variables/">Railway Security Breach: API Keys Exposed | The CyberSec Guru</a></li>
<li><a href="https://cybersecuritynews.com/railway-security-incident/">Railway Security Incident: Hackers May Have Accessed Customer ...</a></li>

</ul>
</details>

**标签**: `#cybersecurity`, `#cloud infrastructure`, `#devops`, `#railway`

---

<a id="item-tech-news-11"></a>
### [开源模型 Carbon-X 支持 DNA 与文本联合推理](https://www.reddit.com/r/MachineLearning/comments/1xchayq/carbonx_is_an_open_148b_model_trained_jointly_on/) ⭐️ 7.0/10

Carbon-X 是一款采用 Apache 2.0 许可证开源的 14.8B 参数仅解码器模型，允许用户直接在对话中输入原始 DNA 序列并以英文获取分析结果。该模型采用统一 token 流与 6-mer 编码，在 302B token 上进行了联合中途训练；在关闭思考功能时，其在 5 项 DNA 基准测试上的平均得分为 66.7%，接近 GPT-6.1 Sol 的 67.5%。其 bfloat16 权重可直接载入单张 80 GB GPU 运行，但官方模型卡明确说明该模型未经临床验证，精确的序列操作仍需依赖外部代码处理。

reddit · r/MachineLearning · /u/jatingargiitk · 10月22日 12:32

**「背景」** 在计算生物学中，传统基因组模型多专注于纯序列建模或特定注释任务，直接跨模态通过自然语言对话解析原始 DNA 序列的工具相对匮乏。此前，Hugging Face 生物学研究团队曾发布过用于大规模基因注释的模型 Carbon-A 及相关数据库，持续探索开源模型在基因组学中的应用。

**「实际影响」** 计算生物学团队能够在受监管或敏感的本地环境中部署 DNA 序列分析流程，避免将私有基因数据上传至第三方商业模型 API。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/blog/HuggingFaceBio/carbon-annotator-genbank-genome-annotation">A Blog post by Hugging Face Biology Research on Hugging Face</a></li>

</ul>
</details>

**标签**: `#machine learning`, `#computational biology`, `#foundation models`, `#open source`

---

<a id="item-tech-news-12"></a>
### [澳洲法院裁定苹果须向第三方应用商店和侧载开放 iPhone](https://9to5mac.com/2026/10/21/apple-must-open-iphone-to-alternative-app-stores-in-australia-after-epic-games-ruling/) ⭐️ 7.0/10

澳大利亚联邦法院在 Epic Games 反垄断诉讼中作出裁决，要求苹果公司自 2027 年 3 月 1 日起，允许澳大利亚 iPhone 用户通过第三方应用商店以及网站下载安装应用，并全面开放第三方支付渠道与外部付款链接。法官认定苹果在 iOS 应用分发及支付市场具有实质性市场支配力，其限制竞争的做法违反了澳大利亚竞争法，同时裁定《堡垒之夜》（Fortnite）即日起可重返澳大利亚 App Store。苹果公司对此表示将提起上诉，并向法院申请暂缓执行该命令。

telegram · zaihuapd · 10月22日 06:54

**「背景」** Epic Games 多年来在多国针对苹果公司发起反垄断诉讼，指控其强制要求使用 App Store 渠道及应用内购买系统构成反竞争行为。澳大利亚联邦法院此前审理了 Epic 对苹果和谷歌的指控并认定其违反竞争法，本次下达的开放要求即为该起长期反垄断案件的补救裁决。

**「影响」** 面向澳大利亚市场的开发者自 2027 年 3 月起可摆脱对苹果官方商店和应用内购抽成的强制依赖，通过第三方商店或外部网页进行分发与结算；同时 Epic Games 旗下的《堡垒之夜》获准立即重返澳区 App Store，不过具体实施进度仍取决于苹果上诉及申请暂缓执行的法律流程。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://9to5mac.com/2026/10/21/apple-must-open-iphone-to-alternative-app-stores-in-australia-after-epic-games-ruling/">An Australian federal judge rules Apple must let Australian ...</a></li>
<li><a href="https://www.australiancompetitionlaw.info/cases/database/2025-epic-apple">Epic Games, Inc v Apple Inc (FCA) - Australian Competition Law</a></li>

</ul>
</details>

**标签**: `#Apple`, `#iOS`, `#Antitrust`, `#App Store`, `#Mobile Development`

---

<a id="item-tech-news-13"></a>
### [研究发现部分智能电视关闭自动内容识别后仍明文上报观看数据](https://watchingthewatchers.github.io/watchingthewatchers/index.html) ⭐️ 7.0/10

一项涵盖 10 家厂商 12 台智能电视的受控实验研究指出，部分电视在用户关闭自动内容识别（ACR）设置后，仍会持续向外上报观看相关流量。其中，运行 VIDAA OS 的机型通过未加密的 MQTT 协议以明文形式外传不可重置的设备 ID 与音频指纹；Vizio 旗下的 WatchFree+ 平台则将节目名称直接写入未加密的 DNS 查询请求中，且未向用户提供关闭选项。

telegram · zaihuapd · 10月22日 09:50

**「技术背景」** 自动内容识别（ACR）是智能电视通过采集画面或音频指纹以实时比对播放内容的技术，设备厂商通常据此分析用户收视习惯并投放定向广告。为满足隐私合规要求，智能电视系统通常在设置中提供退出（Opt-out）选项，供用户自主停用该追踪功能。

**「影响与建议」** 使用受影响机型的用户无法单纯依赖系统设置中的隐私开关来阻止行为数据收集，局域网监听者也能直接获取其观看内容及不可重置的设备指纹，需要通过网络层 DNS 屏蔽或断网等外部手段规避泄露风险。

**标签**: `#Smart TV`, `#Privacy`, `#IoT Security`, `#Network Protocols`, `#Embedded Systems`

---

<a id="item-tech-news-14"></a>
### [米哈游联合清华大学等开源 GameScaling 游戏操作模型](https://arxiv.org/abs/2610.28698v1) ⭐️ 7.0/10

米哈游崩坏 AI 团队联合清华大学等发布 GameScaling 游戏操作模型家族，基于 Qwen3.5 视觉语言模型完成键鼠操作继续预训练，参数规模覆盖 0.8B 至 27B。该模型单次推理可输出未来 200 毫秒内的键盘与鼠标动作，论文通过 120 组训练配置评估了数据量、多样性与模型规模在同源及跨游戏场景中的表现。项目以 Apache-2.0 协议开源了 8 个检查点及配套推理客户端，但未包含训练代码。

telegram · zaihuapd · 10月22日 11:32

**「背景」** 在游戏 AI 与交互决策领域，利用多模态视觉语言模型直接根据屏幕画面生成键鼠指令，是摆脱对游戏底层私有 API 依赖并打造通用操作智能体的重要方向。该技术路线通过将连续游戏帧映射为精细的人类操作时序，用于探索模型参数规模与数据构成对实时感知与动态控制泛化能力的影响。

**「影响分析」** 研究人员与开发者可以直接使用开源检查点部署多尺寸的游戏控制 Agent，但受限于未公开的训练代码，外部团队无法直接复现预训练过程或定制端到端训练管线。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/THUSI-Lab/GameScaling">GitHub - THUSI-Lab/ GameScaling : Scaling in Games: Continued...</a></li>

</ul>
</details>

**标签**: `#game-ai`, `#vision-language-models`, `#ai-agents`, `#open-source-models`, `#reinforcement-learning`

---

<a id="item-tech-news-15"></a>
### [甲骨文修复 Java SE 与 GraalVM 高危漏洞 CVE-2026-91403](https://www.oracle.com/security-alerts/alert-cve-2026-91403.html) ⭐️ 7.0/10

甲骨文发布安全警报并推出了针对高危漏洞 CVE-2026-91403 的修复补丁，该漏洞的 CVSS 评分达 9.1。该缺陷位于 JSSE（Java 安全套接字扩展）组件，未经身份验证的远程攻击者可通过网络直接利用，严重危害系统数据的机密性与完整性。漏洞影响 Java SE 8u511、11.0.33、17.0.21、21.0.13、25.0.5、27.0.1 以及多个 GraalVM 版本，官方敦促受影响用户尽快完成版本升级。

telegram · zaihuapd · 10月22日 12:30

**「背景」** JSSE（Java 安全套接字扩展）是 Java 平台用于实现 SSL/TLS 加密传输与安全网络通信的基础组件。由于 Oracle Java SE 与 GraalVM 均依赖该组件处理传输加密与握手验证，其底层缺陷会直接影响依赖相关运行时构建的网络服务。

**「潜在影响」** 由于该漏洞允许未经认证的网络远程利用，依赖受影响 Java SE 或 GraalVM 运行时的生产系统面临较高安全风险，运维团队需优先安排补丁部署与运行时升级以防范潜在攻击。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.oracle.com/security-alerts/alert-cve-2026-91403.html">Oracle Security Alert Advisory - CVE - 2026 - 91403</a></li>

</ul>
</details>

**标签**: `#Java`, `#Security Advisory`, `#Vulnerability`, `#GraalVM`, `#DevOps`

---