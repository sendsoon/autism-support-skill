# autism-support-skill

[English](README.md) | **简体中文**

给编程智能体用的孤独症谱系成长支持技能：帮助家庭理解孩子的发展特点，并在沟通、情绪、学习、感觉加工、生活自理和分年龄目标上给出可执行的做法。

```bash
npx skills add sendsoon/autism-support-skill
```

本技能**不**诊断孤独症，**不**开具治疗方案，也**不**以消除孤独症特征为目标。

技能正文、参考资料和示例是英文。与家长对话时，智能体使用家长正在使用的语言。

## 技能做什么

`autism-support-skill` 是给编程智能体使用的工作流（Cursor、Claude Code、Codex 及其他会加载 `SKILL.md` 的智能体）。家长描述一个具体困难后，智能体会：

1. 分开已经知道的事实和仍待验证的假设
2. 从发展、沟通、情绪、感觉、场景和安全几方面理解情况
3. 给出这个场景里可以尝试的步骤
4. 说明观察什么、不建议做什么，以及何时需要合格的专业人员评估
5. 在本地记下档案和按日期排列的问题日志，方便以后对照真实反馈做综合分析

眼神接触、安静服从或表面上“像普通孩子”不是成功标准。

## 成长记录

第一次谈到某个孩子时，先问昵称和现在的年龄，并写下首次记录日期。之后用这个日期推算年龄，不把旧年龄一直当成当前年龄。性别、学校简称、主要抚养人、日常学习生活活动能力和兴趣爱好随对话补齐，一次只补问一项。

每个具体问题追加到当前工作区的 `autism-support-records/<昵称>/logs/YYYY-MM-DD.md`。该目录已加入忽略列表，不会提交。技能仓库里没有真实孩子的档案。规则见 [references/records.md](references/records.md)。

## 何时使用

需要处理孤独症、自闭症、ASD、谱系、辅助沟通、情绪失调、同伴交往、注意力、生活自理、融合教育或成年过渡方面的具体问题时使用。

不要用它判断某人是否患有孤独症，不要用它推荐未经证实的根治方法，也不要把它当成医生、治疗师或学校团队的替代。

## 安装

```bash
npx skills add sendsoon/autism-support-skill
```

也可克隆本仓库，把 `SKILL.md`、`references/`、`examples/` 复制到所用智能体的 skills 目录。

安装后，目录页由 [skills.sh](https://skills.sh/) 在收到遥测后展示。

## 如何更新技能

若当初用 Skills CLI 安装，从 GitHub 拉取最新的 `SKILL.md`：

```bash
npx skills check
npx skills update autism-support-skill
```

`check` 只检查是否有新版本。`update` 会把本技能重装到原先那些智能体。要更新本机已安装的全部技能：

```bash
npx skills update
```

跳过确认提示：

```bash
npx skills update autism-support-skill -y
```

再执行一次安装命令也会覆盖为最新文件：

```bash
npx skills add sendsoon/autism-support-skill
```

若是手动复制安装的，先 `git pull` 本仓库，再把 `SKILL.md`、`references/`、`examples/` 覆盖到原来的 skills 目录。

## 用法

```text
孩子 4 岁，想吃零食时拉我去柜子前，但不会说名字。在家可以怎么支持？
一改变计划就哭得很厉害，怎样陪他，而不是硬让他撑过去？
怎样和学校谈适合他的支持？
```

如果缺一项信息就会改变建议，智能体应只问最关键的一个问题，而不是一次索要整份档案。

## 产出

原因还缺一环时，只问一个问题，先不给方案。

情况清楚后，回答保持很短：

1. 一句话说明做什么、为什么
2. 两到四个步骤
3. 一个观察点，或一件不要做的事

对中文用户用中文写。虚构示例见 [examples/output-template.md](examples/output-template.md)。

## 项目结构

本仓库是**单技能包**。技能放在仓库根目录，以便 `npx skills` 优先发现。

```text
autism-support-skill/
├── SKILL.md                      # 智能体入口：frontmatter + 工作流
├── skills.sh.json                # skills.sh 仓库页分组
├── README.md                     # English
├── README.zh-CN.md               # 简体中文
├── LICENSE
├── references/
│   ├── age-stages.md             # 各年龄阶段重点
│   ├── support-strategies.md     # 循证方法与使用边界
│   └── records.md                # 档案与问题日志规则
└── examples/
    ├── output-template.md        # 回答结构与虚构示例
    └── record-template.md        # 虚构档案与日志形状
```

| 文件 | 作用 |
|---|---|
| `SKILL.md` | 智能体实际执行的说明。YAML 的 `name` / `description` 决定能否被发现。 |
| `skills.sh.json` | 在 skills.sh 仓库页把本技能归入 **Family support**。不影响安装。 |
| `README.md` / `README.zh-CN.md` | 给人看的说明。技能本身是英文，这里保留中文版。 |
| `references/` | 按需阅读的年龄阶段、支持方法和成长记录规则。 |
| `examples/` | 输出结构，以及虚构的回答和档案示例。 |

## 许可证

[MIT](LICENSE)
