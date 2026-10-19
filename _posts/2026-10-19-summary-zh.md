---
layout: default
title: "Horizon Summary: 2026-10-19 (ZH)"
date: 2026-10-19
lang: zh
---

> 从 29 条内容中筛选出 7 条重要资讯。

---

**科技新闻**
1. [vLLM v0.32.0 发布：新增结构化决策端点并扩展低精度 KV 缓存](#item-tech-news-1) ⭐️ 8.0/10
2. [Linux 内核 CVE-2026-99999 可致 KVM 访客逃逸](#item-tech-news-2) ⭐️ 8.0/10
3. [混合智能体：潜空间推理、文本行动的 LLM Agent](#item-tech-news-3) ⭐️ 7.0/10
4. [RepRapMicron：开源微米级 3D 打印项目 wiki 引发讨论](#item-tech-news-4) ⭐️ 7.0/10
5. [Open MicroManipulator：开源亚微米级三维运动平台](#item-tech-news-5) ⭐️ 7.0/10
6. [Linux 7.3 内核发布：逾 1.8 万次提交，7.4 合并窗口开启](#item-tech-news-6) ⭐️ 7.0/10
7. [Google 开源 Harness²：不改权重递归优化 LLM 智能体](#item-tech-news-7) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [vLLM v0.32.0 发布：新增结构化决策端点并扩展低精度 KV 缓存](https://github.com/vllm-project/vllm/releases/tag/v0.32.0) ⭐️ 8.0/10

vLLM v0.32.0 发布，包含 814 个提交和 363 名贡献者；新增默认提供的 \`POST /v1/systemone\` 端点，用于对结构化状态回答 \`choice\`、\`noul\` 和 \`score\` 问题，并支持 \`Cloudflare/clef-omni\` 等模型。新增 \`--tool-call-parser hf\` 与 \`--reasoning-parser hf\`，通过读取 checkpoint 的 \`response\_template\`，让自带该模板的模型无需专用解析器，Python 和 Rust 前端均支持。低精度 KV 缓存扩展到更多 NVIDIA 架构和 ROCm：NVFP4 覆盖 SM8x、SM12x 和 SM90，GLM-5.x 在 SM100 默认使用 FP8 KV 缓存，发布说明引用的 PR 基准称每个 rank 的 KV 内存减半、吞吐提高 2.3-5.5%，但 TTFT 增加 7-11%；ROCm 新增 \`ultraquant\_4bit\`，密度约为 FP8 的 2 倍。该版本还包含破坏性变更：停止支持 Python 3.10、默认限制 CORS 来源、收紧 transformers/tokenizers 版本范围，并移除 cascade attention 等。

github · khluu · 10月18日 06:50

**「背景」** Horizon 2026 年 8 月 5 日的日报曾解释，长上下文推理的成本主要来自 KV 缓存：模型需要为每个已处理的 token 保留注意力键值，上下文越长，显存占用越大。vLLM v0.32.0 的多项改动正针对这一瓶颈，例如 GLM-5.x 在 SM100 上默认启用 FP8 KV 缓存以把每卡 KV 显存减半，ROCm 端新增的 4-bit \`ultraquant\_4bit\` 缓存密度约为 FP8 的两倍。与此同时，该版本把依赖下限提高到 \`transformers&gt;=5.16.1,&lt;5.20.0\` 和 \`tokenizers&gt;=0.23.2\`，并停止支持 Python 3.10，升级前需先核对运行环境。

**「影响」** 对自建推理服务的团队，升级前应检查仍在使用 Python 3.10 的环境、依赖宽松跨域设置的浏览器客户端，以及依赖 Responses API 旧推理流事件名或旧 \`max\_tokens\` 上下文预留行为的集成，因为这些都在此版本中发生了破坏性变更。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://blog.bytebytego.com/p/why-an-llms-memory-gets-expensive">2026-08-05 — LLM 长上下文推理为何昂贵：KV 缓存与优化</a></li>

</ul>
</details>

**标签**: `#vLLM`, `#LLM inference`, `#KV cache`, `#structured outputs`, `#release`

---

<a id="item-tech-news-2"></a>
### [Linux 内核 CVE-2026-99999 可致 KVM 访客逃逸](http://pwn.ai/) ⭐️ 8.0/10

PWN.AI 研究人员披露 Linux 内核漏洞 CVE-2026-99999：网络校验和元数据可在内核完成校验后改写 IPv4 头，导致 32 字节主机内存信息泄露。该团队称已在自有 KVM 环境中演示了访客到宿主机逃逸，但现有报道未说明受影响内核版本或具体利用条件。Linux 主线内核已于 2026 年 10 月 14 日合并修复补丁，报道未说明各发行版是否已提供回移更新。

telegram · zaihuapd · 10月18日 09:47

**「背景：校验和卸载路径与已发布的稳定版修复」** 该漏洞位于内核网络栈的 skb\_checksum\_help\(\)，也就是校验和卸载（checksum offload）路径：当带有错误校验和元数据的 IPv4 数据包被处理时，内核可能在完成校验和计算之后仍改写 IPv4 头。Horizon 10 月 16 日的日报曾报道，Greg Kroah-Hartman 当天发布 7.2.11、6.18.57、6.12.113、6.6.159、6.1.190、5.15.223 和 5.10.272 七个稳定版内核，均包含对 CVE-2026-99999 的修复；补丁作者 Michael S. Tsirkin 称此类数据包可能“破坏网络头并造成一系列麻烦”，这说明在本条报告出现之前，修复已进入稳定分支。

**「影响与处置」** 对运行不受信任 KVM 访客的多租户宿主机，在宿主机内核尚未包含修复时，恶意访客可能读取宿主机内存并尝试逃逸；运维方应核对内核版本，并尽快应用主线修复或发行版回移补丁。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://lwn.net/Articles/1100611/">2026-10-16 — Linux 发布七个稳定版内核，修复 skb_checksum_help() 严重漏洞</a></li>

</ul>
</details>

**标签**: `#Linux kernel`, `#KVM`, `#virtualization security`, `#guest escape`, `#vulnerability disclosure`

---

<a id="item-tech-news-3"></a>
### [混合智能体：潜空间推理、文本行动的 LLM Agent](https://arxiv.org/abs/2610.18861) ⭐️ 7.0/10

一篇 arXiv 论文提出“混合推理智能体”（Hybrid Reasoning Agents）：模型在潜空间（latent space）中完成推理，再通过文本动作与外部环境交互，从而把内部思考与可观测的输出动作分开。作者同时放出配套资源：GitHub 上的 togethercomputer/HybridAgent 代码库、HuggingFace 上的模型与数据集合，以及论文第 5 节的评测结果。这属于论文加开源代码、模型的发布，而非已交付的产品能力；实际效果需以论文评测和第三方复现为准。

hackernews · allinonai · 10月18日 20:48 · [社区讨论](https://news.ycombinator.com/item?id=50145337)

**「技术背景」** 常规 LLM 智能体以文本形式输出思维链，每一步推理都要解码成 token，因此速度受逐步生成限制，内部状态也难以直接观察。HybridAgent 的关键机制是 HybridLink：它把最后一层隐藏状态映射回输入嵌入空间，让模型可以在潜在空间里做循环式内部推理，再切回文本模式执行工具调用并接受外部监控（tool-2-2）。潜在推理与文本动作因此处在同一个生成过程中，而非两套分离的流程。

**「部署与复现」** 对想直接试用的开发者来说，当前的落地障碍在推理栈而非 API：有评论者用 llama.cpp（前一天的版本）加载 bartowski 的 8-bit 量化 14B 模型，在一个网页搜索加摘要的简单请求上反复循环同一段文字约五分钟直至耗尽回合预算，并推测可能需要 llama.cpp 侧更新才能适配该模型。这说明量化本地部署路径尚未得到验证，复现前应优先确认官方支持的推理框架与精度配置。

**「社区讨论」** 讨论集中在两点：一是上述 14B 量化模型在 llama.cpp 中的循环失败，被视为对本地可运行性的质疑；二是设计取向之争，有评论者建议既然生成文本时已付出接近完整潜空间模式的计算成本，不如让模型在文本模式下也持续进行潜空间推理，另有人期待把该混合方案用于 Qwen 3.8 27B 以减少其推理输出中的重复复述。这些均为个人观点与个例体验，尚不构成对该方法有效性的共识。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/html/2610.18861v1">Hybrid Reasoning Agents - arXiv.org</a></li>

</ul>
</details>

**标签**: `#LLM agents`, `#latent reasoning`, `#hybrid reasoning`, `#arxiv paper`, `#open-source models`

---

<a id="item-tech-news-4"></a>
### [RepRapMicron：开源微米级 3D 打印项目 wiki 引发讨论](https://github.com/VikOlliver/RepRapMicron/wiki) ⭐️ 7.0/10

RepRapMicron 的项目 wiki 在 Hacker News 上引起关注，该项目试图沿 RepRap 的开源硬件路线，把 3D 打印推进到微米尺度。此次提供的条目只是指向该 wiki 的链接，未附可核验的打印精度、速度、材料清单或第三方复现结果，因此它应被视为进行中的开源探索，而非已展示的突破。讨论的焦点也不在当前能力，而在这类设备若成熟，对芯片类设计从软件走向实体硬件意味着什么。

hackernews · RobotToaster · 10月18日 13:48 · [社区讨论](https://news.ycombinator.com/item?id=50141076)

**「背景」** RepRapMicron（又称 μRepRap）是开源 RepRap 3D 打印机项目的延伸，目标是把微米级制造推广到更广泛的用户群体。项目资料将其描述为一套三轴 3D 打印机构，精度可达几微米、特征尺寸约为 10–20 微米，并设计为兼容标准 3D 打印机和 CNC 控制器，可由普通 3D 打印或 CNC 爱好者组装。

**「对开发者的实际影响」** 对关注开源硬件的开发者来说，目前可做的只有阅读该 wiki，以及社区评论中指向的相关视频资料；在项目给出可复现的精度与工艺参数之前，它还不能作为现有微纳加工或芯片制造流程的替代或兼容方案。

**「社区讨论」** mikewarot 把当前进展类比为 1790 年代 Ramsden 的圆分度、Maudslay 的螺纹车床和 Wilkinson 的镗床，认为其意义在于把原本依赖手艺的精密加工变成可稳定制造的东西。samayashar 期待能廉价、可持续地把只存在于软件里的芯片设计打印出来；godber 则以“18 个月后就能自己做内存”调侃其时间尺度，le-mark 则质疑让机器打印自身千分之一尺寸版本的设想究竟为了什么。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://reprap.org/wiki/RepRapMicron">RepRapMicron - RepRap GitHub - VikOlliver/RepRapMicron: μRepRap - A 3D printer ... RepRapMicron Micron Scale 3D Printer by vik - Thingiverse RepRapMicron Micron Scale 3D Printer by vik - Thingiverse RepRapMicron - The Next Small Thing In 3D Printing - Vik ... RepRapMicron – Hackaday RepRapMicron/Presentations at main · VikOlliver/RepRapMicron</a></li>
<li><a href="https://github.com/VikOlliver/RepRapMicron">GitHub - VikOlliver/RepRapMicron: μRepRap - A 3D printer ...</a></li>
<li><a href="https://www.thingiverse.com/thing:7029371">RepRapMicron Micron Scale 3D Printer by vik - Thingiverse</a></li>

</ul>
</details>

**标签**: `#open-source hardware`, `#3D printing`, `#micron-scale fabrication`, `#RepRap`, `#hardware`

---

<a id="item-tech-news-5"></a>
### [Open MicroManipulator：开源亚微米级三维运动平台](https://github.com/0x23/MicroManipulatorStepper) ⭐️ 7.0/10

Open MicroManipulator 是一个在 Hacker News 上受到关注的开源硬件项目，目标是为硬件爱好者和精密仪器搭建者提供亚微米级三维运动控制平台。该项目以 GitHub 仓库形式发布，相关讨论集中在 DIY 纳米定位的替代方案和实际搭建经验上。现有条目没有提供独立测量数据或完整复现信息，因此其亚微米定位能力和实际可用性仍需以项目文档和第三方验证为准。

hackernews · \_Microft · 10月18日 11:16 · [社区讨论](https://news.ycombinator.com/item?id=50140001)

**「背景」** 亚微米级定位通常依赖压电致动器或柔性铰链机构，成本较高。Open MicroManipulator 则采用现成步进电机加机械减速的方案，据项目介绍可实现低至 50 纳米的步进，用于光学对准、电子元件探测和显微观察等场景。

**「社区讨论」** 评论者指出 RepRap Micron 在做类似的事，并讨论了用压电粘滑致动器实现潜在亚纳米分辨率、成本约 1000 美元的 DIY 路线，同时引用了一篇相关论文。还有评论者称正在搭建该项目的非电动手动版本，准备改装后用于点衍射干涉仪；另一人表示刚花了一个周末组装该项目。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/0x23/MicroManipulatorStepper">GitHub - 0x23/MicroManipulatorStepper: A sub-micrometer 3D ...</a></li>
<li><a href="https://daily.dev/posts/open-micromanipulator-a-sub-micrometer-3d-motion-control-plattform-xceqae2du">Open MicroManipulator – A sub-micrometer 3D motion control ...</a></li>

</ul>
</details>

**标签**: `#open-source hardware`, `#precision motion control`, `#DIY instrumentation`, `#sub-micrometer positioning`, `#nanopositioning`

---

<a id="item-tech-news-6"></a>
### [Linux 7.3 内核发布：逾 1.8 万次提交，7.4 合并窗口开启](https://lwn.net/Articles/1101143/) ⭐️ 7.0/10

Linus Torvalds 已按预期发布 Linux 7.3 内核。据 LWN 统计，本次发布创下纪录：包含 18,765 个非合并提交，来自 3,021 名开发者，其中 807 人是首次参与内核开发。已列出的重要变更包括 binfmt\_misc 的扩展、面向大型系统的分组调度改进、新增“所有操作都失败”的 failfs 文件系统、fchroot\(\) 系统调用、BPF 程序的全局 per-CPU 数据、sched\_ext 子调度器特性的完成、虚拟机的 working-set 跟踪、ntfs3 的备用数据流支持，以及一批 SMB 服务端改进。随着 7.3 发布，7.4 的合并窗口于次日开启，但 Torvalds 表示正值年度家庭休假，他当天大部分时间会在船上和水下，因此合并节奏在一段时间内将不太常规。

rss · LWN.net · 10月18日 23:45

**「此前的开发进展」** Horizon 2026 年 8 月 21 日的日报曾报道 7.3 合并窗口开启：当时已有 2346 个非合并变更集进入主线，重点包括多处理器系统上的组调度权重缩放重构、binfmt\_misc 扩展，以及新增 failfs 文件系统与 fchroot\(\) 系统调用；9 月 1 日的日报则记录了 7.3-rc1 以 15,267 个非合并变更集收官，是内核历史上 -rc1 提交数第二高的版本。此次正式版把非合并提交数推高到 18,765 个、来自 3,021 名开发者，并按计划在发布次日开启 7.4 合并窗口。

**「影响」** 对内核开发者来说，7.4 合并窗口虽已开启，但维护者在假期期间的合并安排可能异常，提交与跟进的时间预期需要相应放宽。希望评估新接口的人可以在 7.3 上直接试用 failfs、fchroot\(\) 与 sched\_ext；LWN 的合并窗口摘要第一、第二部分及 KernelNewbies 7.3 页面给出了比发布公告更细的说明。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://lwn.net/Articles/1089244/">2026-08-21 — Linux 7.3 合并窗口开始：组调度重构与架构弃用更新</a></li>
<li><a href="https://lwn.net/Articles/1089791/">2026-09-01 — Linux 7.3 合并窗口收官：提交量创历史第二</a></li>

</ul>
</details>

**标签**: `#Linux kernel`, `#open source`, `#kernel release`, `#systems software`

---

<a id="item-tech-news-7"></a>
### [Google 开源 Harness²：不改权重递归优化 LLM 智能体](https://github.com/google-research/harness2) ⭐️ 7.0/10

Google Research 开源了 Harness²，一个通过两层递归在不更新模型权重的前提下优化 LLM 智能体表现的框架。据项目方说法，该框架在 WorkBuddy-Bench 等测试中最高带来 11.5 分提升，并支持并行与顺序两种递归模式，已集成多款基准测试，以 Apache 2.0 协议发布。上述分数为项目方自述，目前来源仅为一条简报，尚无独立复现或实现细节披露。

telegram · zaihuapd · 10月18日 11:24

**「背景」** 这里的“harness”指包裹 LLM 的执行脚手架；Harness² 优化的是这一层，而不是模型权重。按项目与论文页面的说明，它把递归分成任务级的反复改进和跨任务的 harness 持续学习两层，并强调在开放环境中处理设计时未见过的新任务。

**「影响」** 对智能体开发者来说，这意味着可以在不重新训练、不改动模型权重的情况下，直接套用该框架及其已集成的基准来调优 agent 流程，Apache 2.0 协议也便于修改和商用集成。但由于缺少实现细节与第三方复现，11.5 分的提升能否迁移到自有任务上仍需自行验证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/google-research/harness2">GitHub - google - research / harness 2 · GitHub</a></li>
<li><a href="https://huggingface.co/papers/2610.14224">Paper page - Harness ^2: Recursive Agent Harnessing for an Open...</a></li>

</ul>
</details>

**标签**: `#LLM agents`, `#recursive optimization`, `#open-source frameworks`, `#Google Research`, `#benchmarking`

---