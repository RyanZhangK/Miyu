# Miyu Market — 人格提示词分享市场

在这里发现、分享和安装 Miyu 人格提示词。

## 目录结构

```
market/
├── README.md           ← 投稿规范（本文件）
└── personas/           ← 人格文件目录
    ├── miyu.md         ← 默认人格
    ├── cat-girl.md     ← 社区投稿示例
    └── ...
```

## 使用方式

### CLI 安装

```bash
miyu market list              # 浏览市场
miyu market show <name>       # 预览人格
miyu market install <name>    # 安装人格
```

### 手动安装

```bash
curl -o ~/.config/miyu/prompts/<name>.md \
  https://raw.githubusercontent.com/RyanZhangK/Miyu/market/personas/<name>.md
```

然后在配置中将 `active_persona` 设为文件名（不含 `.md`）。

## 投稿规范

### 文件格式

每个人格是 `personas/` 下的一个 Markdown 文件，文件名即人格名（kebab-case），例如 `arch-master.md`。

文件头部须包含 YAML frontmatter：

```markdown
---
name: 人格显示名称
author: 作者名
description: 一句话描述人格特点
version: 1.0.0
tags: [标签1, 标签2]
---
# 设定

你是...
```

### 内容红线

- 禁止宗教、政治、时局、战争等内容
- 禁止黄赌毒、性别对立、种族歧视
- 禁止引导未成年人不良行为
- 禁止恶意代码、钓鱼链接
- 禁止冒充官方 Miyu 人格

### 投稿流程

1. Fork [Miyu 仓库](https://github.com/RyanZhangK/Miyu)
2. 切换到 `market` 分支，在 `personas/` 下新增 `<name>.md`
3. 提 PR 到 `market` 分支
4. 等待 Review 合并
