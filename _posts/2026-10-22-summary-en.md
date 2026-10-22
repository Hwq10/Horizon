---
layout: default
title: "Horizon Summary: 2026-10-22 (EN)"
date: 2026-10-22
lang: en
---

> From 37 items, 14 important content pieces were selected

---

**Technology News**
1. [David Harvey Analyzes Proposed $o\(n \\log n\)$ Integer Multiplication Algorithm](#item-tech-news-1) ⭐️ 8.0/10
2. [PHP Foundation Releases Urgent 8.x Updates Following Remote Code Execution Leak](#item-tech-news-2) ⭐️ 8.0/10
3. [SemiAnalysis Details Huawei Ascend 950PR Benchmarks and DeepSeek Integration](#item-tech-news-3) ⭐️ 8.0/10
4. [Quad9 to Exit France Over Legal Domain-Blocking Mandates](#item-tech-news-4) ⭐️ 7.0/10
5. [eMudhra to Exit Global SSL/TLS Certificate Business](#item-tech-news-5) ⭐️ 7.0/10
6. [Earstrip Benchmarks Polygon Triangulation for 3.7M Map Polygons in 489 Milliseconds](#item-tech-news-6) ⭐️ 7.0/10
7. [Railway Discloses Security Incident and Pauses Deployments](#item-tech-news-7) ⭐️ 7.0/10
8. [Amazon Reports Pre-Disclosure Exploitation of PHP2Shell Vulnerability](#item-tech-news-8) ⭐️ 7.0/10
9. [Carbon-X Releases Open-Source 14.8B DNA-and-Text Model under Apache 2.0](#item-tech-news-9) ⭐️ 7.0/10
10. [Claude API 2026-10-21 Removes Sampling Parameters and Updates Auth Headers](#item-tech-news-10) ⭐️ 7.0/10
11. [Australian Court Orders Apple to Allow Third-Party App Stores and Sideloading](#item-tech-news-11) ⭐️ 7.0/10
12. [Study Finds Smart TVs Transmit Viewing Data Even After Disabling ACR](#item-tech-news-12) ⭐️ 7.0/10
13. [miHoYo and Tsinghua Open-Source GameScaling Game Control Models](#item-tech-news-13) ⭐️ 7.0/10
14. [Oracle Patches Critical CVSS 9.1 JSSE Flaw Across Java SE and GraalVM](#item-tech-news-14) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [David Harvey Analyzes Proposed $o\(n \\log n\)$ Integer Multiplication Algorithm](https://web.maths.unsw.edu.au/~davidharvey/research/subnlogn.pdf) ⭐️ 8.0/10

Mathematician David Harvey published an analysis examining a newly proposed integer multiplication algorithm that claims an $o\(n \\log n\)$ runtime bound. The paper reviews three closely related manuscripts to assess whether strictly sub-$n \\log n$ complexity has been achieved for integer arithmetic. Harvey details the structure of the proposed technique while evaluating the mathematical soundness and limits of the underlying arguments.

hackernews · craigcitro · Oct 22, 02:30 · [Discussion](https://news.ycombinator.com/item?id=50190455)

**「Historical multiplication bounds」** In 2019, mathematicians David Harvey and Joris van der Hoeven established an $O\(n \\log n\)$ time complexity algorithm for multiplying two $n$-bit integers, resolving a long-standing conjecture regarding the operation&\#x27;s asymptotic limit. Prior to recent proposals claiming an $o\(n \\log n\)$ running time, $O\(n \\log n\)$ was widely hypothesized to be the optimal lower bound for integer multiplication.

**「Lean formalization and exposition hurdles」** Commenters highlighted active formal verification efforts, with contributors reporting a completed implementation of the bounds in Lean on Mathlib&\#x27;s Turing machine model. Readers also debated the author&\#x27;s candid remarks regarding the source manuscripts&\#x27; dense exposition and his use of an AI model to assist in parsing the proofs.

<details><summary>References</summary>
<ul>
<li><a href="https://fr.wikipedia.org/wiki/Algorithme_de_multiplication_d&#x27;entiers">Algorithme de multiplication d&#x27;entiers — Wikipédia</a></li>
<li><a href="https://salivity.github.io/binary/article/harvey-and-hoeven-o-n-log-n-integer-multiplication">Harvey and Hoeven O (n log n) Integer Multiplication - binary</a></li>

</ul>
</details>

**Tags**: `#theoretical computer science`, `#algorithms`, `#computational complexity`, `#formal verification`

---

<a id="item-tech-news-2"></a>
### [PHP Foundation Releases Urgent 8.x Updates Following Remote Code Execution Leak](https://simonwillison.net/2026/Oct/21/php-security-release/) ⭐️ 8.0/10

The PHP Foundation published urgent security releases across the entire PHP 8.x series to address two remote code execution vulnerabilities carrying a CVSS score of 9.2. The release schedule was accelerated to October 21, 2026, after CVE identifiers leaked and security firm Calif mistakenly posted a demonstration video that spurred external proof-of-concept development. Originally uncovered by Wiz Research, the flaws enable unauthenticated remote code execution and were confirmed to affect widespread applications including WordPress and Drupal.

rss · Simon Willison · Oct 21, 18:41

**「Disclosure Timeline and Leak」** Wiz Research discovered the vulnerabilities—collectively tracked as PHP2Shell—in August 2026, confirming unauthenticated remote code execution against platforms including WordPress and Drupal before reporting them to PHP maintainers. While the coordinated security release was originally planned for October 22, leaked CVE identifiers and an accidental proof-of-concept demonstration accelerated exploit development and prompted the team to move the release forward.

**「Impact」** System administrators and developers managing PHP 8.x deployments must upgrade immediately, as functional exploitation proof-of-concepts are circulating publicly.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/PHP2Shell">PHP 2Shell - Wikipedia</a></li>

</ul>
</details>

**Tags**: `#php`, `#security`, `#vulnerability`, `#remote code execution`, `#open source`

---

<a id="item-tech-news-3"></a>
### [SemiAnalysis Details Huawei Ascend 950PR Benchmarks and DeepSeek Integration](https://newsletter.semianalysis.com/p/huawei-deepseek) ⭐️ 8.0/10

SemiAnalysis published a technical analysis examining the collaboration between Huawei and DeepSeek. The report features microbenchmarks evaluating Huawei&\#x27;s Ascend 950PR hardware alongside an architectural breakdown of DeepSeek&\#x27;s DSv4.1 Flash. It also assesses DeepSeek&\#x27;s software platform support and optimizations for Ascend accelerators.

rss · Semianalysis · Oct 21, 17:34

**「Ascend AI Ecosystem Context」** DeepSeek has actively optimized its model architectures for Huawei&\#x27;s Ascend accelerator platform, adapting core CUDA operators to Huawei&\#x27;s CANN framework to support native inference. Deploying frontier models on Ascend silicon has required extensive custom kernel engineering and specialized compiler tooling to achieve viable throughput outside the established CUDA ecosystem.

<details><summary>References</summary>
<ul>
<li><a href="https://dev.to/lanternproton/deepseek-v4-on-huaweis-ascend-950-a-real-stress-test-for-chinas-ai-chip-ecosystem-ook">DeepSeek V4 on Huawei&#x27;s Ascend 950: A Real Stress Test for ...</a></li>

</ul>
</details>

**Tags**: `#AI Hardware`, `#DeepSeek`, `#Huawei Ascend`, `#Machine Learning Systems`, `#Semiconductors`

---

<a id="item-tech-news-4"></a>
### [Quad9 to Exit France Over Legal Domain-Blocking Mandates](https://quad9.net/news/blog/au-revoir-france/) ⭐️ 7.0/10

Privacy-focused recursive DNS service Quad9 announced its decision to exit France following legal disputes and court-ordered domain-blocking mandates. The provider&\#x27;s withdrawal follows European copyright injunctions compelling public DNS resolvers to restrict access to targeted websites. Rather than maintaining regional blocking regimes or risking penalties for circumvention, Quad9 is ceasing operations within the jurisdiction.

hackernews · farrokhi · Oct 22, 14:32 · [Discussion](https://news.ycombinator.com/item?id=50195959)

**「Background」** French courts have increasingly issued web-blocking injunctions compelling recursive DNS resolvers to filter piracy-related domains, leading Cisco&\#x27;s OpenDNS to pull its service from France in 2024. The latest dispute escalated after broadcaster beIN Sports obtained an order requiring resolvers, including Quad9, to block unauthorized sports streaming domains under threat of daily fines reaching up to €580,000.

**「Impact」** Users and network administrators in France relying on Quad9 for recursive DNS resolution must migrate to alternative providers or accept DNS queries being routed outside French jurisdiction, following the resolver&\#x27;s withdrawal to avoid enforcing local judicial web-blocking orders.

**「Community Discussion」** Commenters criticized court rulings that hold DNS resolvers liable when users bypass geoIP-based blocks via VPNs, comparing the situation to Cisco&\#x27;s prior exit from the French market under similar anti-piracy injunctions. Others questioned how Quad9 plans to reliably restrict access for all French users given the technical limitations of IP geolocation.

<details><summary>References</summary>
<ul>
<li><a href="https://frenchbreaches.com/blog/jusqua-580-000-par-jour-pourquoi-le-service-dns-quad9-menace-de-quitter-la-france">Jusqu’à 580 000 € par jour : pourquoi le service DNS Quad9 ...</a></li>
<li><a href="https://www.justgeek.fr/quad9-blocages-anti-piratage-france-159240/">Après OpenDNS, Quad9 menace à son tour de quitter la France</a></li>
<li><a href="https://www.aubedigitale.com/quad9-envisage-de-quitter-la-france-en-raison-dune-decision-de-blocage-de-son-site-web/">Quad9 envisage de quitter la France en raison d&#x27;une décision ...</a></li>
<li><a href="https://completemusicupdate.com/quad9-vows-to-fight-absurd-web-block-injunction-in-france/">Quad 9 vows to fight “absurd” web- block injunction in France</a></li>

</ul>
</details>

**Tags**: `#dns`, `#networking`, `#internet-governance`, `#legal`, `#infrastructure`

---

<a id="item-tech-news-5"></a>
### [eMudhra to Exit Global SSL/TLS Certificate Business](https://emudhra.com/en/press-release/emudhra-to-exit-global-ssl-tls-certificate-business) ⭐️ 7.0/10

Certificate authority eMudhra announced it will exit the global public SSL/TLS certificate business following intense scrutiny and formal inquiries from major browser root programs. The decision comes after root store maintainers raised critical questions regarding the company&\#x27;s cryptographic implementations and operational security practices. In its announcement, eMudhra stated that its global SSL/TLS operations run separately from the rest of its enterprise digital signature and identity business lines.

hackernews · bo0tzz · Oct 22, 13:33 · [Discussion](https://news.ycombinator.com/item?id=50195110)

**「Background」** Days before the announcement, major browser root store operators including Google, Mozilla, Apple, and Microsoft blocked eight of eMudhra&\#x27;s intermediate certificate authority certificates after discovering critical key generation flaws. Investigations and security analyses revealed that intermediate certificates relied on compromised, trivially weak private keys, prompting intense public scrutiny and formal root program inquiries into the provider&\#x27;s operational practices.

**「Community Discussion」** Commenters criticized eMudhra for attributing the fallout to disproportionate social media scrutiny rather than addressing the underlying cryptographic failures highlighted in Mozilla and Chrome root store discussions. Observers also pointed to real-world fallout from the incident, citing an immediate drop in eMudhra&\#x27;s share price and intense questioning from browser security teams.

<details><summary>References</summary>
<ul>
<li><a href="https://www.moneycontrol.com/technology/emudhra-to-exit-global-website-security-certificate-business-after-key-generation-flaw-article-14057821.html">eMudhra to exit global website security certificate business after...</a></li>
<li><a href="https://cointelegraph.com/news/tech-giants-rush-to-block-flawed-emudhra-certs-that-could-enable-fake-sites">Tech Giants Rush to Block Flawed eMudhra Certificates</a></li>
<li><a href="https://thehackernews.com/2026/10/eight-emudhra-ca-keys-compromised.html">Eight eMudhra CA Keys Compromised, Triggering Emergency Fixes...</a></li>
<li><a href="https://www.theregister.com/security/2026/10/20/indian-certification-authority-emudhras-private-keys-compromised-one-of-them-was-the-number-4/5304312">Indian certification authority eMudhra ’s private keys compromised...</a></li>

</ul>
</details>

**Tags**: `#web-pki`, `#ssl-tls`, `#cybersecurity`, `#certificate-authorities`, `#infrastructure`

---

<a id="item-tech-news-6"></a>
### [Earstrip Benchmarks Polygon Triangulation for 3.7M Map Polygons in 489 Milliseconds](https://globus.software/blog/2026/10/16/cutting-map-polygons/) ⭐️ 7.0/10

A technical benchmark published by Globus Software introduces an optimized polygon triangulation approach, referred to in discussions as Earstrip, that processes 3.7 million map polygons in 489 milliseconds. The algorithm aims to dramatically outpace standard polygon cutting libraries like Earcut when handling large-scale GIS and graphics geometry. Detailed benchmarks and dataset tests were released to demonstrate its throughput advantages over existing triangulators.

hackernews · molind · Oct 22, 09:31 · [Discussion](https://news.ycombinator.com/item?id=50193170)

**「Polygon Triangulation and Earcut」** Polygon triangulation is essential in web mapping and computer graphics to convert arbitrary vector shapes into triangles that GPUs can render. Mapbox&\#x27;s Earcut library has widely served as the standard solution for real-time web rendering by prioritizing execution speed and compact bundle size over mesh quality.

**「Community Discussion」** Earcut author Vladimir Agafonkin noted that Earcut deliberately accepts performance trade-offs to preserve a 4.1 KB minified bundle size for web mapping applications like Mapbox GL JS, while inquiring about Earstrip&\#x27;s WebAssembly footprint. Commenters also highlighted potential graphics drawbacks, cautioning that generating long, thin triangles can degrade GPU rasterization efficiency despite faster initial triangulation times.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/mapbox/earcut">GitHub - mapbox/ earcut : The fastest and smallest JavaScript polygon ...</a></li>

</ul>
</details>

**Tags**: `#computational-geometry`, `#algorithms`, `#gis`, `#performance-optimization`, `#graphics-programming`

---

<a id="item-tech-news-7"></a>
### [Railway Discloses Security Incident and Pauses Deployments](https://blog.railway.com/p/security-disclosure-wednesday-october-21st) ⭐️ 7.0/10

Cloud infrastructure platform Railway published a security disclosure regarding an incident that prompted the team to pause deployments and advise customers to rotate sensitive credentials. Because builds and redeployments were temporarily disabled during the response, users attempting immediate credential rotations could not update running services with the new values.

hackernews · passenger · Oct 21, 21:58 · [Discussion](https://news.ycombinator.com/item?id=50188228)

**「Platform Secret Management」** Cloud hosting platforms like Railway allow developers to deploy applications using centralized environment variable stores to manage sensitive runtime credentials such as API keys and database connection strings \[tool-1-1\]. Because these variables provide direct access to external infrastructure, securing their encrypted storage and decryption workflows is essential to preventing downstream service compromise across hosted applications.

**「Impact」** Affected customers must rotate sensitive environment variables stored on the platform, including database credentials, registry tokens, and third-party API keys targeting AI inference providers, while managing downtime caused by Railway&\#x27;s temporarily paused deployments.

**「Community Discussion」** Users reported that immediately revoking and rotating API keys inadvertently took services offline because Railway&\#x27;s paused build pipeline prevented apps from deploying with the updated credentials. Several developers in community channels also indicated that unauthorized third parties had already begun using exposed environment variables stored across affected Railway projects.

<details><summary>References</summary>
<ul>
<li><a href="https://blog.railway.com/p/security-disclosure-wednesday-october-21st">Security Disclosure: Wednesday October 21st | Railway Blog</a></li>
<li><a href="https://blog.railway.com/p/security-disclosure-wednesday-october-21st">Security Disclosure : Wednesday October 21st | Railway Blog</a></li>

</ul>
</details>

**Tags**: `#security`, `#cloud infrastructure`, `#railway`, `#devops`

---

<a id="item-tech-news-8"></a>
### [Amazon Reports Pre-Disclosure Exploitation of PHP2Shell Vulnerability](https://aws.amazon.com/blogs/security/amazon-threat-intelligence-identifies-php2shell-exploitation-prior-to-public-disclosure-in-madpot/) ⭐️ 7.0/10

Amazon Threat Intelligence reported observing in-the-wild exploitation attempts targeting the PHP2Shell vulnerability on October 17 through its MadPot honeypot infrastructure, prior to the flaw&\#x27;s official public disclosure. The findings indicate that threat actors were actively probing or attempting to leverage the vulnerability before coordinated advisories were publicly released.

hackernews · cubefox · Oct 22, 11:50 · [Discussion](https://news.ycombinator.com/item?id=50194070)

**「The PHP2Shell Vulnerabilities」** PHP2Shell refers to a pair of remote code execution vulnerabilities \(CVE-2026-109618 and CVE-2026-109619\) affecting PHP versions 5.4 through 8.5 that were publicly announced on October 20, 2026. Amazon tracks live attack patterns and scanning activity across internet-facing infrastructure using MadPot, its threat detection sensor network.

**「Incident response timeline」** Because active exploitation occurred prior to the October 20 public disclosure \[tool-2-1\], security teams managing PHP infrastructure must extend forensic log audits and compromise assessments back to at least October 17, 2026.

**「Community Discussion」** Commenters questioned whether observed telemetry reflects functional remote code execution or indiscriminate vulnerability scanning, while noting broader friction surrounding embargo timelines between vendors and PHP maintainers.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/PHP2Shell">PHP 2 Shell - Wikipedia</a></li>
<li><a href="https://aws.amazon.com/blogs/security/amazon-threat-intelligence-identifies-php2shell-exploitation-prior-to-public-disclosure-in-madpot/">Amazon Threat Intelligence identifies PHP 2 Shell exploitation prior to...</a></li>
<li><a href="https://www.cnbc.com/2026/10/22/php-google-openai-and-amazon-cyber.html">PHP web security flaws spark global alarm: Google, OpenAI, Amazon</a></li>
<li><a href="https://en.wikipedia.org/wiki/PHP2Shell">PHP 2 Shell - Wikipedia</a></li>

</ul>
</details>

**Tags**: `#security`, `#php`, `#vulnerability`, `#threat-intelligence`

---

<a id="item-tech-news-9"></a>
### [Carbon-X Releases Open-Source 14.8B DNA-and-Text Model under Apache 2.0](https://www.reddit.com/r/MachineLearning/comments/1xchayq/carbonx_is_an_open_148b_model_trained_jointly_on/) ⭐️ 7.0/10

Hugging Face Bio has released Carbon-X, an Apache 2.0-licensed 14.8-billion-parameter decoder-only model mid-trained on 302 billion tokens using a unified token stream for text and DNA 6-mers. The model runs in bfloat16 on a single 80 GB GPU, enabling users to submit raw DNA sequences in standard chat interfaces and receive English responses. Hugging Face reports a 66.7% average across five DNA benchmarks with thinking disabled, closely trailing GPT-6.1 Sol&\#x27;s 67.5%. The model has not been clinically validated, and its documentation specifies that exact sequence operations must still be handled by dedicated code.

reddit · r/MachineLearning · /u/jatingargiitk · Oct 22, 12:32

**「Background」** HuggingFaceBio previously released Carbon, an open-source DNA foundation model available in 500M, 3B, and 8B parameter variants. Carbon-X builds on this genomic modeling effort by integrating 6-mer DNA representations directly into a unified conversational language model.

**「Impact」** By fitting on a single 80 GB accelerator, Carbon-X allows bioinformatics teams to run conversational genomic sequence analysis locally instead of transmitting sensitive genetic data to proprietary cloud APIs.

<details><summary>References</summary>
<ul>
<li><a href="https://huggingface.co/spaces/HuggingFaceBio/carbon-demo">Carbon - a Hugging Face Space by HuggingFaceBio</a></li>

</ul>
</details>

**Tags**: `#computational biology`, `#genomics`, `#large language models`, `#open source ai`

---

<a id="item-tech-news-10"></a>
### [Claude API 2026-10-21 Removes Sampling Parameters and Updates Auth Headers](https://x.com/ClaudeDevs/status/2113013247209021918) ⭐️ 7.0/10

Anthropic released Claude API version 2026-10-21, marking its first formal API version update since 2023. The new release removes the temperature, top\_p, and top\_k sampling parameters, returning an HTTP 400 error if any of them are passed in a request. Official SDKs and the ant CLI now default to the new version and switch to standard Authorization: Bearer headers, while the older 2023-06-01 version remains supported.

telegram · zaihuapd · Oct 22, 03:54

**「Background」** Anthropic&\#x27;s Claude API had operated under the 2023-06-01 baseline version since 2023, requiring incoming requests to specify an anthropic-version header. Under that original version, standard sampling controls including temperature, top\_p, and top\_k were supported parameters for tuning model generation.

**「Impact」** Developers updating to the latest SDKs or the ant CLI must strip legacy sampling parameters from their request payloads to prevent HTTP 400 errors, or explicitly pin their integration to API version 2023-06-01.

<details><summary>References</summary>
<ul>
<li><a href="https://platform.claude.com/docs/en/api/migration-2026-10-21">Migrating to API version 2026-10-21 - Claude Platform Docs</a></li>
<li><a href="https://platform.claude.com/docs/en/api/versioning">Versions - Claude Platform Docs - Anthropic</a></li>

</ul>
</details>

**Tags**: `#Anthropic`, `#Claude API`, `#LLM`, `#API Design`, `#Software Engineering`

---

<a id="item-tech-news-11"></a>
### [Australian Court Orders Apple to Allow Third-Party App Stores and Sideloading](https://9to5mac.com/2026/10/21/apple-must-open-iphone-to-alternative-app-stores-in-australia-after-epic-games-ruling/) ⭐️ 7.0/10

Australia&\#x27;s Federal Court has ruled that Apple must allow third-party app marketplaces, direct web distribution, and alternative in-app payment systems on iOS in Australia starting March 1, 2027. Stemming from an antitrust lawsuit brought by Epic Games, the court determined that Apple abused its market power and ordered the immediate reinstatement of Fortnite to the Australian App Store. Apple announced that it will appeal the decision and apply for a stay of execution pending the appeal.

telegram · zaihuapd · Oct 22, 06:54

**「Background」** The ruling follows a multi-year legal battle initiated by Epic Games over platform fees and exclusivity restrictions. In August 2025, Australia&\#x27;s Federal Court determined that Apple had engaged in anticompetitive conduct across iOS app distribution and payment systems.

**「Impact」** Australian iOS developers will be able to deploy their own web distribution channels, rival marketplaces, and third-party payment systems starting March 1, 2027, while Epic Games secures an immediate reinstatement of Fortnite on Australia&\#x27;s App Store unless Apple wins a stay pending appeal.

<details><summary>References</summary>
<ul>
<li><a href="https://au.news.yahoo.com/aust-court-orders-fortnite-back-083941972.html">Aust court orders Fortnite back into app store - Yahoo News</a></li>
<li><a href="https://9to5mac.com/2026/10/21/apple-must-open-iphone-to-alternative-app-stores-in-australia-after-epic-games-ruling/">An Australian federal judge rules Apple must let Australian ...</a></li>
<li><a href="https://www.macrumors.com/2026/10/22/rival-app-stores-in-australia-ordered/">Apple Ordered to Open iPhone to Rival App Stores in Australia</a></li>

</ul>
</details>

**Tags**: `#apple`, `#app-store`, `#epic-games`, `#antitrust`, `#mobile-development`

---

<a id="item-tech-news-12"></a>
### [Study Finds Smart TVs Transmit Viewing Data Even After Disabling ACR](https://watchingthewatchers.github.io/watchingthewatchers/index.html) ⭐️ 7.0/10

A study evaluating 12 smart TVs from 10 vendors across 5,943 controlled tests found that multiple models continue transmitting viewing-related traffic after users disable Automatic Content Recognition \(ACR\). Researchers observed that VIDAA OS transmits audio fingerprints and non-resettable device identifiers in plaintext over MQTT despite ACR being disabled. Additionally, Vizio&\#x27;s WatchFree+ service exposes program titles through unencrypted domain name lookups without providing a mechanism for users to opt out.

telegram · zaihuapd · Oct 22, 09:50

**「Background」** Automatic Content Recognition \(ACR\) is a technology embedded in smart TVs that samples audio or visual signals on the screen to identify what viewers are watching, primarily for targeted advertising and audience analytics \[tool-1-1, tool-1-2\]. Manufacturers commonly provide opt-out toggles in system settings that are supposed to disable this content tracking \[tool-1-2\].

**「Impact」** Users cannot rely solely on built-in privacy toggles to prevent viewing telemetry on affected smart TVs, making network-level filtering or complete disconnection from the local network the only reliable mitigations.

<details><summary>References</summary>
<ul>
<li><a href="https://www.ucdavis.edu/news/your-smart-tv-watching-what-you-watch">Your Smart TV is Watching What You Watch - UC Davis</a></li>
<li><a href="https://www.pcmag.com/explainers/is-your-tv-spying-on-you-hidden-setting-watching-everything-how-to-stop">Is Your TV Spying on You? The Hidden Setting Watching ... - PCMag</a></li>

</ul>
</details>

**Tags**: `#privacy`, `#iot security`, `#smart tvs`, `#network security`

---

<a id="item-tech-news-13"></a>
### [miHoYo and Tsinghua Open-Source GameScaling Game Control Models](https://arxiv.org/abs/2610.28698v1) ⭐️ 7.0/10

miHoYo&\#x27;s Honkai AI team and Tsinghua University have open-sourced GameScaling, a family of game-control vision-language models based on Qwen3.5 ranging from 0.8B to 27B parameters. The models are continued-pretrained to output keyboard and mouse actions for the subsequent 200 milliseconds, evaluated across 120 training configurations examining data volume, dataset diversity, and model scale. Eight model checkpoints and an inference client have been released under the Apache-2.0 license, though the project does not include training code.

telegram · zaihuapd · Oct 22, 11:32

**「Game-Playing Agent Control」** Developing autonomous game-playing agents requires translating real-time screen frames directly into continuous, low-latency keyboard and mouse commands. Adapting multimodal foundation models to these environments typically involves continued pre-training on human gameplay traces to output fine-grained action sequences over short temporal intervals \[tool-1-1\].

**「Impact」** Researchers and developers can directly run and evaluate pre-trained real-time game agents across multiple model scales, but teams seeking to adapt or retrain the system on custom games must implement their own training pipelines because training code was withheld.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/THUSI-Lab/GameScaling">GitHub - THUSI-Lab/GameScaling: Scaling in Games: Continued ...</a></li>

</ul>
</details>

**Tags**: `#AI Agents`, `#Vision-Language Models`, `#Game AI`, `#Open Source AI`

---

<a id="item-tech-news-14"></a>
### [Oracle Patches Critical CVSS 9.1 JSSE Flaw Across Java SE and GraalVM](https://www.oracle.com/security-alerts/alert-cve-2026-91403.html) ⭐️ 7.0/10

Oracle has released a security alert and patches addressing CVE-2026-91403, a critical vulnerability rated CVSS 9.1 in the Java Secure Socket Extension \(JSSE\) component of Java SE and GraalVM. The flaw allows unauthenticated attackers to execute remote attacks over the network, threatening the confidentiality and integrity of affected systems. Impacted releases include Java SE versions 8u511, 11.0.33, 17.0.21, 21.0.13, 25.0.5, and 27.0.1, as well as multiple GraalVM distributions.

telegram · zaihuapd · Oct 22, 12:30

**「Background」** The Java Secure Socket Extension \(JSSE\) provides the underlying framework and protocols for secure TLS and SSL network communications across Java runtimes. Oracle issues standalone Security Alerts outside of its regular quarterly update schedule when high-severity flaws require immediate remediation across supported deployments.

**「Impact」** Administrators and developers operating affected Java SE or GraalVM environments must update to the latest patched releases immediately to prevent unauthenticated network-based compromises.

<details><summary>References</summary>
<ul>
<li><a href="https://blogs.oracle.com/security/security-alert-cve-2026-91403-released">Security Alert CVE-2026-91403 Released - Oracle Blogs</a></li>

</ul>
</details>

**Tags**: `#Java`, `#Cybersecurity`, `#Vulnerability`, `#Oracle`

---