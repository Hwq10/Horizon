---
layout: default
title: "Horizon Summary: 2026-10-22 (ZH)"
date: 2026-10-22
lang: zh
---

> 从 37 条内容中筛选出 14 条重要资讯。

---

**科技新闻**
1. [David Harvey 分析新型 o\(n log n\) 整数乘法算法](#item-tech-news-1) ⭐️ 8.0/10
2. [PHP 8.x 发布紧急安全更新修复两处高危远程代码执行漏洞](#item-tech-news-2) ⭐️ 8.0/10
3. [SemiAnalysis 深度分析华为升腾 950PR 与 DeepSeek 技术协同](#item-tech-news-3) ⭐️ 8.0/10
4. [Quad9 因域名屏蔽法律纠纷宣布退出法国](#item-tech-news-4) ⭐️ 7.0/10
5. [eMudhra 宣布退出全球 SSL/TLS 证书业务](#item-tech-news-5) ⭐️ 7.0/10
6. [多边形三角化算法 Earstrip 实测 489 毫秒处理 370 万个地图多边形](#item-tech-news-6) ⭐️ 7.0/10
7. [Railway 发布安全通告并暂停部署，平台凭据疑遭泄露](#item-tech-news-7) ⭐️ 7.0/10
8. [亚马逊称在公开披露前已捕获 PHP2Shell 在野利用](#item-tech-news-8) ⭐️ 7.0/10
9. [开源 14.8B 模型 Carbon-X 支持 DNA 与文本联合分析](#item-tech-news-9) ⭐️ 7.0/10
10. [Anthropic 发布 Claude API 2026-10-21 版本并移除采样参数](#item-tech-news-10) ⭐️ 7.0/10
11. [澳洲法院裁定苹果须开放第三方应用商店与替代支付](#item-tech-news-11) ⭐️ 7.0/10
12. [研究称多款智能电视关闭内容识别后仍持续回传观看数据](#item-tech-news-12) ⭐️ 7.0/10
13. [米哈游与清华大学开源 GameScaling 游戏操作模型](#item-tech-news-13) ⭐️ 7.0/10
14. [甲骨文发布 Java SE 高危漏洞 CVE-2026-91403 安全补丁](#item-tech-news-14) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [David Harvey 分析新型 o\(n log n\) 整数乘法算法](https://web.maths.unsw.edu.au/~davidharvey/research/subnlogn.pdf) ⭐️ 8.0/10

数学家 David Harvey 发布论文分析了近期提出的一种时间复杂度为 o\(n log n\) 的新型整数乘法算法。该研究针对计算复杂度理论中大整数乘法的渐近下界提出了全新探讨，突破了此前公认的 O\(n log n\) 理论界限。这一理论成果随后迅速引发了形式化验证领域的跟进，相关数学推导正在被迁移至定理证明系统中进行精确检验。

hackernews · craigcitro · 10月22日 02:30 · [社区讨论](https://news.ycombinator.com/item?id=50190455)

**「背景」** 2019 年，数学家 David Harvey 与 Joris van der Hoeven 提出了时间复杂度为 $O\(n \\log n\)$ 的快速整数乘法算法，实现了该领域长久以来的渐近复杂度目标。由于该结果曾被广泛推测为整数乘法的计算极限，因此任何严格低于该界限的 $o\(n \\log n\)$ 算法都将对理论计算机科学带来颠覆性影响。

**「社区讨论」** 社区研究者 jdb1729 表示已与合作者在 Lean 定理证明器（基于 Mathlib 的 TM2 机模型）中完成了该结果的形式化证明，并正在持续优化相关指数界限。此外，多位研究者提到该系列论文的数学论证极其晦涩难读，并就使用前沿大语言模型辅助解析高难度数学论文的现象与可靠性展开了讨论。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://fr.wikipedia.org/wiki/Algorithme_de_multiplication_d&#x27;entiers">Algorithme de multiplication d&#x27;entiers — Wikipédia</a></li>
<li><a href="https://salivity.github.io/binary/article/harvey-and-hoeven-o-n-log-n-integer-multiplication">Harvey and Hoeven O (n log n) Integer Multiplication - binary</a></li>

</ul>
</details>

**标签**: `#theoretical computer science`, `#algorithms`, `#computational complexity`, `#formal verification`

---

<a id="item-tech-news-2"></a>
### [PHP 8.x 发布紧急安全更新修复两处高危远程代码执行漏洞](https://simonwillison.net/2026/Oct/21/php-security-release/) ⭐️ 8.0/10

PHP 官方针对整个 PHP 8.x 分支发布了紧急安全更新，以修复两处 CVSS 评分为 9.2 的远程代码执行（RCE）漏洞。该漏洞由 Wiz Research 发现并确认可在 Drupal 和 WordPress 上实现未经身份验证的远程代码执行。因协同披露流程出现泄密且相关机构误发概念验证（PoC）视频，导致外部 PoC 加速扩散，PHP 团队随后将原定补丁发布时间提前至 10 月 21 日 14:00 UTC。

rss · Simon Willison · 10月21日 18:41

**「背景」** 安全研究机构 Wiz Research 于 2026 年 8 月发现该系列漏洞（被称为 PHP2Shell），并在 Drupal 和 WordPress 上成功验证了未经身份验证的远程代码执行能力后向官方报告。双方原定于 10 月 22 日进行协调披露，但由于 CVE 编号及第三方概念验证视频在公开前夕相继泄露，迫使 PHP 团队紧急将补丁发布提前。

**「影响范围与应对措施」** 所有运行 PHP 8.x 的运维人员与开发者需立即将环境升级至最新的安全修复版本，以防范已在公开网络中流传的利用代码对 Drupal、WordPress 等关键系统发起未授权攻击。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/PHP2Shell">PHP 2Shell - Wikipedia</a></li>

</ul>
</details>

**标签**: `#php`, `#security`, `#vulnerability`, `#remote code execution`, `#open source`

---

<a id="item-tech-news-3"></a>
### [SemiAnalysis 深度分析华为升腾 950PR 与 DeepSeek 技术协同](https://newsletter.semianalysis.com/p/huawei-deepseek) ⭐️ 8.0/10

SemiAnalysis 发布了探讨华为与 DeepSeek 技术协同的深度分析报告。报告涵盖了对华为升腾 Ascend 950PR 芯片的微基准测试评估，并梳理了 DeepSeek 对升腾硬件生态的适配支持情况。此外，该分析还进一步剖析了 DeepSeek 的 DSv4.1 Flash 架构设计。

rss · Semianalysis · 10月21日 17:34

**「背景」** 华为升腾系列芯片依托自研的 CANN 软件栈构建独立生态，其计算性能的发挥高度依赖底层算子的适配与软硬件协同设计。此前 DeepSeek 曾针对升腾 950PR 重写了 200 多个核心 CUDA 算子以验证模型推理，推动了 DeepSeek 算法与升腾硬件架构之间的深度绑定与协同优化。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://dev.to/lanternproton/deepseek-v4-on-huaweis-ascend-950-a-real-stress-test-for-chinas-ai-chip-ecosystem-ook">DeepSeek V4 on Huawei&#x27;s Ascend 950: A Real Stress Test for ...</a></li>

</ul>
</details>

**标签**: `#AI Hardware`, `#DeepSeek`, `#Huawei Ascend`, `#Machine Learning Systems`, `#Semiconductors`

---

<a id="item-tech-news-4"></a>
### [Quad9 因域名屏蔽法律纠纷宣布退出法国](https://quad9.net/news/blog/au-revoir-france/) ⭐️ 7.0/10

注重隐私的公共 DNS 解析服务商 Quad9 宣布将退出法国，以应对当地法院下达的域名拦截法令及持续的法律纠纷。此前欧洲版权所有者多次通过诉讼要求公共解析服务商在网络层实施侵权内容屏蔽，使坚持不记录用户隐私且提供无过滤解析的 Quad9 面临严峻的合规与法律处罚风险。

hackernews · farrokhi · 10月22日 14:32 · [社区讨论](https://news.ycombinator.com/item?id=50195959)

**「背景」** 法国法院此前应 beIN Sports 等体育赛事转播商的维权申请，要求 Google、Quad9 等公共 DNS 解析服务商按指令屏蔽侵权转播网站，Quad9 若不执行还将面临每日最高达 58 万欧元的罚款诉求。在公共 DNS 屡遭版权禁令施压的背景下，此前思科旗下的 OpenDNS 也曾因拒绝执行法国法院的强制屏蔽裁决而选择停止在当地提供服务。

**「使用影响」** 在法国境内将 Quad9 设置为默认 DNS 的个人与机构需要重新配置终端设备或网关的解析地址，切换至其他 DNS 提供商以维持域名解析功能；这也直接减少了当地用户在不执行法庭封禁规则下的公共隐私解析选项。

**「社区讨论」** 社区讨论提到，思科此前在面对法国转播权相关的体育盗版屏蔽禁令时也曾选择退出市场，反映出 DNS 解析机构在当地正面临日趋严格的连带责任。部分评论者指出，原告通过 VPN 绕过地理位置拦截后再指控服务商违规并寻求法庭罚款，这种监管和诉讼模式对基础网络基础设施服务商极不合理。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://frenchbreaches.com/blog/jusqua-580-000-par-jour-pourquoi-le-service-dns-quad9-menace-de-quitter-la-france">Jusqu’à 580 000 € par jour : pourquoi le service DNS Quad9 ...</a></li>
<li><a href="https://www.justgeek.fr/quad9-blocages-anti-piratage-france-159240/">Après OpenDNS, Quad9 menace à son tour de quitter la France</a></li>
<li><a href="https://www.aubedigitale.com/quad9-envisage-de-quitter-la-france-en-raison-dune-decision-de-blocage-de-son-site-web/">Quad9 envisage de quitter la France en raison d&#x27;une décision ...</a></li>

</ul>
</details>

**标签**: `#dns`, `#networking`, `#internet-governance`, `#legal`, `#infrastructure`

---

<a id="item-tech-news-5"></a>
### [eMudhra 宣布退出全球 SSL/TLS 证书业务](https://emudhra.com/en/press-release/emudhra-to-exit-global-ssl-tls-certificate-business) ⭐️ 7.0/10

凭证颁发机构（CA）eMudhra 宣布退出全球 SSL/TLS 证书业务。此前，主要浏览器的根证书计划针对该机构的密码学实现与运营安全规范展开了严密审查与连番质询。eMudhra 表示其全球 SSL/TLS 业务基础设施独立于其他业务运行，并称外部舆论对其该项业务的关注已超出实际业务占比。

hackernews · bo0tzz · 10月22日 13:33 · [社区讨论](https://news.ycombinator.com/item?id=50195110)

**「背景」** 在此次宣布退出前，Mozilla 与 Google Chrome 根证书计划确认 eMudhra 旗下的 8 个中级证书颁发机构（CA）私钥存在严重弱私钥缺陷与安全隐患。随后，Google、Apple、Mozilla 和微软等主要平台紧急封锁了这些缺陷证书，以防止攻击者利用其伪造合法网站。

**「潜在影响」** 依赖 eMudhra 签发的公开受信任 SSL/TLS 证书的组织和站长需要尽快规划并迁移至其他受信凭证机构，以防主流浏览器根存储撤销信任导致网站访问受阻。

**「社区讨论」** 技术社区普遍指出 Chrome 团队等在 Bugzilla 上的公开质询暴露了 eMudhra 严重的流程与密钥管理缺陷；评论批评官方将监管压力归咎于“社交媒体过度放大”而非正面说明安全事故原因，同时提及事件已直接导致其股价大幅下跌。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.moneycontrol.com/technology/emudhra-to-exit-global-website-security-certificate-business-after-key-generation-flaw-article-14057821.html">eMudhra to exit global website security certificate business after...</a></li>
<li><a href="https://cointelegraph.com/news/tech-giants-rush-to-block-flawed-emudhra-certs-that-could-enable-fake-sites">Tech Giants Rush to Block Flawed eMudhra Certificates</a></li>
<li><a href="https://thehackernews.com/2026/10/eight-emudhra-ca-keys-compromised.html">Eight eMudhra CA Keys Compromised, Triggering Emergency Fixes...</a></li>

</ul>
</details>

**标签**: `#web-pki`, `#ssl-tls`, `#cybersecurity`, `#certificate-authorities`, `#infrastructure`

---

<a id="item-tech-news-6"></a>
### [多边形三角化算法 Earstrip 实测 489 毫秒处理 370 万个地图多边形](https://globus.software/blog/2026/10/16/cutting-map-polygons/) ⭐️ 7.0/10

技术博客 Globus.software 展示了一项针对地图多边形三角剖分的性能优化成果，其算法实现 Earstrip 在基准测试中仅用 489 毫秒便完成了 370 万个地图多边形的三角化，速度显著优于主流的 Earcut 算法。该测试针对大规模地理信息数据场景展开，并公开发布了相关数据集供其他算法对比。

hackernews · molind · 10月22日 09:31 · [社区讨论](https://news.ycombinator.com/item?id=50193170)

**「背景」** 在 Web 地图渲染与计算几何领域，Mapbox 开源的 Earcut 是广泛采用的多边形三角剖分算法库，其设计优先保障浏览器端的实时计算速度与实现轻量化，而非追求高质量网格划分。Globus Software 则将其自身地图引擎中优化后的多边形剖分算法抽取为独立开源库 earstrip，旨在进一步大幅提升大规模地图多边形的处理性能。

**「社区讨论」** Earcut 原作者 mourner 回应称，Earcut 是为了保持极小代码体积（约 4.1 KB）才主动放弃部分激进优化，其性能已能满足多数前端地图渲染需求，并关切新方案编译为 WASM 后的体积开销；其他开发者则指出该算法输出的部分过于细长的三角形可能会对 GPU 光栅化性能造成额外负担。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://globus.software/blog/2026/10/16/cutting-map-polygons/">Faster than earcut : triangulating 3 . 7 M map polygons in 489 ms</a></li>
<li><a href="https://github.com/mapbox/earcut">GitHub - mapbox/ earcut : The fastest and smallest JavaScript polygon ...</a></li>

</ul>
</details>

**标签**: `#computational-geometry`, `#algorithms`, `#gis`, `#performance-optimization`, `#graphics-programming`

---

<a id="item-tech-news-7"></a>
### [Railway 发布安全通告并暂停部署，平台凭据疑遭泄露](https://blog.railway.com/p/security-disclosure-wednesday-october-21st) ⭐️ 7.0/10

云托管平台 Railway 针对一起安全事件发布披露公告，暂停了平台的构建与部署管道，并建议受影响用户轮换相关凭据。由于部署服务在事件排查期间处于暂停状态，用户即使更新了密钥也暂时无法通过重新部署让新配置生效。

hackernews · passenger · 10月21日 21:58 · [社区讨论](https://news.ycombinator.com/item?id=50188228)

**「事件背景」** Railway 作为应用部署与云托管平台，允许开发者在系统中配置环境变量以注入 API 密钥、数据库凭据等关键敏感信息。官方安全披露显示，平台在检测到存储环境变量的系统出现异常活动后展开调查，确认未授权第三方可能已访问相关加密环境变量，并获取了部分变量解密后的明文内容。

**「影响」** 受影响的开发者需紧急轮换在 Railway 环境变量中配置的 API 密钥、数据库凭据与镜像仓库访问令牌；同时由于平台在处置期间暂停了构建与部署服务，立即失效旧密钥可能导致依赖这些凭据的服务在构建恢复前无法重新部署上线。

**「社区讨论」** 社区开发者反映其存储在 Railway 的环境变量机密疑遭第三方未授权读取与使用；亦有用户抱怨称，在部署被锁定的情况下盲目轮换密钥反而直接导致线上生产服务瘫痪，处置沟通缺乏缓冲。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://blog.railway.com/p/security-disclosure-wednesday-october-21st">Security Disclosure: Wednesday October 21st | Railway Blog</a></li>
<li><a href="https://blog.railway.com/p/security-disclosure-wednesday-october-21st">Security Disclosure : Wednesday October 21st | Railway Blog</a></li>

</ul>
</details>

**标签**: `#security`, `#cloud infrastructure`, `#railway`, `#devops`

---

<a id="item-tech-news-8"></a>
### [亚马逊称在公开披露前已捕获 PHP2Shell 在野利用](https://aws.amazon.com/blogs/security/amazon-threat-intelligence-identifies-php2shell-exploitation-prior-to-public-disclosure-in-madpot/) ⭐️ 7.0/10

Amazon Threat Intelligence 报告称，其 MadPot 蜜罐系统在 10 月 17 日便捕获到了针对 PHP2Shell 漏洞的在野利用尝试，早于该漏洞的正式公开披露时间。这表明攻击者在协调披露流程完成前就已开始针对该漏洞展开探测或利用。目前公开信息主要集中于监测到的攻击尝试，尚未证实是否存在广泛的实际成功入侵案例。

hackernews · cubefox · 10月22日 11:50 · [社区讨论](https://news.ycombinator.com/item?id=50194070)

**「背景」** PHP2Shell 是一组影响 PHP 5.4 至 8.5 版本、可导致远程代码执行的高危漏洞（涵盖 CVE-2026-109618 与 CVE-2026-109619），于 2026 年 10 月 20 日被公开披露。

**「排查与处置影响」** 由于针对 PHP2Shell（CVE-2026-109618 与 CVE-2026-109619）的在野利用尝试早于 10 月 20 日的公开披露，安全与运维团队在排查未授权远程代码执行痕迹时，需将 HTTP 请求与访问日志审计至少前溯至 10 月 17 日，并及时升级覆盖 PHP 5.4 至 8.5 的受影响实例。

**「社区讨论」** 讨论焦点主要在于探测流量的实际威胁程度与漏洞披露的协调问题，多位开发者指出服务器日志中观察到的多为僵尸网络的自动化扫描探测，尚缺乏公开发布且切实有效的完整利用载荷。此外，围绕披露保密期（embargo）、Chainguard 提前发布修补镜像以及各大厂商补丁跟进进度的责任归属也引发了激烈争论。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/PHP2Shell">PHP 2 Shell - Wikipedia</a></li>
<li><a href="https://aws.amazon.com/blogs/security/amazon-threat-intelligence-identifies-php2shell-exploitation-prior-to-public-disclosure-in-madpot/">Amazon Threat Intelligence identifies PHP 2 Shell exploitation prior to...</a></li>
<li><a href="https://en.wikipedia.org/wiki/PHP2Shell">PHP 2 Shell - Wikipedia</a></li>
<li><a href="https://almalinux.org/blog/2026-10-21-php2shell-cve-2026-109618-cve-2026-109619/">php 2 shell ( CVE -2026-109618, CVE -2026-109619)... | AlmaLinux OS</a></li>

</ul>
</details>

**标签**: `#security`, `#php`, `#vulnerability`, `#threat-intelligence`

---

<a id="item-tech-news-9"></a>
### [开源 14.8B 模型 Carbon-X 支持 DNA 与文本联合分析](https://www.reddit.com/r/MachineLearning/comments/1xchayq/carbonx_is_an_open_148b_model_trained_jointly_on/) ⭐️ 7.0/10

开源模型 Carbon-X 基于 Apache 2.0 许可证发布，该模型拥有 14.8B 参数，支持在交互对话中直接接收原始 DNA 序列并使用英文回答。模型在包含文本与 DNA 6-mer 的单一词元流中进行了 3020 亿词元的中程预训练，其 bfloat16 权重可部署在单张 80 GB GPU 上。在关闭思考模式下，Carbon-X 在 5 项 DNA 基准测试上的平均得分为 66.7%（对比 GPT-6.1 Sol 的 67.5%），但目前尚未经过临床验证，模型卡亦注明精确的序列操作仍应由专用代码处理。

reddit · r/MachineLearning · /u/jatingargiitk · 10月22日 12:32

**「背景」** Hugging Face 此前曾推出 Carbon 系列开源 DNA 基础模型（涵盖 5 亿至 80 亿参数），主要聚焦于基因组序列本身的建模与表征 \[tool-1-2\]。传统基因分析工具与通用大语言模型通常彼此分离，而将 DNA 的 6-mer 切片与自然语言整合进统一的 Token 流，旨在让研究人员能够直接使用日常语言查询并分析生物序列 \[tool-1-2, tool-1-3\]。

**「实际影响」** 该模型允许研究团队在单卡硬件上本地运行基因组序列分析，为处理敏感生物数据集提供了无需依赖闭源商业云 API 的本地部署方案。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/spaces/HuggingFaceBio/carbon-demo">Carbon - a Hugging Face Space by HuggingFaceBio</a></li>
<li><a href="https://thenextweb.com/news/hugging-face-carbon-x-dna-ai-model">Hugging Face releases Carbon-X, an AI model for questions ...</a></li>

</ul>
</details>

**标签**: `#computational biology`, `#genomics`, `#large language models`, `#open source ai`

---

<a id="item-tech-news-10"></a>
### [Anthropic 发布 Claude API 2026-10-21 版本并移除采样参数](https://x.com/ClaudeDevs/status/2113013247209021918) ⭐️ 7.0/10

Anthropic 正式发布 Claude API 版本 2026-10-21，这是其自 2023 年以来的首次正式版本更新。新版完全移除了 temperature、top\_p 和 top\_k 等采样参数，若继续传入该类参数将直接返回 400 错误。官方 SDK 与 ant CLI 已默认切换至新版本，认证请求头统一更新为 Authorization: Bearer，旧版 API 2023-06-01 目前未被弃用。

telegram · zaihuapd · 10月22日 03:54

**「背景」** Claude API 自 2023 年 6 月起长期以 2023-06-01 作为基准版本，开发者通过 anthropic-version 请求头固定接口行为，并普遍依赖 temperature、top\_p 与 top\_k 等采样参数控制模型的输出随机性与多样性。

**「影响与适配」** 使用最新官方 SDK 或 CLI 的开发者需移除请求中的采样参数并适配新的认证格式以避免请求失败，若仍需使用这些参数则必须显式锁定旧版 2023-06-01。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://platform.claude.com/docs/en/api/migration-2026-10-21">Migrating to API version 2026-10-21 - Claude Platform Docs</a></li>
<li><a href="https://platform.claude.com/docs/en/api/versioning">Versions - Claude Platform Docs - Anthropic</a></li>

</ul>
</details>

**标签**: `#Anthropic`, `#Claude API`, `#LLM`, `#API Design`, `#Software Engineering`

---

<a id="item-tech-news-11"></a>
### [澳洲法院裁定苹果须开放第三方应用商店与替代支付](https://9to5mac.com/2026/10/21/apple-must-open-iphone-to-alternative-app-stores-in-australia-after-epic-games-ruling/) ⭐️ 7.0/10

澳大利亚联邦法院在 Epic Games 提起的反垄断诉讼中裁定，苹果必须自 2027 年 3 月 1 日起允许澳区 iPhone 用户通过第三方应用商店与网站下载安装应用，并全面开放替代支付方式与外部支付链接，《堡垒之夜》（Fortnite）亦将立即重返当地 App Store。法官认定苹果在 iOS 应用分发及应用内支付市场拥有实质性市场力量，其排他性限制违反了澳大利亚竞争法。苹果随后表示将对该裁决提出上诉，并申请暂缓执行相关命令。

telegram · zaihuapd · 10月22日 06:54

**「背景」** Epic Games 与苹果围绕应用分发限制和应用内支付抽成展开了长达数年的反垄断诉讼。澳大利亚联邦法院曾于 2025 年 8 月裁定苹果存在反竞争行为，本次要求其开放第三方应用商店与外部支付正是该案的后续执行裁决。

**「影响」** 若苹果的上诉与暂缓执行申请未能改变判决，面向澳大利亚市场的开发者自 2027 年 3 月起将可采用第三方商店、网页分发及外部支付渠道绕过官方内购限制；而 Epic Games 旗下的《堡垒之夜》（Fortnite）则获准依判决立即重返澳大利亚 App Store。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://au.news.yahoo.com/aust-court-orders-fortnite-back-083941972.html">Aust court orders Fortnite back into app store - Yahoo News</a></li>
<li><a href="https://9to5mac.com/2026/10/21/apple-must-open-iphone-to-alternative-app-stores-in-australia-after-epic-games-ruling/">An Australian federal judge rules Apple must let Australian ...</a></li>
<li><a href="https://www.macrumors.com/2026/10/22/rival-app-stores-in-australia-ordered/">Apple Ordered to Open iPhone to Rival App Stores in Australia</a></li>

</ul>
</details>

**标签**: `#apple`, `#app-store`, `#epic-games`, `#antitrust`, `#mobile-development`

---

<a id="item-tech-news-12"></a>
### [研究称多款智能电视关闭内容识别后仍持续回传观看数据](https://watchingthewatchers.github.io/watchingthewatchers/index.html) ⭐️ 7.0/10

一项针对智能电视自动内容识别（ACR）的实测研究在测试 10 家厂商的 12 台电视、完成 5943 次受控实验后发现，部分机型在用户于系统设置中关闭 ACR 后仍会持续上报内容关联流量。测试显示，VIDAA OS 通过未加密的 MQTT 协议以明文传输不可重置的设备 ID 及音频指纹；Vizio 平台的 WatchFree+ 更是将正在播放的节目名称直接写入未加密的域名查询中，且该行为未向用户提供关闭选项。

telegram · zaihuapd · 10月22日 09:50

**「背景」** 自动内容识别（ACR）是现代智能电视普遍内置的技术，通过提取并比对音视频信号中的数字指纹来识别用户正在播放的内容，主要用于收视行为分析与定向广告投放。各厂商通常在系统设置中提供关闭 ACR 的隐私选项，允许用户选择退出针对屏幕内容的遥测与数据采集。

**「安全与隐私影响」** 由于系统级隐私开关未能完全阻断数据采集且部分流量缺乏传输加密，受影响设备的用户在观看内容时面临本地网络窃听与不可逆设备画像追踪的风险，仅依靠电视内置设置已无法有效规避遥测。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.ucdavis.edu/news/your-smart-tv-watching-what-you-watch">Your Smart TV is Watching What You Watch - UC Davis</a></li>
<li><a href="https://www.pcmag.com/explainers/is-your-tv-spying-on-you-hidden-setting-watching-everything-how-to-stop">Is Your TV Spying on You? The Hidden Setting Watching ... - PCMag</a></li>

</ul>
</details>

**标签**: `#privacy`, `#iot security`, `#smart tvs`, `#network security`

---

<a id="item-tech-news-13"></a>
### [米哈游与清华大学开源 GameScaling 游戏操作模型](https://arxiv.org/abs/2610.28698v1) ⭐️ 7.0/10

米哈游崩坏 AI 团队联合清华大学等发布并开源了面向实时游戏控制的 GameScaling 模型族。该系列模型基于 Qwen3.5 视觉语言模型进行键鼠动作的继续预训练，参数规模覆盖 0.8B 至 27B，单次推理可输出未来 200 毫秒的键鼠操作指令。研究团队通过 120 组训练配置验证了数据量、多样性与参数规模对跨游戏迁移能力的扩展规律，目前已在 Apache-2.0 协议下开源 8 个模型检查点和推理客户端，但未公开训练代码。

telegram · zaihuapd · 10月22日 11:32

**「背景」** 利用多模态视觉语言模型直接根据游戏画面端到端预测键鼠控制指令，是构建通用游戏智能体的重要方向。为了满足实时操作需求，此类方案通常需要结合当前及历史画面与动作记录，将短时间窗口内的按键序列与鼠标轨迹切片进行高频联合预测。

**「潜在影响」** 游戏 AI 研究者和开发者可以直接使用现成检查点构建针对特定相近游戏的端到端键鼠代理，但由于训练代码未同步释出，基于私有游戏数据复现或扩展整套预训练流程仍面临限制。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/THUSI-Lab/GameScaling">GitHub - THUSI-Lab/GameScaling: Scaling in Games: Continued ...</a></li>

</ul>
</details>

**标签**: `#AI Agents`, `#Vision-Language Models`, `#Game AI`, `#Open Source AI`

---

<a id="item-tech-news-14"></a>
### [甲骨文发布 Java SE 高危漏洞 CVE-2026-91403 安全补丁](https://www.oracle.com/security-alerts/alert-cve-2026-91403.html) ⭐️ 7.0/10

甲骨文发布安全警报并推出修复补丁，以修复 Java SE 中 CVSS 评分为 9.1 的严重漏洞 CVE-2026-91403。该漏洞位于 JSSE（Java 安全套接字扩展）组件中，未经身份验证的远程攻击者可通过网络对其进行利用，破坏数据的机密性与完整性。漏洞影响 Java SE 8u511、11.0.33、17.0.21、21.0.13、25.0.5、27.0.1 以及多个 GraalVM 版本。

telegram · zaihuapd · 10月22日 12:30

**「背景」** JSSE（Java 安全套接字扩展）是 Java 平台负责实现 SSL 与 TLS 协议、保障网络传输安全的核心组件。当该底层通信组件存在安全缺陷时，远程攻击者可在无需身份凭证的情况下直接通过网络实施攻击，导致系统内敏感数据被非法访问、修改或删除。

**「受影响范围与应对措施」** 运行相关 Java SE 长期支持版本（LTS）或 GraalVM 的系统管理员和开发者需尽快升级至已修复版本，以防范未经授权的网络远程攻击。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://app.opencve.io/cve/CVE-2026-91403">CVE-2026-91403 - Vulnerability Details - OpenCVE</a></li>

</ul>
</details>

**标签**: `#Java`, `#Cybersecurity`, `#Vulnerability`, `#Oracle`

---