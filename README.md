# dsh-superagent

> 本文档其余部分为英文；以下是中文项目简介。The rest of this document is in English.

## 中文简介

dsh-superagent 是一个面向单个 GitHub 仓库的主动式编码智能体，以 [DeepSeek Harness](https://www.deepseek.com/en/harness/) 的 bundle 形式打包。它监听 GitHub 以及（可选）Feishu 消息：当被授权的人向它请求工作时，它会创建一个工作项，在自己的智能体会话与目录中独立完成工作，并在原始对话中回复结果（例如一个 pull request）。Web 面板会展示需要人工介入的事项。

这也是一种与智能体协作的方式：**尽可能少占用人的注意力，同时尽可能多产出价值。** 一个能为整个团队行动的智能体，同样可能浪费整个团队的注意力。因此，它只会在被要求、或团队编写的规则允许时采取行动，并且只在有人必须行动、或能直接使用某个结果时才发言。[docs/000-philosophy.md](docs/000-philosophy.md) 阐述了这一原则及其对运维者的要求。

> **仅供研究参考的原型，并非 DeepSeek 官方产品。** 这段代码源自我们团队的日常开发工作，其中大量工程实现由编码智能体完成。请将其视为研究代码而非生产级软件：它可能仍存在 bug，代码风格与工程实践也可能并不统一。在你自己的环境中使用前，请先审查并适配。
>
> 我们已为公开发布做了适配，因此它与我们的内部版本以及《Exploring Super-agent Design: Towards a More Autonomous Agent System》一文中所描述的实现并不完全一致。文中讨论的部分设计是未来的发展方向，尚未在该原型中实现。

---

> **Research prototype for reference only, not an official DeepSeek product.** This code grew out of our team's day-to-day development work, with much of the engineering done by coding agents. Treat it as research code, not production-ready software. It may still contain bugs, and its coding style and engineering practices may be inconsistent. Review and adapt it before using it in your own environment.
>
> We have adapted it for publication, so it is not identical to our internal version or the implementation described in *Exploring Super-agent Design: Towards a More Autonomous Agent System*. Some designs discussed in the article are directions for future development and are not implemented in this prototype.

dsh-superagent is a proactive coding agent for one GitHub repository, packaged as a bundle for [DeepSeek Harness](https://www.deepseek.com/en/harness/). It listens to GitHub and, optionally, Feishu. When someone allowed asks the agent for work, it opens a work item, works on it in its own agent session and directory, and answers in the original conversation, for example with a pull request. A web panel shows what needs a person.

It is also a way of working with an agent: **take as little human attention as possible, and give as much value as possible.** An agent that can act for a whole team can also waste a whole team's attention, so it acts only when asked or when a rule the team wrote allows it, and speaks only when someone must act or can use a result. [docs/000-philosophy.md](docs/000-philosophy.md) explains the principle and what it asks of the operator.

## Setup

Setup has many steps, so an agent does it with you. Ask your coding agent:

> Read SETUP.md in this repository and set up dsh-superagent with me.

It asks one short question at a time, shows the full plan once, and then installs and configures everything. [SETUP.md](SETUP.md) is what it follows.

## Documentation

Read the numbered documents in order; each builds only on the ones before it.

- [000 Philosophy](docs/000-philosophy.md)
- [001 Domain model](docs/001-domain.md)
- [002 Authorization](docs/002-authorization.md)
- [003 Execution](docs/003-execution.md)
- [004 Prompts](docs/004-prompts.md)
- [005 Panel](docs/005-panel.md)
- [006 Deployment](docs/006-deployment.md): manual setup, configuration, upgrades and troubleshooting
- [007 Architecture](docs/007-architecture.md)
- [008 Cookbook](docs/008-cookbook.md): adding a Source

## Development

`pnpm check` runs the typecheck, the tests and the build.

## License

[MIT](LICENSE)
