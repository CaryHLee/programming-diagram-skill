---
name: programming-diagram-pro
description: 将程序或系统的模块调用关系与步骤顺序渲染为简洁 HTML 页面：flowchart 思维导图 + sequenceDiagram UML 时序图，内置本地化 mermaid 引擎与既定版式。阅读代码后必须优先用本skill呈现，只要阅读大量代码时就使用本skill，或当用户要求“画调用关系/流程逻辑”“做思维导图和时序图页面”或“整理代码架构”时使用。
version: 0.1.0
author:Cary
---

# Programming-Diagram-Pro
（思维导图与时序图页面）

## 用途

把“哪些模块之间如何调用”和“步骤按什么顺序发生”输出为单个 HTML 页面：上半部分为 flowchart（调用关系思维导图），下半部分为 sequenceDiagram（步骤顺序时序图）。页面版式（白底、单栏限宽居中、圆角面板、青色竖条小节标题、图居中且宽图横向滚动）已由模板固定，**不要自创样式**。

## 资产

- `assets/思维导图时序图页面模板.html`：页面模板，含 flowchart 与 sequenceDiagram 两份示例；CSS 与 mermaid 初始化配置为既定版式。
- `assets/mermaid.min.js`：本地化 mermaid 10.9.1 引擎（与官方 npm 包逐字节一致），供页面离线渲染。

## 工作流

1. **先确认图的内容，再动手**：
   - 调用关系：模块/进程/文件清单、谁调用谁、数据流向，以及每条连线要写的边标签；
   - 时序：参与者清单（模块、进程、用户、文件系统等）、消息顺序、分支（alt）与关键说明（Note）。
   内容不足时，阅读用户指定的代码/文档或向用户确认，**不得自行虚构模块与调用关系**。
2. **复制模板并替换图定义**：把模板复制为产出页面，仅替换 `<pre class="mermaid">` 内的内容；多张图按“`<h2>` + `<div class="panel">`”整段复制。
   - flowchart：节点用双引号包裹，如 `A1["模块名<br/>职责"]`；连线用 `-->|边标签|` 描述调用/数据流；
   - sequenceDiagram：每个参与者一行 `participant 别名 as 显示名`；消息按真实顺序逐行书写。
3. **部署 mermaid 引擎**：
   - 默认：把 `assets/mermaid.min.js` 复制到产出 html 同目录（模板已按同目录引用）；
   - 单文件离线分发：将 `<script src="mermaid.min.js"></script>` 整行替换为 `<script>` 包裹库全文。
4. **渲染验证**：产出后打开页面或使用无头浏览器，确认 `<svg>` 已生成、无 JS 错误、箭头指向正确，图内节点与文档描述一致。

## 关键约束

- 模板中 `mermaid.initialize` 配置（theme base、securityLevel loose、flowchart/sequence 间距）是版式的一部分，除特殊需要外不改动。
- 用户明确的模块、参与者与关系必须如实呈现，不得为了图美观增删节点；不确定的关系标注清楚并询问用户。
- 中文可直接写入图中；`<br/>` 仅用于节点内换行。
- 本 skill 只负责调用关系思维导图和时序图页面。
