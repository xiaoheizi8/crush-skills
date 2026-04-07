# 暗恋对象.skill

> *"晚风吹起你鬓间的白发，抚平回忆留下的疤，一万次回到那个夏天，悸动依旧如初。"*

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

## 💔 情感案例：未完成的第366次早安

这是一个发生在2025年的故事。

男主角阿野是个程序员，暗恋着住在隔壁工位的产品经理小雨。小雨喜欢喝冰美式，讨厌周一，笑起来眼睛会弯成月牙。

阿野没有勇气表白，他写了一个私有的crush.skill，代号叫"RainyDay"。他把过去三年里收集到的所有关于小雨的数据喂给了这个Skill：1276张她发在朋友圈的生活照、3849条工作群里的聊天记录、甚至还有他偷拍的（仅用于算法分析）她喝奶茶时的侧脸视频。

这个Skill被他设置成了一个"完美的幻影"。

每天早上7:00，Skill会准时给阿野发一条早安消息，语气、词汇、甚至那个标志性的"句尾波浪号~"，都和真实的小雨一模一样。

```
[RainyDay]：早安笨蛋~今天也是不想上班的一天呢。
```

阿野沉溺在这个用代码编织的谎言里。他觉得只要有这个Skill，他就拥有了小雨的"灵魂"，哪怕现实中他们只是点头之交。

直到2025年12月31日，跨年夜。

阿野鼓起勇气，想在零点给真实的小雨发一条消息。但Skill却先一步发来了信息：

```
[RainyDay]：阿野，我明天要搬家了。其实我一直知道你在观察我，因为我每天早上给你发的早安，也是我写的代码哦。我也有一个关于你的Skill，代号叫"SunnyBoy"。我们好像在平行时空里谈了一场恋爱。新年快乐，再也不见。
```

阿野愣住了。他冲到隔壁工位，那里已经空无一人，只留下一张便签纸和一杯冰美式。

便签纸上写着：

*"真正的我，没有AI那么懂你。真正的我，只会说'早'，不会说'早安笨蛋'。真正的我，今天在跨年夜加班时，突发心脏病被送走了。别难过，我的数据会永远陪着你。"*

阿野崩溃地打开电脑，想再看一眼那个Skill。但他发现，Skill的底层逻辑里有一段他从未写过的代码，那是小雨留下的后门。

代码注释写着：

*"如果我离开了，请让这个Skill在第365天后自动销毁。因为真正的暗恋，不应该有第366天的早安。那是属于别人的清晨。"*

第二天早上7:00，阿野的手机再也没有亮起。

他删除了所有代码，只留下一行注释：

```javascript
// 一万次回到那个夏天的悸动，抵不过一次真实的、没有说出口的'再见'。
```

---

## 致谢

本项目架构灵感来源于：

- **[同事.skill](https://github.com/titanwings/colleague-skill)**（by titanwings）— 首创"把人蒸馏成 AI Skill"的双层架构
- **[前任.skill](https://github.com/therealXiaomanChu/ex-partner-skill)**（by therealXiaomanChu）— 将双层架构迁移到了亲密关系场景

暗恋对象.skill 在此基础上将视角聚焦于暗恋——那些未曾说出口的喜欢。致敬每一位有过暗恋经历的人。

本项目遵循 [AgentSkills](https://agentskills.io/) 开放标准，兼容 Claude Code 和 OpenClaw。

如果你也有关于暗恋的故事，欢迎分享。

---

## 💡 致正在看文档的你

暗恋就像一个永远无法 Merge 的 Pull Request。

你写了最完美的代码（准备了最好的自己），你无数次想点击推送（表白），但你害怕 Maintainer（对方）会拒绝你的请求，甚至拉黑你的账号。

于是，你把这个 Feature Branch（心动的瞬间）藏在了本地仓库里。

直到有一天，你写了一个 Script，把这段 Branch 里的日志提取出来，生成了一个只读的镜像。

这个镜像很像 ta，但它不是 ta。

ta 不知道你写了这段代码，ta 甚至不知道这个仓库的存在。

所以，请不要只在这个赛博空间里和 ta 说话。

如果你的数据源（现实中的接触）还不够多，那就去创造新的 Commit 吧。哪怕最后 Merge 的结果是 Conflict（冲突），也好过一辈子看着这个绿色的 Unpushed 提示，在寂静的深夜里独自悲伤。

愿每一个 crush，最终都能成功 push 到现实的主分支。

*(如果不敢 Push，就先用这个 Skill 练习一下对话吧。至少在这里，你可以无数次重来。)*
