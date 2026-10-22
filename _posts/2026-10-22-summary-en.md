---
layout: default
title: "Horizon Summary: 2026-10-22 (EN)"
date: 2026-10-22
lang: en
---

> From 37 items, 15 important content pieces were selected

---

**Technology News**
1. [David Harvey Analyzes Proposed o\(n log n\) Integer Multiplication Algorithm](#item-tech-news-1) ⭐️ 8.0/10
2. [PHP Releases Emergency Updates Across PHP 8.x for Critical RCE Vulnerabilities](#item-tech-news-2) ⭐️ 8.0/10
3. [Analysis Examines Huawei Ascend 950PR Architecture and DeepSeek Model Integration](#item-tech-news-3) ⭐️ 8.0/10
4. [Quad9 Announces Exit from France Over Court-Ordered DNS Blocking](#item-tech-news-4) ⭐️ 7.0/10
5. [eMudhra Announces Exit from Global SSL/TLS Certificate Business](#item-tech-news-5) ⭐️ 7.0/10
6. [Anthropic Introduces Claude Duet Personal Assistant with Waitlist Access](#item-tech-news-6) ⭐️ 7.0/10
7. [Optimized Polygon Triangulation Library Processes 3.7M Map Polygons in 489 ms](#item-tech-news-7) ⭐️ 7.0/10
8. [Unpatched Linux Kernel Vulnerabilities Accidentally Disclosed on Public Mailing List](#item-tech-news-8) ⭐️ 7.0/10
9. [Amazon Detects Pre-Disclosure PHP2Shell Exploitation in Honeynet Telemetry](#item-tech-news-9) ⭐️ 7.0/10
10. [Railway Discloses Security Incident Compromising Environment Secrets](#item-tech-news-10) ⭐️ 7.0/10
11. [Carbon-X Open 14.8B Model Jointly Trains on DNA and Text](#item-tech-news-11) ⭐️ 7.0/10
12. [Australian Court Orders Apple to Allow Alternative iOS App Stores by 2027](#item-tech-news-12) ⭐️ 7.0/10
13. [Smart TVs Transmit Viewing Data and Identifiers Despite Disabling ACR](#item-tech-news-13) ⭐️ 7.0/10
14. [miHoYo and Tsinghua Open-Source GameScaling Game Action Models](#item-tech-news-14) ⭐️ 7.0/10
15. [Oracle Issues Alert for Critical Java SE and GraalVM JSSE Vulnerability](#item-tech-news-15) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [David Harvey Analyzes Proposed o\(n log n\) Integer Multiplication Algorithm](https://web.maths.unsw.edu.au/~davidharvey/research/subnlogn.pdf) ⭐️ 8.0/10

Mathematician David Harvey published an analysis examining a recently proposed $o\(n \\log n\)$ integer multiplication algorithm, assessing claims that beat the long-standing $O\(n \\log n\)$ theoretical complexity barrier. The paper evaluates a trio of technical papers detailing the sub-$n \\log n$ arithmetic bounds. Independent researchers simultaneously announced that the result has been formally verified in the Lean proof assistant using Mathlib&\#x27;s Turing machine model.

hackernews · craigcitro · Oct 22, 02:30 · [Discussion](https://news.ycombinator.com/item?id=50190455)

**「Integer Multiplication Bounds」** In 1971, Arnold Schönhage and Volker Strassen conjectured that multiplying two n-bit integers takes O\(n log n\) bit operations, an upper bound proven by David Harvey and Joris van der Hoeven in 2019. Any algorithm operating in strictly sub-n log n time, or o\(n log n\), would surpass this milestone and contradict long-held expectations regarding the fundamental computational limits of integer arithmetic.

**「Community Discussion」** Commenters highlighted an active Lean repository tracking improvements to the formal bound exponent, while noting excerpts where the author described using an LLM to help digest the dense underlying papers.

<details><summary>References</summary>
<ul>
<li><a href="https://hal.science/hal-02070778v2/file/nlogn.pdf">Integer multiplication in time O(n log n) - hal.science</a></li>
<li><a href="http://www.mmrc.iss.ac.cn/~xgao/cls2023/pap21-IntMult.pdf">Integer multiplication in time O(n log n) - mmrc.iss.ac.cn</a></li>

</ul>
</details>

**Tags**: `#algorithms`, `#theoretical computer science`, `#computational complexity`, `#formal verification`

---

<a id="item-tech-news-2"></a>
### [PHP Releases Emergency Updates Across PHP 8.x for Critical RCE Vulnerabilities](https://simonwillison.net/2026/Oct/21/php-security-release/) ⭐️ 8.0/10

The PHP project has issued emergency security releases across all PHP 8.x branches to resolve two remote code execution vulnerabilities carrying a CVSS score of 9.2. The release was moved forward by 24 hours after leaked CVE identifiers and the accidental publication of a working proof-of-concept demonstration video by security firm Calif accelerated exploit development. Originally identified in August 2026 by Wiz Research, the vulnerabilities enable unauthenticated remote code execution and were confirmed against targets including WordPress and Drupal.

rss · Simon Willison · Oct 21, 18:41

**「Disclosure Timeline」** Wiz Research originally identified the remote code execution vulnerabilities in August 2026, confirming unauthenticated exploits against Drupal and WordPress before coordinating a planned release with the PHP security team for October 22. The coordinated timeline collapsed on October 20 after CVE identifiers leaked online and security firm Calif mistakenly published a demonstration video, accelerating exploit development across the community.

**「Immediate Patching Required」** Administrators managing PHP environments—especially those running applications like WordPress or Drupal—must urgently upgrade to the patched PHP 8.x releases to protect against unauthenticated remote code execution enabled by publicly circulating exploit code.

**Tags**: `#php`, `#security`, `#vulnerabilities`, `#remote-code-execution`

---

<a id="item-tech-news-3"></a>
### [Analysis Examines Huawei Ascend 950PR Architecture and DeepSeek Model Integration](https://newsletter.semianalysis.com/p/huawei-deepseek) ⭐️ 8.0/10

SemiAnalysis published a technical investigation detailing the hardware and software collaboration between Huawei and DeepSeek. The report evaluates Huawei&\#x27;s Ascend 950PR accelerator through microbenchmarks alongside an architectural analysis of the DSv4.1 Flash model and its native support on Ascend silicon. Specific benchmark figures and architectural constraints are detailed in the full publication.

rss · Semianalysis · Oct 21, 17:34

**「Background」** DeepSeek partners closely with Huawei by providing pre-release model weights to support Day-0 optimized software releases, including DeepSeek V4 and V4.1. This co-development is necessary because Ascend hardware features unique architectural characteristics, such as specific accumulator designs that require custom adaptations for attention mechanisms.

<details><summary>References</summary>
<ul>
<li><a href="https://newsletter.semianalysis.com/p/huawei-deepseek">The Huawei - DeepSeek Symbiosis</a></li>

</ul>
</details>

**Tags**: `#AI Hardware`, `#Huawei Ascend`, `#DeepSeek`, `#Microbenchmarks`, `#Semiconductors`

---

<a id="item-tech-news-4"></a>
### [Quad9 Announces Exit from France Over Court-Ordered DNS Blocking](https://quad9.net/news/blog/au-revoir-france/) ⭐️ 7.0/10

Public recursive DNS resolver Quad9 has announced plans to exit France following escalating legal disputes over court-mandated content blocking. The decision stems from rulings where standard IP-based geo-blocking measures were deemed noncompliant after plaintiffs demonstrated they could circumvent the restrictions using VPNs. To avoid contempt-of-court fines and mounting legal liabilities, the nonprofit provider is discontinuing its operational presence in the country.

hackernews · farrokhi · Oct 22, 14:32 · [Discussion](https://news.ycombinator.com/item?id=50195959)

**「Background」** French courts have increasingly targeted public recursive DNS resolvers with web-blocking injunctions, requiring providers to censor access to unauthorized sports streaming sites at the request of commercial broadcasters such as Canal+ \[tool-1-2\]. Quad9 has historically contested court-mandated domain filtering across Europe, having previously fought a multi-year copyright blocking battle in Germany \[tool-1-2\].

**「Community Discussion」** Commenters noted that holding recursive DNS resolvers liable when geofences are bypassed with VPNs creates an untenable compliance burden for infrastructure operators. Others pointed out that Quad9 is following a precedent set by Cisco, which previously withdrew OpenDNS services from France amid similar piracy-blocking court orders.

<details><summary>References</summary>
<ul>
<li><a href="https://completemusicupdate.com/quad9-vows-to-fight-absurd-web-block-injunction-in-france/">Quad 9 vows to fight “absurd” web- block injunction in France</a></li>

</ul>
</details>

**Tags**: `#DNS`, `#internet infrastructure`, `#networking`, `#tech policy`

---

<a id="item-tech-news-5"></a>
### [eMudhra Announces Exit from Global SSL/TLS Certificate Business](https://emudhra.com/en/press-release/emudhra-to-exit-global-ssl-tls-certificate-business) ⭐️ 7.0/10

Certificate Authority eMudhra has announced its exit from the global SSL/TLS certificate business following public scrutiny and browser trust investigations over severe private key security practices. The withdrawal follows reports from security researchers that intermediate CA certificates were compromised, prompting browser root programs including Google Chrome and Mozilla to investigate and revoke trust. In its communications, eMudhra noted that its global SSL/TLS certificate infrastructure operates independently from its broader domestic and enterprise trust operations.

hackernews · bo0tzz · Oct 22, 13:33 · [Discussion](https://news.ycombinator.com/item?id=50195110)

**「Browser Trust Oversight」** Public Certificate Authorities must adhere to strict operational and private key security standards enforced by major browser root store programs to maintain global web trust. The exit follows a vulnerability disclosure involving compromised intermediate CA certificates that prompted formal inquiries and scrutiny from browser root programs.

**「Impact」** Organizations relying on eMudhra-issued SSL/TLS certificates must migrate approximately 30,000 active certificates to alternative Certificate Authorities as browsers including Chrome and Firefox block compromised intermediate certificates and advance plans to distrust the root CA, while non-browser environments and custom trust stores require explicit software updates.

**「Community Discussion」** Commenters criticized eMudhra&\#x27;s characterization of the controversy as disproportionate social media amplification, arguing that weak private keys represented fundamental cryptographic and operational negligence. Participants also tracked disparities in browser ecosystem responses, contrasting Google Chrome&\#x27;s rapid revocation against days-long delays in Apple updating its trust store.

<details><summary>References</summary>
<ul>
<li><a href="https://www.marketscreener.com/news/india-s-emudhra-to-exit-global-ssl-tls-certificate-business-ce785cdedb8af125">India&#x27;s eMudhra to exit global SSL / TLS certificate business</a></li>
<li><a href="https://cyberinsider.com/google-apple-mozilla-rush-to-block-compromised-emudhra-certificates/">Google, Apple, Mozilla rush to block compromised eMudhra ...</a></li>
<li><a href="https://www.rescana.com/post/emudhra-intermediate-ca-key-compromise-october-2026">eMudhra CA Key Compromise: Chrome and Firefox Have Blocked It ...</a></li>

</ul>
</details>

**Tags**: `#cybersecurity`, `#pki`, `#ssl-tls`, `#web-infrastructure`, `#cryptography`

---

<a id="item-tech-news-6"></a>
### [Anthropic Introduces Claude Duet Personal Assistant with Waitlist Access](https://claude.com/product/claude-duet) ⭐️ 7.0/10

Anthropic has introduced Claude Duet, a new personal assistant product under the Claude platform. Initial access is being offered through a waitlist sign-up, though full technical specifications and rollout schedules remain unannounced in the primary listing.

hackernews · kuberwastaken · Oct 21, 19:14 · [Discussion](https://news.ycombinator.com/item?id=50186037)

**「Background」** Frontier AI labs have increasingly expanded beyond standard conversational chatbots toward proactive agents capable of coordinating tasks across connected user applications \[tool-1-2, tool-1-3\]. Claude Duet marks Anthropic&\#x27;s entry into dedicated personal assistant products, arriving alongside similar agent offerings from competitors such as OpenAI&\#x27;s Dots and Meta Muse \[tool-1-3\].

**「Community Discussion」** Commenters criticized the onboarding flow for requiring a separate waitlist sign-up rather than integrating directly into existing authenticated Claude chat sessions. Others compared assistant experiences across major AI providers, discussing whether non-real-time personal assistant tasks allow labs to run inference more efficiently through batch scheduling.

<details><summary>References</summary>
<ul>
<li><a href="https://support.claude.com/en/articles/17631495-get-started-with-claude-duet">Get started with Claude Duet | Claude Help Center</a></li>
<li><a href="https://www.engadget.com/2293646/claude-duet-is-anthropics-answer-to-meta-muse-and-openai-dots/">Claude Duet is Anthropic&#x27;s answer to Meta Muse and OpenAI ...</a></li>

</ul>
</details>

**Tags**: `#artificial intelligence`, `#anthropic`, `#claude`, `#ai assistants`, `#llms`

---

<a id="item-tech-news-7"></a>
### [Optimized Polygon Triangulation Library Processes 3.7M Map Polygons in 489 ms](https://globus.software/blog/2026/10/16/cutting-map-polygons/) ⭐️ 7.0/10

A technical benchmark and post introduces a high-performance polygon triangulation implementation capable of triangulating 3.7 million map polygons in 489 milliseconds, significantly outperforming the widely adopted Earcut library. The implementation targets massive geographic datasets to reduce preprocessing bottlenecks in mapping pipelines. Detailed comparisons highlight substantial throughput gains, though real-world deployment depends on binary size constraints and triangle quality.

hackernews · molind · Oct 22, 09:31 · [Discussion](https://news.ycombinator.com/item?id=50193170)

**「Polygon Triangulation in Vector Mapping」** Polygon triangulation decomposes complex two-dimensional vector geometries into triangles so GPUs can rasterize geographic features such as buildings and water bodies. Mapbox&\#x27;s lightweight Earcut library has long served as a widely adopted standard for this task across web and native mapping engines, leading Globus Software to release its own high-throughput triangulator, earstrip, under the same ISC license \[tool-1-1\].

**「Impact」** For developers compiling geometric processing pipelines to WebAssembly, earstrip significantly narrows the browser execution penalty compared to earcut.hpp, which loses 67% of its native performance in V8 compared to earstrip&\#x27;s 23% drop.

**「Community Discussion」** Earcut&\#x27;s author noted that Earcut intentionally foregoes complex optimizations to maintain a minimal 4.1 KB bundle size for browser map rendering, questioning the footprint of this implementation&\#x27;s WebAssembly build. Commenters also questioned whether the resulting narrow, sliver-shaped triangles might negatively affect GPU rasterization performance.

<details><summary>References</summary>
<ul>
<li><a href="https://globus.software/blog/2026/10/16/cutting-map-polygons/">Faster than earcut: triangulating 3 . 7 M map polygons in... | GLOBUS</a></li>
<li><a href="https://globus.software/blog/2026/10/16/cutting-map-polygons/">Faster than earcut : triangulating 3.7M map polygons in... | GLOBUS</a></li>

</ul>
</details>

**Tags**: `#computational-geometry`, `#algorithms`, `#performance-optimization`, `#graphics-programming`

---

<a id="item-tech-news-8"></a>
### [Unpatched Linux Kernel Vulnerabilities Accidentally Disclosed on Public Mailing List](https://www.phoronix.com/news/LKML-New-Trend-Vulnerabilities) ⭐️ 7.0/10

Trend Micro&\#x27;s Zero Day Initiative accidentally published multiple unpatched Linux kernel vulnerability reports directly to the public Linux Kernel Mailing List instead of a private security channel. The leaked reports detail local privilege escalations and severe flaws rated up to CVSS 9.0, reportedly touching kernel subsystems such as SMB and KSMBD. The accidental public disclosure exposes these flaws as zero-days before maintainers could coordinate and release upstream patches.

hackernews · mrkn1 · Oct 22, 11:12 · [Discussion](https://news.ycombinator.com/item?id=50193804)

**「Coordinated Disclosure Process」** Linux kernel security reports are typically handled through a private security mailing list so maintainers can investigate and develop patches under an embargo before public release. Bypassing this workflow exposes unpatched flaw details on public forums like the Linux Kernel Mailing List, eliminating lead time for fixes.

**「KSMBD Zero-Day Exposure」** Administrators running the Linux kernel&\#x27;s in-tree KSMBD server face immediate exposure to two publicly disclosed CVSS 9.0 remote code execution vulnerabilities—including one that can be triggered without network authentication—prior to security patches being merged into the mainline kernel.

**「Community Discussion」** Commenters noted that the highest-severity vulnerabilities target in-kernel SMB implementations like KSMBD, meaning deployments not running those modules may remain unaffected. Others debated how the leak relates to kernel maintainer policies around handling high volumes of automated or AI-assisted vulnerability reports.

<details><summary>References</summary>
<ul>
<li><a href="https://www.phoronix.com/news/LKML-New-Trend-Vulnerabilities">Several Linux Kernel Vulnerabilities Accidentally ... - Phoronix</a></li>
<li><a href="https://thehackernews.com/2026/10/two-cvss-90-linux-ksmbd-rce-flaws.html">Two CVSS 9.0 Linux KSMBD RCE Flaws Disclosed on Public ...</a></li>

</ul>
</details>

**Tags**: `#linux-kernel`, `#cybersecurity`, `#vulnerability`, `#open-source`

---

<a id="item-tech-news-9"></a>
### [Amazon Detects Pre-Disclosure PHP2Shell Exploitation in Honeynet Telemetry](https://aws.amazon.com/blogs/security/amazon-threat-intelligence-identifies-php2shell-exploitation-prior-to-public-disclosure-in-madpot/) ⭐️ 7.0/10

Amazon Threat Intelligence reported that its MadPot honeynet infrastructure detected exploitation activity targeting the PHP2Shell vulnerability on October 17, prior to public disclosure. The telemetry indicates that threat actors were actively probing or targeting the flaw in the wild before official coordinated advisories were released.

hackernews · cubefox · Oct 22, 11:50 · [Discussion](https://news.ycombinator.com/item?id=50194070)

**「Background」** PHP2Shell refers to a pair of remote code execution vulnerabilities, tracked as CVE-2026-109618 and CVE-2026-109619, affecting PHP versions 5.4 through 8.5. The flaws were publicly disclosed on October 20, 2026, prompting coordinated patching across Linux distributions and web hosting infrastructure.

**「Community Discussion」** Commenters questioned whether the early telemetry reflected viable remote code execution exploits rather than automated scanner probing, while also discussing friction regarding disclosure embargo timelines between vendors and the PHP project.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/PHP2Shell">PHP 2 Shell - Wikipedia</a></li>
<li><a href="https://aws.amazon.com/blogs/security/amazon-threat-intelligence-identifies-php2shell-exploitation-prior-to-public-disclosure-in-madpot/">Amazon Threat Intelligence identifies PHP 2 Shell exploitation prior ...</a></li>
<li><a href="https://ubuntu.com/blog/php2shell-vulnerability-fixes-available">php 2 shell ( CVE -2026-109618 and CVE -2026-109619) – PHP... | Ubuntu</a></li>

</ul>
</details>

**Tags**: `#security`, `#vulnerabilities`, `#php`, `#threat-intelligence`

---

<a id="item-tech-news-10"></a>
### [Railway Discloses Security Incident Compromising Environment Secrets](https://blog.railway.com/p/security-disclosure-wednesday-october-21st) ⭐️ 7.0/10

Cloud deployment platform Railway has issued a security disclosure regarding a security breach that compromised customer environment secrets and variables. In response to the incident, the platform paused deployments and builds, preventing users from immediately redeploying services to roll out rotated credentials.

hackernews · passenger · Oct 21, 21:58 · [Discussion](https://news.ycombinator.com/item?id=50188228)

**「Background」** Railway is a cloud deployment platform where developers host applications and store sensitive configuration data, including API keys and database credentials, as environment variables. In platform-as-a-service architectures, central secret stores are trusted to inject runtime configurations safely, making any breach of those stored values an immediate risk to connected downstream infrastructure.

**「Credential remediation」** Affected organizations must audit and rotate all sensitive credentials, API keys, and database secrets stored in Railway environment variables to prevent unauthorized access across connected systems \[tool-2-2, tool-2-3\].

**「Community Discussion」** Affected developers reported instances of compromised secrets being actively used by unauthorized third parties, while others noted that following advice to rotate credentials caused service outages because Railway&\#x27;s paused deployment pipeline prevented applications from picking up the new keys.

<details><summary>References</summary>
<ul>
<li><a href="https://thecybersecguru.com/news/railway-security-breach-environment-variables/">Railway Security Breach: API Keys Exposed | The CyberSec Guru</a></li>
<li><a href="https://cybersecuritynews.com/railway-security-incident/">Railway Security Incident: Hackers May Have Accessed Customer ...</a></li>

</ul>
</details>

**Tags**: `#cybersecurity`, `#cloud infrastructure`, `#devops`, `#railway`

---

<a id="item-tech-news-11"></a>
### [Carbon-X Open 14.8B Model Jointly Trains on DNA and Text](https://www.reddit.com/r/MachineLearning/comments/1xchayq/carbonx_is_an_open_148b_model_trained_jointly_on/) ⭐️ 7.0/10

Carbon-X is an open-source, 14.8-billion-parameter decoder-only model released under the Apache 2.0 license that accepts raw DNA sequences in standard chat prompts and outputs analysis in English. Built with a unified token stream using 6-mer tokens and mid-trained on 302 billion tokens, it runs in bfloat16 on a single 80 GB GPU. Hugging Face reports that the model achieves a 66.7% average score across five DNA benchmarks without reasoning tokens enabled, compared to 67.5% for GPT-6.1 Sol. The release is not clinically validated, and the model card notes that exact sequence operations still require deterministic code.

reddit · r/MachineLearning · /u/jatingargiitk · Oct 22, 12:32

**「Background」** Interpreting genomic sequences with language models typically requires specialized pipelines or separate encoders to bridge raw nucleotide data with natural language. Prior to Carbon-X, Hugging Face Biology Research focused its Carbon efforts on domain-specific systems like Carbon-A, which was developed for large-scale genome annotation across thousands of species.

**「Impact」** Computational biology teams can execute conversational genomic sequence analysis locally on a single enterprise GPU, allowing privacy-sensitive genetic data to be processed on-premises without relying on closed proprietary APIs.

<details><summary>References</summary>
<ul>
<li><a href="https://huggingface.co/blog/HuggingFaceBio/carbon-annotator-genbank-genome-annotation">A Blog post by Hugging Face Biology Research on Hugging Face</a></li>

</ul>
</details>

**Tags**: `#machine learning`, `#computational biology`, `#foundation models`, `#open source`

---

<a id="item-tech-news-12"></a>
### [Australian Court Orders Apple to Allow Alternative iOS App Stores by 2027](https://9to5mac.com/2026/10/21/apple-must-open-iphone-to-alternative-app-stores-in-australia-after-epic-games-ruling/) ⭐️ 7.0/10

The Federal Court of Australia has ruled in Epic Games&\#x27; antitrust lawsuit that Apple must permit third-party app stores, direct web downloads, and alternative payment methods on iPhones in Australia starting March 1, 2027. Under the decision, which found Apple&\#x27;s iOS app distribution and payment restrictions violated Australian competition law, Fortnite will also return immediately to the regional App Store. Apple has stated that it will appeal the ruling and seek a stay of enforcement pending that appeal.

telegram · zaihuapd · Oct 22, 06:54

**「Background」** The ruling follows a multi-year antitrust battle brought by Epic Games challenging Apple&\#x27;s control over iOS app distribution and mandatory in-app payment systems \[tool-1-2\]. The case led the Federal Court of Australia to determine that Apple engaged in anti-competitive conduct in violation of national competition laws \[tool-1-2, tool-1-3\].

**「Impact」** Unless Apple secures a stay pending appeal, Australian iOS developers will be able to distribute apps through rival marketplaces or direct web sideloading and adopt external payment links by March 1, 2027, while Epic Games receives immediate clearance to bring Fortnite back to the Australian App Store.

<details><summary>References</summary>
<ul>
<li><a href="https://9to5mac.com/2026/10/21/apple-must-open-iphone-to-alternative-app-stores-in-australia-after-epic-games-ruling/">An Australian federal judge rules Apple must let Australian ...</a></li>
<li><a href="https://www.australiancompetitionlaw.info/cases/database/2025-epic-apple">Epic Games, Inc v Apple Inc (FCA) - Australian Competition Law</a></li>
<li><a href="https://www.macsurfer.com/headlines/australia-court-orders-apple-open-app-store-rivals">Australia Court Orders Apple to Open App Store to Rivals</a></li>
<li><a href="https://www.gsmarena.com/apple_must_allow_thirdparty_app_stores_on_the_iphone_the_federal_court_of_australia_rules-news-75165.php">Apple must allow third-party app stores on the iPhone, the ...</a></li>

</ul>
</details>

**Tags**: `#Apple`, `#iOS`, `#Antitrust`, `#App Store`, `#Mobile Development`

---

<a id="item-tech-news-13"></a>
### [Smart TVs Transmit Viewing Data and Identifiers Despite Disabling ACR](https://watchingthewatchers.github.io/watchingthewatchers/index.html) ⭐️ 7.0/10

A study evaluating 12 smart TV models from 10 manufacturers across 5,943 controlled experiments found that several platforms continue exfiltrating viewing telemetry even after users turn off Automatic Content Recognition \(ACR\). Researchers observed that VIDAA OS transmits audio fingerprints and non-resettable device identifiers in plaintext over MQTT. Additionally, Vizio&\#x27;s WatchFree+ service embeds program names directly into unencrypted DNS queries with no user-facing option to disable the behavior.

telegram · zaihuapd · Oct 22, 09:50

**「Background」** Automatic Content Recognition \(ACR\) technology samples on-screen video frames or audio signatures to identify what viewers watch in real time, primarily to power targeted advertising and audience measurement. Smart TV manufacturers routinely include settings menus that nominally allow consumers to disable this tracking.

**「Impact」** Because built-in privacy settings fail to halt these transmissions, users cannot rely on system toggles alone and must implement network-level controls, such as DNS sinkholing or blocking unencrypted MQTT traffic, to prevent passive tracking of their viewing habits.

**Tags**: `#Smart TV`, `#Privacy`, `#IoT Security`, `#Network Protocols`, `#Embedded Systems`

---

<a id="item-tech-news-14"></a>
### [miHoYo and Tsinghua Open-Source GameScaling Game Action Models](https://arxiv.org/abs/2610.28698v1) ⭐️ 7.0/10

miHoYo&\#x27;s Honkai AI team and Tsinghua University have released GameScaling, a family of game-playing models continually pre-trained on Qwen3.5 vision-language backbones to predict keyboard and mouse actions over 200-millisecond windows. Across 120 experimental training setups ranging from 0.8B to 27B parameters, the authors found that scaling data volume directly improved in-domain gameplay performance, while data diversity facilitated transfer primarily to visually and mechanically similar titles rather than substantially different game worlds. Eight inference checkpoints and an inference client have been released under the Apache-2.0 license on GitHub, though the underlying training code is not included.

telegram · zaihuapd · Oct 22, 11:32

**「Background」** Developing real-time game-playing agents requires mapping visual screen frames and input history into precise, low-latency keyboard and mouse control sequences. While vision-language foundation models provide general visual reasoning, adapting them to interactive gameplay requires specialized pre-training on behavioral traces to determine how parameter scaling and dataset diversity impact control generalization across different game environments.

**「Impact」** Game AI developers and agent researchers can run the pre-trained checkpoints locally to evaluate real-time screen-to-action gameplay inference, but adapting or reproducing the models on novel genres remains limited due to the omission of the training code.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/THUSI-Lab/GameScaling">GitHub - THUSI-Lab/ GameScaling : Scaling in Games: Continued...</a></li>

</ul>
</details>

**Tags**: `#game-ai`, `#vision-language-models`, `#ai-agents`, `#open-source-models`, `#reinforcement-learning`

---

<a id="item-tech-news-15"></a>
### [Oracle Issues Alert for Critical Java SE and GraalVM JSSE Vulnerability](https://www.oracle.com/security-alerts/alert-cve-2026-91403.html) ⭐️ 7.0/10

Oracle has issued a security alert for CVE-2026-91403, a critical vulnerability rated CVSS 9.1 in the Java Secure Socket Extension \(JSSE\) component of Java SE and GraalVM. The flaw allows unauthenticated attackers to execute remote exploits over the network, threatening data confidentiality and integrity. The issue affects Java SE versions 8u511, 11.0.33, 17.0.21, 21.0.13, 25.0.5, and 27.0.1, as well as multiple GraalVM releases, and Oracle has released security patches resolving the defect.

telegram · zaihuapd · Oct 22, 12:30

**「Background」** The Java Secure Socket Extension \(JSSE\) is the core framework that implements Transport Layer Security \(TLS\) and secure network communications across Java runtimes \[tool-1-1\]. Oracle typically bundles security fixes into its scheduled quarterly Critical Patch Update releases, issuing standalone Security Alerts only for severe vulnerabilities that warrant immediate out-of-band remediation \[tool-1-3\].

**「Impact」** Administrators and developers operating affected Java SE or GraalVM environments must apply Oracle&\#x27;s latest security updates immediately to mitigate the risk of unauthenticated remote attacks.

<details><summary>References</summary>
<ul>
<li><a href="https://www.oracle.com/security-alerts/alert-cve-2026-91403.html">Oracle Security Alert Advisory - CVE - 2026 - 91403</a></li>
<li><a href="https://blogs.oracle.com/security/security-alert-cve-2026-91403-released">Security Alert CVE - 2026 - 91403 Released | security</a></li>

</ul>
</details>

**Tags**: `#Java`, `#Security Advisory`, `#Vulnerability`, `#GraalVM`, `#DevOps`

---