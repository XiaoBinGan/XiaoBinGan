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

Right now most of my open-source commits go to [REA](https://github.com/morluto/rea), the agentic
reverse-engineering toolkit, where I work mainly on the JavaScript analysis lanes.

My personal research is in local inference, agent tooling and benchmarking. If you would like to
collaborate on any of that, reach me on WeChat or open an issue on a repository I've worked in.
中文 / English both fine.

**Elsewhere** — CSDN: [吴佳浩 Alben](https://blog.csdn.net/weixin_43712047) ·
掘金 (Juejin): [吴佳浩 Alben](https://juejin.cn/user/2696441245481975) ·
简书 (Jianshu): 吴佳浩 · WeChat 公众号: 全栈架构师笔记

#### Building

- **[dsh-mermaid-fence](https://github.com/XiaoBinGan/dsh-mermaid-fence)** - DeepSeek Harness Web GUI plugin: renders a settled `mermaid` fence as an SVG diagram, then hardens the rendered SVG so the output cannot fetch or execute.
- **[DocMind](https://github.com/XiaoBinGan/DocMind)** - Reasoning-based document QA. Parses PDFs to Markdown, builds an index tree from the document structure, and lets the model navigate that tree instead of chasing vector similarity.
- **[model-deploy-platform](https://github.com/XiaoBinGan/model-deploy-platform)** - Lightweight control plane for local LLM deployment: scan the host, recommend a model and quantization, plan the parameters, then deploy to vLLM / SGLang / Ollama / Transformers and test the OpenAI-compatible API.
- **[wsPlayer](https://github.com/tokamakz/wsPlayer)** - Built with colleagues: a low-latency WebSocket-fMP4 web player. H.264 plays through MSE; H.265 is decoded with WebAssembly FFmpeg and rendered through WebGL, which is how it plays in browsers without native HEVC support. The React component ships as `magic-videoplayer` ([source](https://github.com/XiaoBinGan/MagicPlayer)), with format detection and multi-player time sync.
- **[gpu-calculator](https://github.com/XiaoBinGan/gpu-calculator)** - A single-page calculator for how large a model actually fits on a given card.
- **[OpenWebUi_webSearch](https://github.com/XiaoBinGan/OpenWebUi_webSearch)** - An AI web-search backend for Open WebUI.
- **[GB28181_SIP](https://github.com/XiaoBinGan/GB28181_SIP)** - A Go implementation of the GB28181 SIP stack for video surveillance.

#### Contributing to

- **[REA: Reverse Engineer Anything](https://github.com/morluto/rea)** [![GitHub stars](https://img.shields.io/github/stars/morluto/rea?style=flat&color=gold)](https://github.com/morluto/rea) - My most active project right now: more than 20 merged pull requests, mostly on the JavaScript analysis lanes. An HTTP request is no longer emitted for a target that is not a URL, a socket is not emitted for a literal out-of-range port, spawn options are read the way Node reads them, and a resource release must match the handle it acquired.
- **[Strata](https://github.com/Niko1221/Strata)** [![GitHub stars](https://img.shields.io/github/stars/Niko1221/Strata?style=flat&color=gold)](https://github.com/Niko1221/Strata) - Local inference for Qwen3.8-Flash-Next on consumer hardware. Community benchmark reports on an RTX 5090 (shared card versus exclusive card), plus fixes to the managed runtime host lifecycle, the disk check, `doctor` and `models explain` diagnostics, Docker seccomp startup and Windows model deletion.
- **[Run:ai](https://github.com/dsx-ai-factory/run-ai)** [![GitHub stars](https://img.shields.io/github/stars/dsx-ai-factory/run-ai?style=flat&color=gold)](https://github.com/dsx-ai-factory/run-ai) - Go control plane for Kubernetes workload orchestration. Nil-safe org-unit and policy-scope handling, quota rounding, cache-lock reporting, installer validation for nodes and Helm values, CLI flag bounds and label hashing.
- **[train-llm-from-scratch](https://github.com/FareedKhan-dev/train-llm-from-scratch)** [![GitHub stars](https://img.shields.io/github/stars/FareedKhan-dev/train-llm-from-scratch?style=flat&color=gold)](https://github.com/FareedKhan-dev/train-llm-from-scratch) - Merged: modern-GPU compatibility and documented RTX 5090 validation.
- **[all-agentic-architectures](https://github.com/FareedKhan-dev/all-agentic-architectures)** [![GitHub stars](https://img.shields.io/github/stars/FareedKhan-dev/all-agentic-architectures?style=flat&color=gold)](https://github.com/FareedKhan-dev/all-agentic-architectures) - Added a DeepSeek provider and the Mixture of Agents (MoA) architecture.

---

### 你好，我是 Alben

人工智能行业从业者，拥有人工智能相关专利 12 篇，其中发明专利发布 10 篇。长期写中文长文，方向是大模型部署、
AI Agent、AI Infra 与推理框架，也写把一个 Agent 产品拆开之后看到的真实问题。

最近主要在做消费级硬件上的本地推理：测量它、部署它，然后修掉那些只在真机上才暴露的故障。我为
[Strata](https://github.com/Niko1221/Strata) 写过 RTX 5090 的社区压测报告（同一张卡被别的任务占用，
对比完全独占），也顺着这些测量结果提了对应修复。

目前我开源提交最多的是 [REA](https://github.com/morluto/rea)（Agent 反向工程工具），改动主要集中在
JavaScript 分析链路。

个人研究方向是本地推理、Agent 工具链和 benchmark。想在这几块合作，欢迎公众号留言，或者到我参与过的仓库开
issue。中文、英文都可以。

**联系方式** —— CSDN：[吴佳浩 Alben](https://blog.csdn.net/weixin_43712047) ·
掘金社区：[吴佳浩 Alben](https://juejin.cn/user/2696441245481975) ·
简书：吴佳浩 · 微信公众号：全栈架构师笔记

#### 我在做

- **[dsh-mermaid-fence](https://github.com/XiaoBinGan/dsh-mermaid-fence)** - DeepSeek Harness Web GUI 插件：把**已定格**的 `mermaid` 围栏渲染成 SVG 图，再对渲染结果做一遍加固，让图里的内容既不能发起请求、也不能执行。
- **[DocMind](https://github.com/XiaoBinGan/DocMind)** - 推理式文档问答。PDF 先解析成 Markdown，再按文档结构生成索引树，让模型自己去遍历这棵树，而不是靠向量相似度找片段。
- **[model-deploy-platform](https://github.com/XiaoBinGan/model-deploy-platform)** - 轻量级本地大模型部署控制面：探测宿主机、推荐模型与量化、规划启动参数，然后交给 vLLM / SGLang / Ollama / Transformers 部署，并测试 OpenAI 兼容接口。
- **[wsPlayer](https://github.com/tokamakz/wsPlayer)** - 和同事一起做的低延时 WebSocket-fMP4 Web 播放器：H.264 走 MSE 播放，H.265 用 WebAssembly FFmpeg 解码、WebGL 渲染，解决浏览器不原生支持 H.265 的问题；React 组件发布为 `magic-videoplayer`（[源码](https://github.com/XiaoBinGan/MagicPlayer)），带视频格式识别与多播放器时间同步。
- **[gpu-calculator](https://github.com/XiaoBinGan/gpu-calculator)** - 单页计算器：给定一张卡，模型到底放不放得下。
- **[OpenWebUi_webSearch](https://github.com/XiaoBinGan/OpenWebUi_webSearch)** - 给 Open WebUI 用的 AI 联网搜索后端。
- **[GB28181_SIP](https://github.com/XiaoBinGan/GB28181_SIP)** - Go 实现的 GB28181 SIP 协议栈，面向视频监控。

#### 我在参与

- **[REA: Reverse Engineer Anything](https://github.com/morluto/rea)** [![GitHub stars](https://img.shields.io/github/stars/morluto/rea?style=flat&color=gold)](https://github.com/morluto/rea) - 目前投入最多的项目：已合并 20 多个 PR，主要集中在 JavaScript 分析链路。目标不是 URL 时不再产出 HTTP 请求、端口字面量越界时不再产出 socket、spawn 选项按 Node 的读法来读、资源释放必须对上实际拿到的 handle。
- **[Strata](https://github.com/Niko1221/Strata)** [![GitHub stars](https://img.shields.io/github/stars/Niko1221/Strata?style=flat&color=gold)](https://github.com/Niko1221/Strata) - 在消费级硬件上跑 Qwen3.8-Flash-Next 的本地推理。写了 RTX 5090 的社区压测报告（共享卡 vs 独占卡），也修了托管运行时宿主进程生命周期、磁盘检查、`doctor` 与 `models explain` 诊断、Docker seccomp 启动、Windows 下删除模型等问题。
- **[Run:ai](https://github.com/dsx-ai-factory/run-ai)** [![GitHub stars](https://img.shields.io/github/stars/dsx-ai-factory/run-ai?style=flat&color=gold)](https://github.com/dsx-ai-factory/run-ai) - Kubernetes 工作负载编排的 Go 控制面：org-unit 与 policy scope 的空值处理、配额取整、缓存锁上报、安装器对节点与 Helm 值的校验、CLI 参数边界与 label 哈希。
- **[train-llm-from-scratch](https://github.com/FareedKhan-dev/train-llm-from-scratch)** [![GitHub stars](https://img.shields.io/github/stars/FareedKhan-dev/train-llm-from-scratch?style=flat&color=gold)](https://github.com/FareedKhan-dev/train-llm-from-scratch) - 已合并：现代 GPU 兼容性改进与 RTX 5090 验证记录。
- **[all-agentic-architectures](https://github.com/FareedKhan-dev/all-agentic-architectures)** [![GitHub stars](https://img.shields.io/github/stars/FareedKhan-dev/all-agentic-architectures?style=flat&color=gold)](https://github.com/FareedKhan-dev/all-agentic-architectures) - 新增 DeepSeek provider 与 Mixture of Agents（MoA）架构。
