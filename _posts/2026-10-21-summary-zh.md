---
layout: default
title: "Horizon Summary: 2026-10-21 (ZH)"
date: 2026-10-21
lang: zh
---

> 从 47 条内容中筛选出 13 条重要资讯。

---

**科技新闻**
1. [Google 开源 TorchTPU：TPU 原生 PyTorch 后端](#item-tech-news-1) ⭐️ 8.0/10
2. [eMudhra 中间 CA 私钥被指仅一字节](#item-tech-news-2) ⭐️ 8.0/10
3. [tsrs：用 Rust 移植 TypeScript 编译器](#item-tech-news-3) ⭐️ 8.0/10
4. [DeepSeek 上线 DeepInfer 推理框架仓库，细节与基准尚未披露](#item-tech-news-4) ⭐️ 7.0/10
5. [Mistral 发布 Voxtral 3 与实时语音代理 SDK](#item-tech-news-5) ⭐️ 7.0/10
6. [Google Cloud europe-west2 故障波及多家银行](#item-tech-news-6) ⭐️ 7.0/10
7. [作者称推动移除 300 多个恶意 Tor 出口节点](#item-tech-news-7) ⭐️ 7.0/10
8. [Rust 编译器 2026 年路线图：求解器、Polonius 与产物体积](#item-tech-news-8) ⭐️ 7.0/10
9. [SUSE 工程师推动系统级禁用 setuid/setgid](#item-tech-news-9) ⭐️ 7.0/10
10. [Kangrejos 2026 谨慎讨论用 Rust 重写 XArray](#item-tech-news-10) ⭐️ 7.0/10
11. [OpenBSD 8.0 发布：arm64 支持休眠，amd64 内核空间达 512GB](#item-tech-news-11) ⭐️ 7.0/10
12. [DeepSeek 据报深度参与华为未来 AI 芯片设计](#item-tech-news-12) ⭐️ 7.0/10

**科技博客**
1. [Shopify 从 React Native 转向原生开发](#item-tech-blog-1) ⭐️ 5.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Google 开源 TorchTPU：TPU 原生 PyTorch 后端](https://github.com/google-pytorch/torch_tpu) ⭐️ 8.0/10

Google 已开源 TorchTPU，这是一个面向 TPU 的原生 PyTorch 后端，旨在简化开发者在 TPU 硬件上使用 PyTorch 的流程。项目托管在 google-pytorch 的 GitHub 组织下。公开信息目前没有说明它支持哪些 PyTorch 版本、性能表现如何，以及是否达到生产可用，因此尚无法判断它相对现有 XLA 路径的成熟度。

hackernews · ilreb · 10月20日 16:40 · [社区讨论](https://news.ycombinator.com/item?id=50169053)

**「背景」** 在 TorchTPU 之前，PyTorch 在 TPU 上运行主要依赖 PyTorch/XLA 这一桥接层，把 PyTorch 计算图交给 XLA 编译，而不是作为 PyTorch 原生后端直接接入。评论者 ismailmaj 也回忆说，过去要让 PyTorch 跑在 TPU 上「得和 XLA 较劲」，这与本次以原生后端形式接入的定位形成对照。

**「对开发者的直接影响」** 现有 PyTorch 用户可以将训练与推理流程直接迁移到 TPU 上，无需改用 JAX 或自行对抗 XLA：官方说明可与 vLLM、SGLang、llm-d、TorchTitan、Ray、TorchRec、Hugging Face、LiteRT 等既有工具链配合完成训练、服务和部署。该后端由 Google 与 Meta 合作开发，通过即时执行（eager execution）优化与 torch.compile 集成来提供原生硬件支持，因此迁移仍以接入这一新后端及其编译路径为前提，而非零改动切换。

**「社区讨论」** 有评论者称，自己正基于 Tenstorrent 软件栈开发开源的 libtpu 实现，目前已能运行 TorchTPU 的大部分功能；还有人指出，AWS 为 Trainium 提供了类似的 torch-neuronx 后端。另有评论认为，XLA 可能成为比 inductor 更强的编译器基础设施，从而改善多种硬件上的性能，并称这对 TensorFlow 不利；也有人表示，在获得第一方支持后，JAX 与 PyTorch 之间的选择可能更多取决于使用风格。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://cloud.google.com/blog/topics/ai-infrastructure/torchtpu-is-now-open-source-run-native-pytorch-on-tpus">TorchTPU is now open source: Run native PyTorch on TPUs</a></li>
<li><a href="https://pytorch.org/blog/introducing-torchtpu/">Introducing TorchTPU - PyTorch</a></li>

</ul>
</details>

**标签**: `#PyTorch`, `#TPU`, `#ML systems`, `#open source`, `#hardware acceleration`

---

<a id="item-tech-news-2"></a>
### [eMudhra 中间 CA 私钥被指仅一字节](https://emudhra.we-have-a-problem.com/) ⭐️ 8.0/10

eMudhra 的中间 CA 事件出现关键细节：社区讨论称，8 个被列为遭攻破的 CA 私钥都只有一个字节，其中一个私钥就是“4”，但这一说法目前仍是社区指认，尚未经过独立验证。引用 Mozilla Bugzilla 的讨论称，eMudhra 初步归因于当天生成这些 ECC 签发者时使用的 KGC 脚本存在缺陷，并提到一项经批准的对常规 KGC 的偏离。评论者 galadran 表示，Firefox 已通过 OneCRL 在数小时内自动吊销相关证书，用户无需更新；Chrome、Apple 和 Microsoft 也有类似工具，但生态中其他依赖方对吊销的投入仍然不足。

hackernews · galadran · 10月20日 13:58 · [社区讨论](https://news.ycombinator.com/item?id=50166579)

**「背景」** 浏览器和操作系统并不逐一信任所有站点证书，而是信任一组根证书；根证书签发中间 CA，中间 CA 再签发站点的叶证书，因此中间 CA 的私钥一旦泄露，攻击者无需触碰根证书就能签发被信任的伪造证书。据 Mozilla 说明，其于 10 月 17 日 20:06 UTC 收到报告，涉及 8 张 eMudhra 中间证书的私钥泄露，而这些中间证书链到 Mozilla、Microsoft、Apple 和 Chrome 根计划以及众多下游信任库所信任的根。eMudhra 在 Mozilla 的 bug 报告中初步表示，问题源于当天用于生成这批 ECC 签发者的密钥生成（KGC）脚本存在缺陷，并提及这是对其常规流程的一次经批准的偏离。

**「实际影响」** 对不依赖浏览器内置撤销列表的系统，尤其是嵌入式/IoT 设备和自建 TLS 客户端，不能假定相关中间 CA 会被自动剔除；运维方需要检查信任库、确认证书链是否受影响，并重新签发证书或手动移除不再可信的中间 CA。

**「社区讨论」** eqvinox 用“一个字节、其中一个就是 4”强调这些私钥的弱度，并称很难把这种情况称为真正意义上的“攻破”；hypfer 则称相关密钥疑似出现在 repository.emsign.com 的证书路径下，但同时承认自己可能误读，呼吁有资质的人给出可信解释。tech234a 摘录了 eMudhra 在 Mozilla Bugzilla 中的初步说明，galadran 则把讨论拉回吊销机制：浏览器端处理很快，但浏览器之外的生态响应参差。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://news.ycombinator.com/item?id=50166579">EMudhra Intermediate CA Compromise | Hacker News</a></li>
<li><a href="https://blog.mozilla.org/security/2026/10/20/protecting-firefox-users-following-the-compromise-of-emudhra-intermediate-certificates/">Protecting Firefox users following the compromise of eMudhra ...</a></li>
<li><a href="https://emudhra.we-have-a-problem.com/">eMudhra Intermediate CA Compromise</a></li>

</ul>
</details>

**标签**: `#PKI`, `#TLS certificates`, `#CA compromise`, `#browser security`, `#cryptography`

---

<a id="item-tech-news-3"></a>
### [tsrs：用 Rust 移植 TypeScript 编译器](https://blog.cloudflare.com/typescript-rust-port/) ⭐️ 8.0/10

Cloudflare 博客的一篇文章介绍了 tsrs：一个把 TypeScript 编译移植到 Rust 的项目。据评论者引用的移植文档，它用永不释放的 arena 安放长生命周期对象，以在没有 GC 的 Rust 中模拟 GC；另一名评论者称，项目动机之一是获得能在 WASM-only 沙箱中运行的编译器，避免 tsc 的 Go 版本附带完整 Go 运行时。该评论者还称 Rust 版本快于参考的 tsc/Go 实现。现有材料没有说明 tsrs 的发布状态、与 tsc 的兼容范围或可复现的基准数据，因此这些速度说法仍需核实。

hackernews · hnisjafx40 · 10月20日 13:18 · [社区讨论](https://news.ycombinator.com/item?id=50165953)

**「背景」** TypeScript 官方编译器 tsc 用 TypeScript 编写，运行时依赖 JavaScript 引擎的垃圾回收来管理 AST、符号表等长期存活的对象；若要在 Rust 中重写，就必须重新安排这些数据的生命周期，这也是长期阻碍用 Rust 重写 tsc 的原因之一。Cloudflare 参与合作的 tsrs 还服务于另一个具体约束：让编译器能够在只有 WebAssembly 的沙箱中运行。Cloudflare 博客称，该 Rust 版本的编译速度最高提升 8 倍，内存占用减少约 70%。

**「影响」** 对需要在 WASM 沙箱中运行 TypeScript 编译的团队，这条路径的直接影响是可能不必随编译器打包完整 Go 运行时；但 tsrs 是否已发布、覆盖哪些 TypeScript 版本和编译选项尚不清楚，采用前需要先确认兼容性和性能数据。

**「社区讨论」** TypeScript 团队成员 DanRosenwasser 表示，tsrs 的速度不只取决于语言选择，其中一些优化也会让 TS 7.1 更快、更精简；评论者 afdbcreid 则强调其 arena 内存模型是绕开 Rust 无 GC 的关键。egonschiele 对速度提升表示期待，但对博客所述完全由 AI 生成移植的方式持保留态度，并提到博客作者称自己未写代码。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://blog.cloudflare.com/typescript-rust-port/">Introducing tsrs : a Port of TypeScript to Rust | Cloudflare Blog</a></li>

</ul>
</details>

**标签**: `#TypeScript`, `#Rust`, `#compilers`, `#WebAssembly`, `#memory management`

---

<a id="item-tech-news-4"></a>
### [DeepSeek 上线 DeepInfer 推理框架仓库，细节与基准尚未披露](https://github.com/deepseek-ai/DeepInfer) ⭐️ 7.0/10

DeepSeek 在 GitHub 上发布了名为 DeepInfer 的仓库，并将其定位为面向 DeepSeek 模型的高性能推理框架，该仓库在 Hacker News 上引发了大量讨论。但本次条目未附带任何仓库内容，既没有文档，也没有版本号、基准数据或硬件兼容清单，因此其吞吐、延迟与部署成本目前无法核实。讨论中的具体性能数字均来自评论者转述的第三方文章，而非官方材料。

hackernews · ggcr · 10月20日 09:08 · [社区讨论](https://news.ycombinator.com/item?id=50163277)

**「背景」** 此前，DeepSeek 的 V4 系列模型主要依靠第三方推理框架部署：Horizon 4 月 28 日的日报显示，vLLM v0.20.0 首次加入对 DeepSeek V4 的支持；5 月 17 日的日报又记录 SGLang v0.5.12 提供完整的 DeepSeek V4 推理支持，涵盖张量并行与专家并行、DeepGemm 内核以及预填充与解码分离。据 MarkTechPost 报道，此次开源的 DeepInfer 最初主要基于 vLLM 构建，并以 Apache 2.0 许可发布；当前版本只覆盖离线推理，包含大规模服务所需的核心功能。

**「实际影响」** 对打算选用推理栈的团队来说，在官方基准、许可证条款和硬件兼容列表公布之前，这个仓库还不足以支撑选型或迁移决策；评论者 yaoke259 特别把“开源推理代码支持华为升腾 950 NPU”视为最值得关注的潜在变量，但这一支持范围目前只见于评论，未获官方材料确认。

**「社区讨论」** 评论者 schneehertz 引用一篇知乎文章，称基于该框架已为“DeepSeek V4.1 Flash”提供大规模服务，单集群日吞吐达 155 万亿 token、单卡每小时收入 38 美元（非高峰定价）；这些数字未经独立核实，也只是转述。另有评论把仓库发布时间与美国 DHS 的相关命令联系起来，属于个人推测而非已证事实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/sgl-project/sglang/releases/tag/v0.5.12">2026-05-17 — sglang v0.5.12 Adds Full DeepSeek V4 Inference Support</a></li>
<li><a href="https://github.com/vllm-project/vllm/releases/tag/v0.20.0">2026-04-28 — vLLM v0.20.0 Released with DeepSeek V4 and CUDA 13.0</a></li>
<li><a href="https://www.marktechpost.com/2026/10/20/deepseek-deepinfer-open-source-inference-framework/">DeepSeek Open-Sources DeepInfer, the Inference Framework ...</a></li>
<li><a href="https://aiweekly.co/alerts/deepseek-open-sources-deepinfer-its-v41-flash-serving-stack">DeepSeek open-sources DeepInfer, its V4.1-Flash serving stack</a></li>

</ul>
</details>

**标签**: `#DeepSeek`, `#LLM inference`, `#open source`, `#model serving`, `#Hacker News`

---

<a id="item-tech-news-5"></a>
### [Mistral 发布 Voxtral 3 与实时语音代理 SDK](https://mistral.ai/news/voxtral-3/) ⭐️ 7.0/10

Mistral 宣布推出 Voxtral 3，并发布一套实时语音代理 SDK；该 SDK 将听取语音、推理、工具调用和语音回复整合到电话或网页的实时对话中。公告未披露基准测试、模型许可或架构细节，因此其语音识别质量、延迟和本地部署条件仍无法核实。

hackernews · ilreb · 10月20日 16:02 · [社区讨论](https://news.ycombinator.com/item?id=50168396)

**「从开源权重语音模型到语音智能体套件」** Horizon 3 月 27 日的日报曾报道，Mistral 发布 Voxtral TTS——一个 3B 参数的开源权重语音合成模型，支持九种语言，首段音频延迟约 90 毫秒。此次 Voxtral 3 的形态不再只是单个语音模型，而是打包的语音智能体开发套件：按 Mistral 的说法，它把语音识别、带情感适应的语音合成与工具调用结合进实时多轮对话，覆盖 50 多种语言。

**「对本地部署用户的影响」** 对需要私有化或离线部署的开发者来说，最直接的区别在于托管方式：有评论者称自己已把上一代开放权重的 Voxtral Mini 4B Realtime 做成商用 Windows 软件，仅需 4GB 显存，并在 Ryzen 5 5600U 核显笔记本上超过实时速率。另有评论者指出 Voxtral 3 属于闭源模型（源材料未给出许可证信息，应视为社区说法），若属实，想让新模型在自有硬件或内网运行的团队就无法像上一代那样自行托管，只能通过 Mistral 的语音代理 SDK 或接口调用。

**「社区讨论」** 评论者对实际效果和演示可信度提出质疑：一位开发者称已商用 Voxtral Mini 4B Realtime 的离线推理，在 4GB 显存、Ryzen 5 5600U 集显的笔记本上超过实时速度，并正在移植 Linux；另有评论称 Voxtral 3 是闭源模型，认为这不利于本地部署。还有用户抱怨 Teams 和 8x8 的现成转写质量太差，希望把音频流接入更好的模型，并有人指出演示中的法国皮肤科预约速度不现实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://mistral.ai/news/voxtral-3/">Voxtral 3: Voice Agent SDK &amp; Speech Models in 50+ Languages</a></li>
<li><a href="https://www.reddit.com/gallery/1s46ylj">2026-03-27 — Mistral AI releases Voxtral TTS, a 3B-parameter open-weights model outperforming ElevenLabs Flash v2.5</a></li>

</ul>
</details>

**标签**: `#speech-recognition`, `#voice-agents`, `#Mistral AI`, `#real-time AI`, `#speech-to-text`

---

<a id="item-tech-news-6"></a>
### [Google Cloud europe-west2 故障波及多家银行](https://www.neowin.net/news/google-cloud-outage-takes-down-hsbc-revolut-bank-of-scotland-llyods-equifax-more/) ⭐️ 7.0/10

Google Cloud 的状态页显示，europe-west2 区域自 2026-10-19 23:08 PDT 起有多项服务受影响，原因是 europe-west2-b 可用区发生供电事件；状态页称供电事件已缓解，并预计在 30 分钟内部分恢复基础设施服务。据 Neowin 汇总，汇丰、Revolut、苏格兰银行、劳埃德和 Equifax 等欧洲服务出现中断，但现有证据不足以支持标题中近乎全面停摆的说法。一名汇丰客户在评论中称其服务正常，并指出 Downdetector 主要依赖用户上报，不能作为权威宕机证据。

hackernews · paweladamczuk · 10月20日 10:26 · [社区讨论](https://news.ycombinator.com/item?id=50163961)

**「背景」** Google Cloud 按区域（region）和可用区（zone）组织基础设施，europe-west2 是区域标识，europe-west2-b 是该区域内的一个可用区。有评论引用其状态页称，europe-west2 的多项服务从 2026-10-19 23:08 PDT 起受影响，起因是 europe-west2-b 发生电力事件，这有助于理解为何同一区域的银行等服务会同时受波及。

**「影响」** 对依赖 europe-west2 的银行客户，最直接的后果是登录、取款和刷卡支付一度中断；The Register 报道称该区域多个服务出现高错误率和间歇性网络故障，且当时“暂无变通方案”，BBC 也报道 HSBC、Lloyds 和 Revolut 等服务受影响。这意味着受影响机构只能等待该区域恢复，业务连续性会受制于单一云区域，跨区域故障切换成为实际关切。

**「社区讨论」** 评论中的亲身经历并不一致：一位 Revolut 用户称当天早上起无法登录、取现或刷卡，且没有电话客服可联系；一位 HSBC 用户则说服务一切正常。后者还批评 Downdetector 主要反映用户上报而非真实宕机状态，提醒对报道中的受影响范围保持谨慎。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.theregister.com/paas-and-iaas/2026/10/20/google-clouds-london-zones-takes-a-nap-multiple-services-disrupted/5304084">Google Cloud &#x27;s London zones takes a nap, multiple services disrupted</a></li>
<li><a href="https://www.bbc.com/news/live/c58jd2kjp93xt">Google Cloud says services are recovering after outage hit banks ...</a></li>

</ul>
</details>

**标签**: `#google-cloud`, `#cloud-outage`, `#europe-west2`, `#banking`, `#cloud-reliability`

---

<a id="item-tech-news-7"></a>
### [作者称推动移除 300 多个恶意 Tor 出口节点](https://kaba.cx/posts/20261020_Tor/) ⭐️ 7.0/10

一篇帖子称，作者通过调查推动移除了 300 多个恶意 Tor 出口节点；帖子将此事与 SSH 中间人攻击的检测和处置联系起来。材料没有提供攻击时间线、涉及的具体托管商或独立验证结果，因此这仍是作者自述的调查结果。对 Tor 用户和出口节点运营者而言，帖子呈现的关键点是：恶意出口节点可参与 SSH 流量劫持，而 SSH 的主机密钥警告和密钥认证是讨论中的主要检测与防护手段。

hackernews · kabakabakaba · 10月20日 13:39 · [社区讨论](https://news.ycombinator.com/item?id=50166257)

**「背景」** Tor 出口节点是流量离开 Tor 网络、进入公开互联网的最后一跳，控制出口节点者可以观察甚至篡改未端到端加密的流量；SSH 中间人攻击则针对登录凭据和会话。此前 ESET 对 Ebury 僵尸网络的记录显示，这一 OpenSSH 后门曾感染包括 Tor 出口节点在内的大量主机，且单一托管商在 2023 年就有 7 万台服务器被感染，说明出口节点与 SSH 层入侵结合并非新问题。

**「实际影响」** 对用 SSH 管理服务器的 Tor 节点运营者来说，评论者强调密钥认证可避免密码在中间人攻击中泄露，因为私钥不会离开客户端；但攻击者仍可能观察用户输入的命令，主机密钥校验和留意 SSH 的 MITM 警告仍是必要动作。

**「社区讨论」** 评论中，exitmap 的作者表示该工具已使用十余年；多位评论者认为攻击者选择 SSH 反而失策，因为 SSH 的 MITM 警告横幅使攻击立即暴露，并让管理员更容易追踪受感染节点。也有评论者质疑 Tor 出口节点数量只有约 3000，认为这一规模过小。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.darkreading.com/threat-intelligence/400k-linux-servers-recruited-by-resurrected-ebury-botnet">400K Linux Servers Recruited by Resurrected Ebury Botnet</a></li>
<li><a href="https://www.thestack.technology/single-host-saw-70-000-servers-hit-with-ebury-backdoor/">Single host saw 70,000 servers hit with Ebury backdoor</a></li>

</ul>
</details>

**标签**: `#Tor`, `#network security`, `#SSH`, `#threat intelligence`, `#privacy`

---

<a id="item-tech-news-8"></a>
### [Rust 编译器 2026 年路线图：求解器、Polonius 与产物体积](https://yoyo-code.com/2026-is-exciting-year-for-rust-compiler-and-me/) ⭐️ 7.0/10

Rust 编译器贡献者 panstromek 撰文展望 2026 年 Rust 编译器的工作重点，帖文在 Hacker News 引发讨论。由于原文正文未随讨论一并提供，具体版本号、落地时间表与已完成状态均无法核实；从讨论内容看，涉及的核心议题是 trait 求解器（solver）、Polonius 借用检查、长期停滞的 specialization，以及 target 目录体积。评论者引用了文中一句评价，称这项工作“解决了编译器开发者多年来梦寐以求的一大块技术债”，但该引文本身没有点明具体对应哪个组件。

hackernews · panstromek · 10月20日 13:53 · [社区讨论](https://news.ycombinator.com/item?id=50166502)

**「背景」** Rust 编译器团队重写 trait solver 已持续多年：Horizon 3 月 31 日的日报曾报道，这项重写接近完成，目标是修复健全性缺陷、改善编译时间并简化 trait 系统的后续改动。与之并行的是新的借用检查器 Polonius，其项目目标先是稳定 alpha 分析，再逐步提升表达力，让更多借用模式通过编译。这篇 2026 年路线图文章所谈的，正是这些长期项目在同一时间点走向成熟。

**「影响」** 对日常使用 Rust 的开发者来说，最直接可感知的收益是 target 目录体积与编译时间——评论者对缩小 target 目录的反应最为具体；而求解器与 Polonius 能否真正解锁 specialization，仍取决于尚未公布的落地进度，依赖该 nightly 特性的库作者目前没有可据以规划的时间点。

**「社区讨论」** 一位自称多年参与编译器贡献的评论者认为 Rust 已不再是“未来”，理由是项目规模膨胀拖慢编译，他期待出现一门兼具 Go 的平实、Zig 的编译速度与 Rust 安全性的新语言。另一位评论者则表示自己等求解器已等了大约五年，希望它与 Polonius 一起让停滞多年的 specialization 解冻；作者本人另在评论中抱怨帖子标题被提交平台反复改错。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://lwn.net/Articles/1063124/">2026-03-31 — Rust&#x27;s next-generation trait solver nears completion to fix soundness bugs and improve compile times.</a></li>
<li><a href="https://goals.rust-lang.org/2026/polonius.html">Stabilize and model Polonius Alpha - Rust Project Goals</a></li>

</ul>
</details>

**标签**: `#Rust`, `#compilers`, `#programming languages`, `#compile times`, `#open source`

---

<a id="item-tech-news-9"></a>
### [SUSE 工程师推动系统级禁用 setuid/setgid](https://lwn.net/Articles/1100257/) ⭐️ 7.0/10

SUSE 杰出工程师 Thorsten Kukuk 在 2026 年 All Systems Go\! 会议上介绍了一项仍在推进的工作：通过让 systemd 的 PID 1 设置 NoNewPrivileges=yes，在内核层为所有进程启用 no\_new\_privs，从而阻止 execve\(\) 赋予 setuid、setgid 或文件能力，目标是系统级禁用这类二进制。该标志会跨 fork\(\)、clone\(\) 和 execve\(\) 保持，但不会阻止已有特权的任务直接调用 setuid\(\) 或 setresuid\(\)。为处理账户管理，他开发了 scan-caps 和 account-utils，并以经 varlink 通信、仅能访问 /etc/passwd 与 /etc/shadow 的 pwaccessd/pwupdd 服务替代 shadow-utils、PAM 等需要特权的客户端。报道没有说明该方案已在 SUSE 产品中默认启用；sudo 改用 run0 等“侵入性包”会把 sudoers 配置变为 polkit 规则，构成破坏性变更。

rss · LWN.net · 10月20日 18:36

**「背景」** setuid 和 setgid 二进制在执行时会获得文件所有者或所属组的权限，因此程序一旦存在缺陷，就可能成为提权入口；SUSE 的安全团队此前已在 openSUSE 打包规范中禁止未经审查和明确许可的 setuid/setgid 二进制。Linux 内核的 no\_new\_privs 标志会让后续 execve\(\) 不再因 setuid、setgid 或文件 capabilities 而增加权限，并且该设置会跨 fork\(\)、clone\(\) 和 execve\(\) 持续生效。Kukuk 的方案正是尝试通过 systemd 为 PID 1 启用 NoNewPrivileges=yes，把这一限制推广到全系统。

**「影响」** 对使用 sudo 的服务器管理员而言，采用该路线意味着需要把 sudoers 规则迁移为 polkit 规则，而不是仅替换二进制；其他被替换工具则被要求保持配置和行为不变。

**标签**: `#Linux security`, `#setuid`, `#SUSE`, `#system hardening`, `#open source`

---

<a id="item-tech-news-10"></a>
### [Kangrejos 2026 谨慎讨论用 Rust 重写 XArray](https://lwn.net/Articles/1100520/) ⭐️ 7.0/10

在 Kangrejos 2026 上，Daniel Gomez 提议试验用 Rust 重写内核的 XArray 数据结构，目标是减少 XFS 大块大小支持中难以发现的缺陷。他提到 XFS 曾因 folio 支持引入文件系统损坏，问题多年未被发现，最终定位到 XArray API 的锁误用；XArray 在内核中有 351 个使用点、126 个维护者条目，2026 年已有 3 个 CVE 与误用有关。与会者持谨慎态度：核心内核功能在 Rust 中重写面临架构支持、为 C 调用者提供接口的接受度等问题。目前这仍是探索性讨论，没有作出重写决定，也没有已合入的代码。

rss · LWN.net · 10月20日 15:46

**「背景：XArray 与 XFS 大块尺寸支持」** XArray 是内核中把基数树（radix tree）封装成可扩展数组的数据结构；简单接口 xa\_\*\(\) 自动处理锁，高级接口 xas\_\*\(\) 则把加锁责任交给调用者，XFS 使用的正是后者。XFS 自 2021 年底加入 large folio 支持后，2023 年 6 月出现文件间页面串写的损坏问题；排查发现根因是 XFS 代码未加锁就调用 XArray 的高级接口，开发者最终回退 folio 支持并重构加锁方式，这也让依赖该转换的大块尺寸支持被迫推迟。

**「影响」** 短期内对 XFS 用户没有直接的兼容性或行为变化，因为该重写仍处于实验和讨论阶段；若继续推进，最先的现实约束是 351 个内核使用点和 126 个维护者条目如何迁移或保持 C 接口兼容。Tyr GPU 驱动提供了一个具体落点：其作业队列原计划使用 C 版 XArray，开发者表示若 Rust 版出现，Tyr 可能成为首个 Rust 使用者。

**标签**: `#rust`, `#linux-kernel`, `#xfs`, `#xarray`, `#filesystems`

---

<a id="item-tech-news-11"></a>
### [OpenBSD 8.0 发布：arm64 支持休眠，amd64 内核空间达 512GB](https://lwn.net/Articles/1101536/) ⭐️ 7.0/10

OpenBSD 8.0 已发布。该版本为 arm64 平台增加休眠支持，将 amd64 的内核虚拟地址空间扩大到 512GB，并改进了支持高通 Wi-Fi 6 设备的 qwx 驱动。官方还列出了更多变更，细节见完整更新日志。

rss · LWN.net · 10月20日 13:07

**「背景」** OpenBSD 的 arm64 休眠功能会把内存状态写入磁盘后断电，恢复时再读回，因此内核必须在睡眠和恢复路径上完整保存设备与内存状态；amd64 的内核虚拟地址空间则是内核用来映射自身代码、数据及物理内存的地址范围，扩大该空间可缓解大内存机器上的映射压力。此前 10 月 17 日的日报曾报道，研究人员演示了 OpenBSD 内核中一个存在 37 年的漏洞，但当时材料未说明受影响的具体组件、版本范围与修复状态，因此无法从现有信息确认 8.0 是否包含相关修复。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://calif.io/research/big-fish">2026-10-17 — Big Fish：利用 OpenBSD 存在 37 年的内核漏洞</a></li>

</ul>
</details>

**标签**: `#openbsd`, `#operating-systems`, `#bsd`, `#release`, `#arm64`

---

<a id="item-tech-news-12"></a>
### [DeepSeek 据报深度参与华为未来 AI 芯片设计](https://www.theinformation.com/articles/deepseek-shaping-huaweis-ai-chips-growing-challenge-nvidia) ⭐️ 7.0/10

据 The Information 援引知情人士报道，DeepSeek 正深度参与华为未来 AI 芯片设计：华为工程师长期驻场 DeepSeek 办公室，并将 DeepSeek 在模型计算和处理器间数据传输方面的建议，纳入面向 2027 年及以后推出的芯片。报道称，这种超出常规供应商沟通的合作可能降低中国构建前沿 AI 模型时对英伟达技术的依赖；但 DeepSeek 并未放弃英伟达，仍在寻求获取其先进处理器。上述内容来自未具名消息源，尚无独立验证。

telegram · zaihuapd · 10月20日 05:10

**「背景」** 此前已有迹象显示 DeepSeek 与华为的绑定超出普通采购关系：Horizon 9 月 5 日的日报曾援引彭博社报道称，DeepSeek 计划在内蒙古新建数据中心部署至少 16 万颗华为升腾 950DT 芯片。Horizon 9 月 18 日的日报则报道，华为在上海发布新一代 Ascend 960，但要到 2027 年才商用——这与本次报道中“涉及 2027 年及以后推出的芯片”的时间窗口吻合，说明 DeepSeek 此次是从买方变成参与设计方。两项早期报道同样基于匿名消息源，未获 DeepSeek 或华为确认。

**「影响」** 若该合作按报道推进，计划在 2027 年及以后采用华为 AI 芯片的训练和推理团队，可能获得更贴合 DeepSeek 模型计算与处理器间数据传输特点的硬件设计。但报道未披露具体芯片规格、软件兼容性或性能提升，现有 DeepSeek 工作负载能否迁移、能获得多少收益仍无法判断，采购方宜将英伟达供应与华为软件栈适配作为并行方案评估。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.bloomberg.com/news/articles/2026-09-04/deepseek-plans-big-huawei-ai-chip-order-to-power-new-data-center">2026-09-05 — DeepSeek 拟在内蒙古部署 16 万颗华为升腾芯片</a></li>
<li><a href="https://www.bloomberg.com/news/articles/2026-09-16/huawei-set-to-unveil-china-s-best-answer-to-nvidia-ai-chip-reign">2026-09-18 — 华为将发布 Ascend 960 AI 芯片，2027 年商用</a></li>

</ul>
</details>

**标签**: `#AI chips`, `#Huawei`, `#DeepSeek`, `#Nvidia`, `#China AI`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [Shopify 从 React Native 转向原生开发](https://blog.bytebytego.com/p/why-shopify-migrated-from-react-native) ⭐️ 5.0/10

rss · ByteByteGo · 10月20日 15:31

**「背景」** 2020 年 Shopify 全面采用 React Native，是为了避免 iOS 与 Android 各写一遍、团队被平台栈割裂，并维持双端功能对齐；但框架本身、性能优化和依赖升级也带来持续维护成本。到 2025 年，作者认为 AI 编码代理显著改变了这笔账：让 Swift 与 Kotlin 双端实现的成本不再像过去那样高。

**「方案」** Shopify 先用 Swift 和 Kotlin 重写部分核心模块做试验，发现代理能拿一个平台的实现当参考生成另一个平台代码，再由开发者按平台惯例审查；Shopify 称，代理已把重复实现的负担降到不再像 2020 年那样主导决策，因此他们选择全新原生重写（greenfield），先迁面向消费者的 Shop 应用，再迁拥有 300 多个屏幕、小组件和 Watch 应用的商家版。为避免模型一次性重写大功能导致代码难维护、难审查，团队构建 Helix，把迁移拆成有顺序的小检查点：先确定屏幕结构与导航，再逐步处理订单摘要等部分；每个检查点都要经过行为测试、与旧版对比的视觉审查、对抗式代码审查和开发者复核，才能成为下一块的基础。应用逻辑与 UI 分离，业务逻辑可无头运行，并通过 CLI 暴露状态和操作，让代理直接断言状态而不是解析截图。按文中引用的 Shopify 数据，Shop 原生版 12 周上线；iOS 启动从 3200 ms 降至约 2400 ms，Android 从约 4400 ms 降至 2200 ms，Android 包体从 293 MB 降至 184 MB，无崩溃会话占比上升。不过这篇二手整理没有说明 300 多个屏幕的视觉审查究竟如何执行，这仍是该方案未展开的环节。

**「启示」** 作者的核心结论是：AI 代理让双端原生开发重新可行，但大规模迁移能否安全推进，取决于能否用小型可审查检查点和快速、可断言的反馈闭环来验证代理产出，而不只是代码生成能力本身。

**标签**: `#react-native`, `#mobile-development`, `#ai-coding-agents`, `#migration-strategy`, `#developer-tooling`

---