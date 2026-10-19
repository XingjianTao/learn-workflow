# Learn Workflow

[English](README.md)

通过虚拟案例，学习多个 skill 如何协作。本仓库包含两个可移植的指令型 skill：

| Skill | 用途 |
| --- | --- |
| **build-workflow** | 读取相关 skill 的真实约定，通过提问澄清关键决策，编写经确认的固定工作流、虚拟案例和练习。 |
| **learn-workflow** | 按固定流程逐步教学，反馈学习者的答案，并将上一环节的产物交给下一环节。 |

前者定义流程，后者教授某个确定版本。它们不包含自动执行工作流的引擎。

## 快速开始

使用 [Skills CLI](https://github.com/vercel-labs/skills) 安装，需要 Node.js/npm：

```sh
npx skills add XingjianTao/learn-workflow --skill build-workflow --skill learn-workflow
```

也可以将 `skills/build-workflow/` 和 `skills/learn-workflow/` 连同资源文件复制到所用 AI 工具支持的 skills 目录。例如 Codex 项目可以使用 `.agents/skills/`。在现有 AI 宿主之外，教学本身不需要额外的 API 密钥、Python 包、外部账户或独立应用；宿主需支持读取 skill 指令和对话，保存进度时还需可写目录。

先体验内置案例：

> 使用 $learn-workflow，用中文教我内置的读书会报名工作流。从第一道练习开始，等我回答再继续。

也可以创建自己的流程：

> 使用 $build-workflow，帮我设计从研究笔记到经过审查的报告的工作流。读取我提供的 skills，用 grilling 澄清未决问题，将固定流程、虚拟案例和练习保存到 workflows/research-report.md。

然后学习它：

> 使用 $learn-workflow，带我学习 workflows/research-report.md，每次一个练习。

不同宿主的调用语法可能不同，也可以明确要求 AI 读取对应的 `SKILL.md`。能够读取文件，不代表宿主已经将它注册为可选 skill。

## 如何学习

1. 读取作者确认的内置案例，或用户确认的工作流定义。
2. 查看一个短示例和当前输入产物。
3. 自己选择下一步，或写出一小段产物。
4. 得到具体反馈；遗漏关键约束时先修正。
5. 将通过检查的产物传入下一环节。
6. 换一个虚拟情境，检验能否独立使用这套流程。

内置的[读书会案例](skills/learn-workflow/references/reading-club.md)包含需求澄清、规格、任务拆分、实现证据、审查和进度记录。案例故意缺少一次重启验证，让学习者练习返回补齐证据，而不是过早宣布完成。

教学区分“已展示理解”“自述理解”“跳过”和“仍需练习”。本地或对话内的进度记录会保存正在等待回答的问题和已接受的产物，不会把“已经讲过”当成“已经学会”。讲解可以使用学习者的语言，但不改变案例规则。

## 虚拟演练与真实工作

默认明确标记为 **SIMULATED／模拟**。教学过程中不会为了演示而调用实现类 skill、安装依赖、创建真实 issue、提交代码、发布内容或发送消息。可以在指定的学习目录保存进度。实际操作属于另一个模式，需要明确目标，并通过正常授权的工具执行。

`build-workflow` 在可用时读取用户提供、本地已有或权威来源中的 skill 定义，记录来源限制，不安装缺失的 skill。`grilling` 是可选的访谈辅助；未安装时也有自包含的提问方法。`learn-workflow` 只读取已形成的固定定义，不根据已安装 skills 临时拼出另一条流程。

## 文件结构

```text
skills/
  build-workflow/
    SKILL.md
    agents/openai.yaml
    assets/workflow-template.md
  learn-workflow/
    SKILL.md
    agents/openai.yaml
    references/checkpoint.md
    references/reading-club.md
evals/scenarios.md
```

每个 skill 的必要资源都在自身目录中，可以单独安装。工作流文件可以保存在宿主能读取的其他位置；格式约定见[工作流定义模板](skills/build-workflow/assets/workflow-template.md)。

## 验证与限制

[行为验证场景](evals/scenarios.md)覆盖首次教学、错误答案、中断恢复、模拟边界和流程编写。这些是对 AI 行为的检验案例，不是自动执行引擎，也不保证所有宿主都已兼容。验证记录见 [evals/RESULTS.md](evals/RESULTS.md)。

Skill 仍然是给模型的指令，模型可能出错。重要产物需要检查，虚拟结果不能作为真实测试证据。固定案例中的来源说明对应所查阅的版本或日期，不保证上游未来版本行为不变。

## 致谢与许可

由 Xingjian Tao 原创实现。访谈、产物交接和依据学习证据推进的思路参考了 [Matt Pocock 的 skills](https://github.com/mattpocock/skills)，尤其是 `grilling`、`to-spec`、`to-tickets`、`teach` 和 `ask-matt`。本仓库未打包这些上游 skill，也不将其作为必装运行依赖。详见 [ATTRIBUTION.md](ATTRIBUTION.md)。

采用 [MIT 许可证](LICENSE)。
