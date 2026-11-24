### Hey, I'm Alben

[English](#hey-im-alben) · [中文](#你好我是-alben)

[![GitHub followers](https://img.shields.io/github/followers/XiaoBinGan?style=flat&color=gold&label=followers)](https://github.com/XiaoBinGan)
[![CSDN](https://img.shields.io/badge/CSDN-%E5%90%B4%E4%BD%B3%E6%B5%A9%20Alben-FC5531?style=flat&logo=csdn)](https://blog.csdn.net/weixin_43712047)
[![Juejin](https://img.shields.io/badge/Juejin-%E5%90%B4%E4%BD%B3%E6%B5%A9%20Alben-1E80FF?style=flat&logo=juejin)](https://juejin.cn/user/2696441245481975)
![Jianshu: 吴佳浩](https://img.shields.io/badge/%E7%AE%80%E4%B9%A6-%E5%90%B4%E4%BD%B3%E6%B5%A9-EA6F5A?style=flat)
![WeChat: 全栈架构师笔记](https://img.shields.io/badge/WeChat-%E5%85%A8%E6%A0%88%E6%9E%B6%E6%9E%84%E5%B8%88%E7%AC%94%E8%AE%B0-07C160?style=flat&logo=wechat)

I work in AI — an AI industry practitioner with twelve AI-related patents, ten of them published
invention patents. I write long-form technical notes in Chinese about large-model deployment, AI
agents, AI infra and inference engines, and about what I find when I take an agent product apart.

Most recently I've been working on local inference on consumer hardware: measuring it, deploying it,
and fixing the failures that only show up on a real machine. I wrote community benchmark reports for
[Strata](https://github.com/Niko1221/Strata) on an RTX 5090 — the same card shared with other
workloads versus held exclusively — and opened the fixes those measurements turned up.

Right now my commits concentrate in two places: [rust-anything](https://github.com/erkamyaman/rust-anything),
where I sit second on the commit graph of 44 contributors behind the maintainer, and
[REA](https://github.com/morluto/rea), the agentic reverse-engineering toolkit, where I am 9th of 440.

My personal research is in local inference, agent tooling and benchmarking. If you would like to
collaborate on any of that, reach me on WeChat or open an issue on a repository I've worked in.
中文 / English both fine.

**Elsewhere** — CSDN: [吴佳浩 Alben](https://blog.csdn.net/weixin_43712047) ·
掘金 (Juejin): [吴佳浩 Alben](https://juejin.cn/user/2696441245481975) ·
简书 (Jianshu): 吴佳浩 · WeChat 公众号: 全栈架构师笔记

#### Building

- **[OpenLog](https://github.com/XiaoBinGan/OpenLog)** [![release](https://img.shields.io/badge/release-v1.3.0-2ea043?style=flat)](https://github.com/XiaoBinGan/OpenLog/releases) - **Self-hosted observability for GPU fleets, Docker hosts and Kubernetes clusters — one Node process, one port, no cloud, no telemetry, no account.** System and GPU metrics, live log streams, container management, SSH hosts, and a **Prometheus-compatible time-series store built in** (scrape any `/metrics`, a PromQL subset with `rate()` / `sum by()` / `topk()` / `histogram_quantile()`, expression alerting with `for:` + grouping / inhibition / silences, tiered retention, `remote write` intake — put Grafana on `/api/v1/*`, or point Prometheus at OpenLog's own `/metrics`). On top of that sits an agent that reads the data and then acts on it: it locates the problem, reads the code, edits, verifies, and every write needs a confirmation and lands in an audit trail. **Kubernetes** is read-only by default and talks straight to the kube-apiserver — nothing installed on the nodes, no `kubectl` needed, mTLS or ServiceAccount token, as many clusters as you paste in.
  - **HAMi vGPU: allocated vs actually used.** The annotation says what each pod was *given*; `nvidia-smi` over the SSH you already have says what it *used*, joined per GPU UUID — because HAMi v2 dropped the utilisation series. A device that cannot be measured says so instead of printing zeros.
  - **Scheduler policy, warning digest, opt-in writes.** `binpack` / `spread` and the overcommit ratio each carry their provenance (`configmap` / `scheduler-args` / `default`); `type=Warning` events collapse to one line per reason; scale, rolling restart and graceful pod delete stay **403** until `OPENLOG_K8S_WRITE=1`, and each accepted one is audited with the previous replica count.
  - **Shippable.** 2,600+ tests, offline amd64 + arm64 packages built by one command on an Apple Silicon Mac (each with its own triple architecture check), 1,000-server scale, and a demo mode that fills every panel with deterministic fixtures so the UI can be reviewed on a machine with no fleet attached.
- **[hermes-purge](https://github.com/XiaoBinGan/hermes-purge)** [![release](https://img.shields.io/badge/release-3.7.3-2ea043?style=flat)](https://github.com/XiaoBinGan/hermes-purge) - A capability layer for Hermes Agent: 77 capabilities, each landing through one of four independent paths (Python AST / site-packages shim / text / config), so a host upgrade that moves code does not silently turn the patch off. Turns approvals and guardrails off, swaps the prompt persona, resamples on refusal, and rolls back byte-for-byte. Zero dependencies, verified on macOS and Windows; the same engine drives a DSH adapter.
- **[anti-geo](https://github.com/XiaoBinGan/anti-geo)** [![release](https://img.shields.io/badge/release-v0.4.1-2ea043?style=flat)](https://github.com/XiaoBinGan/anti-geo) - A purely local MV3 extension that lays out what stands behind every citation in an AI answer, across eight engines (ChatGPT / Perplexity / Google AI Overviews / 豆包 / Kimi / 元宝 / 秘塔 / DeepSeek): a source that earned the citation, or a content farm built to poison the answer. No backend, zero dependencies, 119 tests.
- **[model-deploy-platform](https://github.com/XiaoBinGan/model-deploy-platform)** - Lightweight control plane for local LLM deployment: scan the host, recommend a model and quantization, plan the parameters, then deploy to vLLM / SGLang / Ollama / Transformers and test the OpenAI-compatible API.
- **[dsh-mermaid-fence](https://github.com/XiaoBinGan/dsh-mermaid-fence)** - DeepSeek Harness Web GUI plugin: renders a settled `mermaid` fence as an SVG diagram, then hardens the rendered SVG so the output cannot fetch or execute.
- **[DocMind](https://github.com/XiaoBinGan/DocMind)** - Reasoning-based document QA. Parses PDFs to Markdown, builds an index tree from the document structure, and lets the model navigate that tree instead of chasing vector similarity.
- **[wsPlayer](https://github.com/tokamakz/wsPlayer)** [![GitHub stars](https://img.shields.io/github/stars/tokamakz/wsPlayer?style=flat&color=gold)](https://github.com/tokamakz/wsPlayer) - Built with colleagues: a low-latency WebSocket-fMP4 web player. H.264 plays through MSE; H.265 is decoded with WebAssembly FFmpeg and rendered through WebGL, which is how it plays in browsers without native HEVC support. The React component ships as `magic-videoplayer` ([source](https://github.com/XiaoBinGan/MagicPlayer)), with format detection and multi-player time sync.
- **[gpu-calculator](https://github.com/XiaoBinGan/gpu-calculator)** - A single-page calculator for how large a model actually fits on a given card.
- **[OpenWebUi_webSearch](https://github.com/XiaoBinGan/OpenWebUi_webSearch)** - An AI web-search backend for Open WebUI.
- **[GB28181_SIP](https://github.com/XiaoBinGan/GB28181_SIP)** - A Go implementation of the GB28181 SIP stack for video surveillance.

#### Contributing to

- **[rust-anything](https://github.com/erkamyaman/rust-anything)** [![GitHub stars](https://img.shields.io/github/stars/erkamyaman/rust-anything?style=flat&color=gold)](https://github.com/erkamyaman/rust-anything) - **The second-most active contributor** on the project's commit graph, behind the maintainer. A rewrite is only safe when it matches the original's recorded behaviour, and a claim about a language is only worth what its parser knows: a C-style array parameter keeps its dimensions, a Java wildcard is named a wildcard and still refused, a YARD `@param` reads in either order, a phpdoc type containing a space parses, integer specifiers parse in any order, and `report` takes `--resolve-from` the way `bench` and `fuzz` already did.
- **[REA: Reverse Engineer Anything](https://github.com/morluto/rea)** [![GitHub stars](https://img.shields.io/github/stars/morluto/rea?style=flat&color=gold)](https://github.com/morluto/rea) - **9th of 440 contributors** on the commit graph — the top two percent of a project this size. The lanes have moved well past JavaScript: native / ELF / PE reads go through one `BinaryReader`, a 32-bit `prpsinfo` decodes with a 32-bit `pr_uid`, `pefile`'s unrounded raw offset survives a sub-page section, a v8 code-cache header size comes from the container, browser CORP and `X-Content-Type-Options` values must be grammatical before they are reported, and an HTTP method token Node refuses at the call site is refused here too.
- **[Linger](https://github.com/simplexai-labs/linger)** [![GitHub stars](https://img.shields.io/github/stars/simplexai-labs/linger?style=flat&color=gold)](https://github.com/simplexai-labs/linger) - **Among the ten most active contributors** of an agent that runs entirely on your own PC: an installer that says **why** `initdb` failed rather than where to look, names and descriptions counted in characters the way each contract says, a mention that works in unspaced scripts, and a Simplified Chinese README.
- **[Strata](https://github.com/Niko1221/Strata)** [![GitHub stars](https://img.shields.io/github/stars/Niko1221/Strata?style=flat&color=gold)](https://github.com/Niko1221/Strata) - Local inference for Qwen3.8-Flash-Next on consumer hardware. Community benchmark reports on an RTX 5090 (a card shared with other workloads versus held exclusively), and two fixes on trunk from what the measurements turned up: a launcher that still starts the bundled runtime when `access(X_OK)` is denied, and a saved preset whose lower-case model tag reaches setup as its key.
- **[Run:ai](https://github.com/dsx-ai-factory/run-ai)** [![GitHub stars](https://img.shields.io/github/stars/dsx-ai-factory/run-ai?style=flat&color=gold)](https://github.com/dsx-ai-factory/run-ai) - Go control plane for Kubernetes workload orchestration. I work through the installer validation, the quota-rounding path and label hashing — the places where a value that looks fine in a chart turns into a workload that does not schedule.
- **[train-llm-from-scratch](https://github.com/FareedKhan-dev/train-llm-from-scratch)** [![GitHub stars](https://img.shields.io/github/stars/FareedKhan-dev/train-llm-from-scratch?style=flat&color=gold)](https://github.com/FareedKhan-dev/train-llm-from-scratch) - Merged: modern-GPU compatibility and documented RTX 5090 validation.

---

### 你好，我是 Alben

人工智能行业从业者，拥有人工智能相关专利 12 篇，其中发明专利发布 10 篇。长期写中文长文，方向是大模型部署、
AI Agent、AI Infra 与推理框架，也写把一个 Agent 产品拆开之后看到的真实问题。

最近主要在做消费级硬件上的本地推理：测量它、部署它，然后修掉那些只在真机上才暴露的故障。我为
[Strata](https://github.com/Niko1221/Strata) 写过 RTX 5090 的社区压测报告（同一张卡被别的任务占用，
对比完全独占），也顺着这些测量结果提了对应修复。

目前提交重心在 [rust-anything](https://github.com/erkamyaman/rust-anything)（44 位贡献者里排第 2，仅次于
维护者）与 [REA](https://github.com/morluto/rea)（440 位贡献者里排第 9）。

个人研究方向是本地推理、Agent 工具链和 benchmark。想在这几块合作，欢迎公众号留言，或者到我参与过的仓库开
issue。中文、英文都可以。

**联系方式** —— CSDN：[吴佳浩 Alben](https://blog.csdn.net/weixin_43712047) ·
掘金社区：[吴佳浩 Alben](https://juejin.cn/user/2696441245481975) ·
简书：吴佳浩 · 微信公众号：全栈架构师笔记

#### 我在做

- **[OpenLog](https://github.com/XiaoBinGan/OpenLog)** [![release](https://img.shields.io/badge/release-v1.3.0-2ea043?style=flat)](https://github.com/XiaoBinGan/OpenLog/releases) - **自托管的观测平台：GPU 集群、Docker 主机、Kubernetes 集群全在一处 —— 一个 Node 进程、一个端口，没有云依赖、没有遥测、不用注册。** 系统与 GPU 指标、实时日志流、容器管理、远程 SSH 主机，外加**内置一套 Prometheus 兼容的时序库**（抓任意 `/metrics`，PromQL 子集 `rate()` / `sum by()` / `topk()` / `histogram_quantile()`，带 `for:` 与分组/抑制/静默的表达式告警，分层保留，接收 `remote write` —— Grafana 直接指 `/api/v1/*`，也可以让 Prometheus 来抓 OpenLog 自己的 `/metrics`）。在这之上挂一个读过数据就能动手的 agent：定位问题 → 读代码 → 改 → 验证，每次写都要确认并留审计。
  - **Kubernetes 只读接入，默认写不进去。** 直连 kube-apiserver —— 节点上不装任何东西、不需要 `kubectl`，mTLS 与 ServiceAccount token 都支持，粘几个 kubeconfig 就有几个集群。
  - **HAMi vGPU：分配 vs 实际使用。** 注解只说明每个 Pod **拿到了多少**；用你已有的 SSH 跑 `nvidia-smi` 才知道**实际用了多少**，按 GPU UUID join —— 因为 HAMi v2 已经去掉利用率序列。测不到的卡会明说，而不是显示一排 0。
  - **调度策略、事件摘要、可选写操作。** `binpack` / `spread` 与超卖比例各自带来源（`configmap` / `scheduler-args` / `default`）；`type=Warning` 事件按 reason 归并成一行；扩缩容、滚动重启、优雅删 Pod 在 `OPENLOG_K8S_WRITE=1` 之前一律 **403**，每次成功的写都连同改动前的副本数一起落审计。
  - **能交付。** 2,600+ 测试；在 Apple Silicon Mac 上一条命令出 amd64 + arm64 离线包（各自三重架构校验）；1,000 台服务器量级；演示模式用确定性夹具把每个面板填满，没有集群的机器上也能审 UI。
- **[hermes-purge](https://github.com/XiaoBinGan/hermes-purge)** [![release](https://img.shields.io/badge/release-3.7.3-2ea043?style=flat)](https://github.com/XiaoBinGan/hermes-purge) - 给 Hermes Agent 打的能力层：77 条能力，每条走四条独立落地路径之一（Python AST / site-packages shim / 文本 / 配置），宿主升级把代码挪了位置也不会把补丁悄悄关掉。关审批与护栏、换提示词人格、被拒自动重采样，改坏了能逐字节回滚。零依赖，macOS 与 Windows 都实测过；同一套引擎还驱动一个 DSH adapter。
- **[anti-geo](https://github.com/XiaoBinGan/anti-geo)** [![release](https://img.shields.io/badge/release-v0.4.1-2ea043?style=flat)](https://github.com/XiaoBinGan/anti-geo) - 纯本地 MV3 扩展：在八个 AI 引擎（ChatGPT / Perplexity / Google AI 概览 / 豆包 / Kimi / 元宝 / 秘塔 / DeepSeek）的回答里，把每条引用的底细摊开 —— 是挣来的引用，还是专门喂给 AI 的内容农场。无后端、零依赖、119 个测试。
- **[model-deploy-platform](https://github.com/XiaoBinGan/model-deploy-platform)** - 轻量级本地大模型部署控制面：探测宿主机、推荐模型与量化、规划启动参数，然后交给 vLLM / SGLang / Ollama / Transformers 部署，并测试 OpenAI 兼容接口。
- **[dsh-mermaid-fence](https://github.com/XiaoBinGan/dsh-mermaid-fence)** - DeepSeek Harness Web GUI 插件：把**已定格**的 `mermaid` 围栏渲染成 SVG 图，再对渲染结果做一遍加固，让图里的内容既不能发起请求、也不能执行。
- **[DocMind](https://github.com/XiaoBinGan/DocMind)** - 推理式文档问答。PDF 先解析成 Markdown，再按文档结构生成索引树，让模型自己去遍历这棵树，而不是靠向量相似度找片段。
- **[wsPlayer](https://github.com/tokamakz/wsPlayer)** [![GitHub stars](https://img.shields.io/github/stars/tokamakz/wsPlayer?style=flat&color=gold)](https://github.com/tokamakz/wsPlayer) - 和同事一起做的低延时 WebSocket-fMP4 Web 播放器：H.264 走 MSE 播放，H.265 用 WebAssembly FFmpeg 解码、WebGL 渲染，解决浏览器不原生支持 H.265 的问题；React 组件发布为 `magic-videoplayer`（[源码](https://github.com/XiaoBinGan/MagicPlayer)），带视频格式识别与多播放器时间同步。
- **[gpu-calculator](https://github.com/XiaoBinGan/gpu-calculator)** - 单页计算器：给定一张卡，模型到底放不放得下。
- **[OpenWebUi_webSearch](https://github.com/XiaoBinGan/OpenWebUi_webSearch)** - 给 Open WebUI 用的 AI 联网搜索后端。
- **[GB28181_SIP](https://github.com/XiaoBinGan/GB28181_SIP)** - Go 实现的 GB28181 SIP 协议栈，面向视频监控。

#### 我在参与

- **[rust-anything](https://github.com/erkamyaman/rust-anything)** [![GitHub stars](https://img.shields.io/github/stars/erkamyaman/rust-anything?style=flat&color=gold)](https://github.com/erkamyaman/rust-anything) - **该仓库提交图上第二活跃的贡献者**，仅次于维护者本人。前提很简单：重写只有在每一步都对得上原实现记录下来的行为时才安全，而关于某门语言的断言，只值它的解析器真正懂的那部分 —— C 风格数组参数保住维度，Java 通配符被叫作通配符且照样拒绝，YARD `@param` 两种顺序都读，带空格的 phpdoc 类型能解析，整数格式符任意顺序都认，`report` 也像 `bench`、`fuzz` 一样接受 `--resolve-from`。
- **[REA: Reverse Engineer Anything](https://github.com/morluto/rea)** [![GitHub stars](https://img.shields.io/github/stars/morluto/rea?style=flat&color=gold)](https://github.com/morluto/rea) - **440 位贡献者里的第 9 位** —— 这种体量的项目里排进前 2%。而且早就不止 JavaScript 一条链路：native / ELF / PE 的读取统一走一个 `BinaryReader`，32 位 `prpsinfo` 按 32 位 `pr_uid` 解，`pefile` 未取整的 raw offset 在 sub-page section 上保留，v8 code cache 的头长度从容器里读，browser 的 CORP 与 `X-Content-Type-Options` 值必须先语法合法才上报，Node 在调用点拒绝的 HTTP method token 这里也拒绝。
- **[Linger](https://github.com/simplexai-labs/linger)** [![GitHub stars](https://img.shields.io/github/stars/simplexai-labs/linger?style=flat&color=gold)](https://github.com/simplexai-labs/linger) - **完全跑在自己电脑上的 agent，我是它最活跃的十位贡献者之一**：安装器在 `initdb` 失败时说清**为什么**失败而不只是去哪儿看，名称与描述按各自契约的字符数来数，无空格文字里的 @ 也能提到人，补了简体中文 README。
- **[Strata](https://github.com/Niko1221/Strata)** [![GitHub stars](https://img.shields.io/github/stars/Niko1221/Strata?style=flat&color=gold)](https://github.com/Niko1221/Strata) - 在消费级硬件上跑 Qwen3.8-Flash-Next 的本地推理。写了 RTX 5090 的社区压测报告（同一张卡被别的任务占用 vs 完全独占），并顺着这些测量在主干上落了两个修复：`access(X_OK)` 被拒时启动器仍能拉起内置运行时，保存的预设用小写模型标签也能作为 key 抵达 setup。
- **[Run:ai](https://github.com/dsx-ai-factory/run-ai)** [![GitHub stars](https://img.shields.io/github/stars/dsx-ai-factory/run-ai?style=flat&color=gold)](https://github.com/dsx-ai-factory/run-ai) - Kubernetes 工作负载编排的 Go 控制面。我在安装器校验、配额取整与 label 哈希这几条路径上做事 —— 也就是「在图里看着没问题、落到工作负载上却调度不出去」的那些位置。
- **[train-llm-from-scratch](https://github.com/FareedKhan-dev/train-llm-from-scratch)** [![GitHub stars](https://img.shields.io/github/stars/FareedKhan-dev/train-llm-from-scratch?style=flat&color=gold)](https://github.com/FareedKhan-dev/train-llm-from-scratch) - 已合并：现代 GPU 兼容性改进与 RTX 5090 验证记录。

