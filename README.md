# ArkTS Grammar Standards

> 面向 HarmonyOS / OpenHarmony 开发的 AI 编程技能包 —— ArkTS 语法规范

在编写或修改 `.ets` 文件时自动激活，确保代码严格遵守 ArkTS 语法规范，防止使用 `any`、`as` 类型断言、模板字符串等受限语法。适用于 Claude Code、DevEco Code、Cursor、GitHub Copilot、Windsurf 等 AI 编程工具。

## 核心规则

- 不使用 `any` 或 `unknown`（除非用户明确允许）
- 不使用 `as` 类型断言，改用显式类型、构造函数或类型辅助函数
- 不依赖结构化类型，优先使用命名类和接口
- 不使用 `obj[key]` 动态属性访问
- 对象字面量必须提供显式类型上下文
- 不使用内联对象字面量类型，须定义命名接口或类
- 不使用模板字符串 `` `${value}` ``，改用字符串拼接
- 避免解构声明、函数表达式、`delete`、`in`、`for...in` 等受限语法

## 参考文档

| 文件 | 用途 |
|------|------|
| `references/basic-syntax.md` | ArkTS 正常编写模式与推荐语法 |
| `references/restrictions.md` | 禁止的语法、受限运算符、对象字面量规则、Sendable |
| `references/ts-diff.md` | TypeScript 到 ArkTS 的差异与迁移指南 |
| `references/topic-aliases.json` | 主题别名映射 |

## 安装

### Claude Code / DevEco Code

```bash
npx skills add xiegen2020/arkts-grammar-standards
```

或手动复制到技能目录：

```bash
# Claude Code
cp -r arkts-grammar-standards ~/.claude/skills/

# DevEco Code
cp -r arkts-grammar-standards ~/.config/deveco/skills/
```

### Cursor

将 `SKILL.md` 内容复制到项目的 `.cursor/rules/arkts-grammar-standards.mdc` 文件中。

### 其他工具

将 `SKILL.md` 放入对应工具的技能/规则配置目录即可。

## 目录结构

```
arkts-grammar-standards/
├── SKILL.md                     # 技能主文件（AI 工具自动加载）
├── README.md
└── references/
    ├── basic-syntax.md          # ArkTS 基本语法指南
    ├── restrictions.md          # 语法限制与禁止项
    ├── ts-diff.md               # TypeScript → ArkTS 差异
    └── topic-aliases.json       # 主题别名映射
```

## 来源

本技能提取自 [DevEco Code](https://gitcode.com/openharmony-sig/deveco-code) 开源项目（MIT 协议），由华为官方内置的 HarmonyOS 开发技能包。

## 相关技能

- [arkts-error-fixes](https://github.com/xiegen2020/arkts-error-fixes) — 编译错误修复
- [arkts-runtime-fix](https://github.com/xiegen2020/arkts-runtime-fix) — 运行时崩溃诊断
- [arkui-knowledge](https://github.com/xiegen2020/arkui-knowledge) — ArkUI 组件知识库
- [deveco-create-project](https://github.com/xiegen2020/deveco-create-project) — 项目脚手架

## License

MIT
