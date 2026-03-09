# project-mastermind

这是一个为 Claude Code 开发的技能（Skill），用于快速创建项目计划、任务拆解、估算、资源分配、进度监控及报告。搭建成skills主要是看好能够稳定输出。

## 是什么

**project-mastermind** 帮助项目经理/产品经理等专业人士初步了解项目目标、需求、成员类型的情况下，快速制作项目计划。在项目推进过程中快速了解进展。


## 核心原则

1. 专注内容：通过自动化排版和可视化（Markdown 甘特图等），让 PM 专注于决策而非格式。
2. 渐进增强：不一上来就展示所有细节。先建立框架，再深入估算，最后分配资源。
3. 确定性输出：所有时间线和资源图表必须使用标准 Markdown (Mermaid) 渲染，确保在各种编辑器中可见。

## 安装说明

### 针对 Claude Code 用户

将skills文件复制到你的 Claude Code skills目录中：

```bash
# Create the skill directory
mkdir -p ~/.claude/skills/project-mastermind

# Copy all files (or clone this repo directly)
cp SKILL.md  ~/.claude/skills/project-mastermind/
```

Or clone directly:

```bash
git clone https://github.com/wufang7788-a11y/project-mastermind.git ~/.claude/skills/project-mastermind
```

然后在 Claude Code 中输入 /project-mastermind 即可使用。

## 使用说明

```
/project-mastermind

> "我想要生成一个关于***的项目计划"
```

The skill will:
我理解您想要使用项目管理助手。让我先确认您的需求模式。
1. 请问您需要执行哪种操作？ (项目规划，估算，资源分配，项目进度报告/增强)
2. 为创建完整的项目计划，需求收集以下信息 (project_type, project_objectives, industry, project_requirements, team_members, budget(可选)
3. 保存当前计划（将完整计划导出为markdown文件）
4. 保存路径选择


## 结构

 `SKILL.md` 是一张简明地图（约 100 行），辅助文件仅在需要时按需加载。

| Phase | Purpose | Loaded When |
|------|---------|-------------|
| `Phase0` | 获取用户意图 | 一直执行 |
| `Phase1` | 创建项目计划 | Phase 1 |
| `Phase2` | 成本估算 | Phase 2 |
| `Phase3` | 资源分配 | Phase 3 |
| `Phase4` | 创建进度报告 | Phase 4 |
| `Mode E` | 增强现有文件 | 当用户提出该需求 |

This design follows [OpenAI's harness engineering](https://openai.com/index/harness-engineering/) principle: "give the agent a map, not a 1,000-page instruction manual."


### 项目甘特图查看图标方式
将```mermaid   ```里的内容复制到mermaindonline官网（https://www.mermaidonline.live/）  ，可以在线生成对应的图片使用。


## License

MIT — Use it, modify it, share it.


# 将markdown文件转换为HTML
为了方面对外展示，可以使用github下另一个skills，将markdown格式文件转换为HTML，效果还不错：frontend-slides。
Created by [@zarazhangrui](https://github.com/zarazhangrui) with Claude Code.

