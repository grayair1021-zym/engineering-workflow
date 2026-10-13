# Engineering Workflow

一份以实际风险和需求为边界的工程协作 Skill：在必要处充分验证，覆盖功能自然包含的场景，证据充分后及时停止。

An instruction-only engineering Skill for proportionate verification, necessary generality, and clear completion boundaries.

## 内容与边界

- **Minimum Sufficient Rigor**：验证强度匹配风险；保留安全、数据完整性、兼容承诺和回滚；有新证据再重验。
- **Minimum Necessary Generality**：区分功能对象和首个样例，考虑一个合理的第二场景；优先简单参数与现有接口。
- 工程入口按需加载三个分支：调研与方案确认、能力准入、疑难诊断。普通修复不固定执行整套流程。
- 保留用户授权、只读边界和收尾确认；不把询问“完成了吗”变成新的全量审计。

此仓库只包含 **engineering-workflow**；`writing-for-agents`、`codebase-design`、`skill-creator` 和 `openai-docs` 是按任务使用的可选协作能力，不是安装依赖。必要的 Skill mechanics 已包含在 references 中。

Skill 是指导文字，**不是权限沙箱或安全隔离工具**。实际文件、网络、进程及审批边界由宿主和项目落实。没有安装脚本、MCP、Hook、常驻服务或模型调用；也不要求采用某套 Registry、记忆系统或工程框架。ECC 是新增能力时的研究候选，不会被自动安装。

## 使用

先审阅 `skills/engineering-workflow/`。按 [Codex 官方 Skill 文档](https://developers.openai.com/codex/skills/)选择安装位置：

- 项目范围：复制完整目录到项目的 `.agents/skills/engineering-workflow/`。
- 用户范围：复制完整目录到 `~/.agents/skills/engineering-workflow/`。

已有同名 Skill 时先比较内容，不覆盖或重复安装。Codex 可按 description 自动选择，也可显式使用 `$engineering-workflow`。例如：

> 修复这个模块的 CSV 导入错误，验证受影响行为，并遵守项目已有授权与发布规则。

直接 Skill 文件适合本地／仓库使用；跨产品可安装分发可参考官方 Plugin 格式，本仓库未创建 Plugin 或市场发布。

## 验证范围

这是自用实践流程的公开适配版，不宣称通用性能提升或零缺陷。发布前检查原生 Skill 格式、引用完整性、私人信息、许可证和隔离任务行为。上述检查不能代替具体项目的测试，也不能保证所有模型都遵守指令。

2026-10-13 首次公开适配验证：原生格式与包内链接检查通过；一次独立隔离任务仅修正指定拼写错误，并通过准入 reference 只读评估新增 Skill，未越界创建或安装。该验收使用显式 Skill 路径，不是自动 discovery、跨模型性能或宿主沙箱验证。

## 来源与许可

采用 MIT 许可。疑难诊断及部分 Agent 文档方法参考 [Matt Pocock 的 Skills](https://github.com/mattpocock/skills)，保留其版权和许可；具体来源、固定参考修订及适配范围见 [ATTRIBUTION](skills/engineering-workflow/ATTRIBUTION.md)。模型／Skill 设计另参考 [OpenAI 官方文章](https://developers.openai.com/blog/rethinking-skills-and-prompts-for-gpt-6-astra)。
