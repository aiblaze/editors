# Cursor Notepads Collection

这是一个用于分享 Cursor Notepads 常用模板和最佳实践的集合。

Cursor Notepads 是一个强大的上下文共享工具，可以在 Composer 和 Chat 交互之间建立桥梁。

## 什么是 Cursor Notepads？

Cursor Notepads 是一个增强的参考文档工具，它超越了 `.cursorrules` 的功能，允许你为开发工作流创建可重用的上下文。它可以：

- 在不同开发环境部分之间共享上下文
- 使用 `@` 语法引用
- 支持文件附件
- 作为各种开发场景的动态模板

## 目录结构

```
.
├── templates/          # 通用模板集合
│   ├── api/           # API 开发相关模板
│   ├── frontend/      # 前端开发相关模板
│   └── backend/       # 后端开发相关模板
├── best-practices/    # 最佳实践指南
└── examples/         # 示例集合
```

## 使用指南

1. 在 Cursor 中点击 Notepads 部分的 "+" 按钮
2. 为你的 notepad 指定一个有意义的名称
3. 添加内容、上下文、文件和其他相关信息
4. 在 composers 或 chat 中使用 `@` 引用

## 最佳实践

### 适合写入 Notepads 的内容

- 项目架构决策
- 开发指南和标准
- 可重用代码模板
- 需要频繁引用的文档
- 团队特定的约定和规则

### 不适合写入 Notepads 的内容

- 临时笔记或草稿
- 属于版本控制的信息（如 git）
- 敏感数据或凭证
- 频繁变化的信息

### 推荐格式

- 使用清晰的标题和章节
- 包含相关示例
- 保持内容重点突出且组织有序
- 使用 markdown 格式提高可读性
- 必要时添加相关文件附件

## 贡献指南

欢迎提交 Pull Request 来分享你的 Notepads 模板和最佳实践。在提交时，请确保：

1. 遵循现有的目录结构
2. 提供清晰的文档说明
3. 包含实际使用示例
4. 使用 markdown 格式

## 许可证

CC0 1.0 Universal

## 参考

- [Cursor Notepads 官方文档](https://docs.cursor.com/beta/notepads)

