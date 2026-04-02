# 暗恋对象.skill

> *"一万次回到那个夏天的悸动。"*

**我会为了你一万次回到那个心动的瞬间。**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Python 3.9+](https://img.shields.io/badge/Python-3.9%2B-blue.svg)](https://python.org)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Skill-blueviolet)](https://claude.ai/code)
[![AgentSkills](https://img.shields.io/badge/AgentSkills-Standard-green)](https://agentskills.io)

&nbsp;

提供暗恋对象的原材料（聊天记录、照片、社交媒体）加上你的主观描述  
生成一个**真正像ta的 AI Skill**  
用ta的口头禅说话，用ta的方式回复你，记得你们之间的每一个心动的瞬间

⚠️ **本项目仅用于个人情感分析与回忆，不用于骚扰、跟踪或侵犯他人隐私。**

[安装](#安装) · [使用](#使用) · [效果示例](#效果示例)

---

## 安装

### Claude Code

> **重要**：Claude Code 从 **git 仓库根目录** 的 `.claude/skills/` 查找 skill。请在正确的位置执行。

```bash
# 安装到当前项目（在 git 仓库根目录执行）
mkdir -p .claude/skills
git clone https://github.com/xiaoheizi8/crush-skills .claude/skills/create-crush

# 或安装到全局（所有项目都能用）
git clone https://github.com/xiaoheizi8/crush-skills ~/.claude/skills/create-crush
```

### 依赖（可选）

```bash
pip3 install -r requirements.txt
```

---

## 使用

在 Claude Code 中输入：

* `/create-crush`
* "帮我创建一个暗恋对象 skill"
* "我想蒸馏一个暗恋的人"
* "给我做一个 XX 的 skill"

### 创建流程

1. **基础信息**：花名/代号 + 基本信息 + 性格画像（3个问题）
2. **原材料导入**：聊天记录、照片、社交媒体（可选）
3. **分析生成**：Relationship Memory + Persona
4. **对话测试**：像ta一样跟你聊天

### 管理命令

| 命令 | 说明 |
|------|------|
| `/list-crushes` | 列出所有暗恋对象 |
| `/{slug}` | 和ta聊天 |
| `/{slug}-memory` | 回忆模式 |
| `/{slug}-persona` | 性格模式 |
| `/delete-crush {slug}` | 删除 |

---

## 效果示例

### 创建时

```
用户：帮我创建一个暗恋对象的skill

我：先给ta起个代号吧。不需要真名，昵称、备注名、外号都行。
比如：小明 / 女神 / 那个人 / crush

用户：就叫ta小美吧

我：好的，一句话介绍一下？

用户：认识三个月了 还没表白 同事

我：最后，用一句话描述ta的性格？

用户：ENFP双子座 话很多 永远在社交 但偶尔会对视
```

### 对话时

```
用户：/xiaomei

小美：干嘛突然找我 有事吗

用户：没什么 就是想你了

小美：...少来这套 你是不是又闲了
    上班时间摸鱼啊你

用户：想约你吃饭

小美：看情况吧 最近有点忙
    你请我就考虑考虑😏
```

---

## 安全边界

1. **仅用于个人情感分析** — 不用于骚扰或侵犯隐私
2. **不主动联系真人** — 对话模拟不会替代真实沟通
3. **不鼓励纠缠** — 如有不健康执念，建议寻求专业帮助
4. **隐私保护** — 所有数据仅本地存储
5. **保持分寸感** — 朋友以上恋人未满的暧昧感

---

## 项目结构

```
crush/
├── SKILL.md                    # 主技能文件
├── prompts/
│   ├── intake.md              # 信息录入引导
│   ├── memory_builder.md     # 关系记忆模板
│   ├── memory_analyzer.md    # 关系记忆分析器
│   ├── persona_builder.md    # 人物性格模板
│   ├── persona_analyzer.md   # 性格行为分析器
│   ├── merger.md             # 增量合并逻辑
│   └── correction_handler.md # 对话纠正处理器
└── tools/
    ├── wechat_parser.py      # 微信聊天记录解析
    ├── qq_parser.py          # QQ聊天记录解析
    ├── social_parser.py      # 社交媒体内容解析
    ├── photo_analyzer.py    # 照片EXIF分析
    ├── version_manager.py   # 版本管理/回滚
    └── skill_writer.py      # Skill文件管理
```

---

## 致谢



本项目架构灵感来源于：

- **[同事.skill](https://github.com/titanwings/colleague-skill)**（by titanwings）— 首创"把人蒸馏成 AI Skill"的双层架构
- **[前任.skill](https://github.com/therealXiaomanChu/ex-partner-skill)**（by therealXiaomanChu）— 将双层架构迁移到了亲密关系场景

自己.skill 在此基础上将视角内转：对象不再是他人，而是你自己。致敬两位原作者的创意和开源精神。

本项目遵循 [AgentSkills](https://agentskills.io/) 开放标准，兼容 Claude Code 和 OpenClaw。

如果你也有关于暗恋的故事，欢迎分享。
