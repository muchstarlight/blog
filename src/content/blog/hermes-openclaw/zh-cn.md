---
title: 对 Hermes 和 OpenClaw 的一些看法
pubDate: 2026-04-25
description: 上手体验后的真实感受
category: 技术随笔
image: ./images/对Hermes和Openclaw的一些看法.png
draft: false
slugId: momo/hermes-openclaw
---

最近在网络上看到了不少推荐 Hermes 和 OpenClaw 的视频，这些视频给人的感觉就是：不去了解这些新技术就落后于时代了。但我实际上手体验之后发现完全不是这样的，甚至这些技术本来就不成熟，我认为完全就是一个中间产物，根本没必要去详细了解。

## 对于 OpenClaw

OpenClaw 这个 AI Agent 想法非常好，确实让 AI Agent 比较像人了，接入即时聊天也促进了这一点。问题是这个东西根本不稳定。我是不太能理解这代码怎么这么冗长的，Vibe Coding 的后果吗？启动起来超级慢，配置工具和本体是一个文件，本身 Node.js 的效率对比其他语言就没那么高，还要完整加载这屎山。

## 对于 Hermes

Hermes 本身也是 Vibe Coding 的产物，但感觉比 OpenClaw 稳定了很多，思路也非常不错，可以总结技能，然后转换成知识。但是这个东西有一个缺点，你根本不知道 Skill 什么时候创建，虽然内容是透明的，但你可能也无法理清其关系和运作原理，非常难以维护。以及技能会占用上下文的，一大堆技能还没干活能先吃一半上下文（夸张），分散模型注意力，得不偿失啊。

## 总结

目前 AI 正在高速发展，完全没必要因为无法实时跟进新内容而焦虑，除非你是从业者。好用的东西需要时间来检验，我们要选择的不是新概念新技术，而是我们所需要的技术。

## 更新

### 2026-08-12 对文章内容稍作修改

有一些内容有点过时了，所以更新了一下，以及谈谈我新的理解

最近也是用上Openclaw了，~~主要是Token开销大，可以帮花花掉Opencode Go 用不完的deepseek v4 flash额度~~，目前对我来说，Openclaw和Hermess可能还是用处不大，学生党没有那些小的杂事，或者说事情不多，自己手动干比AI干快多了。

现在用来Vide Coding的Agent是Zcode，也许是GLM和Deepseek一样没眼睛的原因，Zcode接Deepseek-v4-flash还挺好用的，Codex在我目前使用的Windows端卡的根本没法用，Claude Code之前爆出来的后门让我不信任这家公司了，我的个人感觉是AI Agent推荐使用官方自己出的。


