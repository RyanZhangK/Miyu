# Miyu Market — 人格 & 角色分享市场

在这里发现、分享和安装 Miyu 的提示词人格（Persona）与用户身份（Identity）。

## 人格 vs 角色

| | 人格 (Persona) | 角色/身份 (Identity) |
| --- | --- | --- |
| 定义 | AI 助手的系统提示词 | 用户的身份档案 |
| 效果 | 改变 Miyu 的性格、语气、行为 | 告诉 Miyu 你是谁、你的偏好 |
| 安装到 | `~/.config/miyu/prompts/` | `~/.config/miyu/identities/` |
| 激活方式 | 设 `active_persona` | 设 `active_identity` |

## 目录结构

```
market/
├── README.md             ← 投稿规范（本文件）
├── personas/             ← 人格文件
│   ├── miyu.md           ← 默认 Miyu 人格
│   ├── cat-girl.md       ← 猫娘人格
│   └── ...
└── identities/           ← 角色文件
    ├── developer.md      ← 开发者身份
    └── ...
```

## 使用方式

### CLI 安装

```bash
miyu market list personas              # 列出所有人格
miyu market list identities            # 列出所有角色
miyu market show persona <name>        # 预览人格
miyu market install persona <name>     # 安装人格
miyu market install identity <name>    # 安装角色
miyu market update personas            # 更新已安装人格
```

### 手动安装

```bash
# 安装人格
curl -o ~/.config/miyu/prompts/<name>.md \
  https://raw.githubusercontent.com/RyanZhangK/Miyu/market/personas/<name>.md

# 安装角色
curl -o ~/.config/miyu/identities/<name>.md \
  https://raw.githubusercontent.com/RyanZhangK/Miyu/market/identities/<name>.md
```

## 投稿规范

### 文件格式

每个人格/角色是一个 Markdown 文件，放在对应的 `personas/` 或 `identities/` 目录下。文件名即名称（kebab-case）。

文件头部须包含 YAML frontmatter：

```markdown
---
name: 显示名称
author: 作者名
description: 一句话描述
version: 1.0.0
tags: [标签1, 标签2]
---
# 设定 / 用户身份

...
```

### 内容红线

- 禁止宗教、政治、时局、战争等内容
- 禁止黄赌毒、性别对立、种族歧视
- 禁止引导未成年人不良行为
- 禁止恶意代码、钓鱼链接
- 禁止冒充官方 Miyu 人格

### 投稿流程

1. Fork [Miyu 仓库](https://github.com/RyanZhangK/Miyu)
2. 切换到 `market` 分支，在 `personas/` 或 `identities/` 下新增 `<name>.md`
3. 提 PR 到 `market` 分支
4. 等待 Review 合并
