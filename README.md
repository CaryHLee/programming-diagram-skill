# Programming-Diagram-Pro

把程序或系统中的模块调用关系与步骤顺序，转化为一张清晰、专业的 HTML 页面，帮助快速理解代码架构和执行逻辑。

## 它能做什么

这个技能主要解决两类问题：

- **谁调用了谁**：梳理模块、进程、文件之间的调用关系和数据处理流向。
- **事情按什么顺序发生**：呈现参与者之间消息发送、分支判断和关键说明的执行顺序。

最终产物是单个 HTML 页面：

- 上半部分使用 `flowchart` 绘制调用关系思维导图；
- 下半部分使用 `sequenceDiagram` 绘制 UML 时序图；
- 内置本地 `mermaid` 引擎，无需联网即可离线渲染。

## 适用场景

- 阅读大量代码时，快速理清模块之间的依赖与调用关系。
- 维护、交接或讲解项目时，直观展示程序架构与执行步骤。
- 需要整理代码架构，或生成“调用关系图 / 流程逻辑图 / 思维导图 + 时序图”时。

## 目录结构

```
.
├── SKILL.md
├── agents
│   └── openai.yaml
└── assets
    ├── mermaid.min.js
    ├── LICENSE-mermaid
    └── 思维导图时序图页面模板.html
```

## 使用方式

对AI说：安装https://github.com/CaryHLee/programming-diagram-skill/
将本目录作为 Codex skill 放入本地 skills 目录后，即可在需要梳理程序架构或绘制调用关系、流程逻辑时触发使用。

## 许可

- 本项目采用 MIT 许可。
- `assets/mermaid.min.js` 来自 mermaid，采用 MIT 许可，详见 `assets/LICENSE-mermaid`。
