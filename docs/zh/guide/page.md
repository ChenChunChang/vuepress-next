# 页面

VuePress 是以 Markdown 为中心的。你项目中的每一个 Markdown 文件都是一个单独的页面。

## 页面路由

默认情况下，页面的路由路径是根据你的 Markdown 文件的相对路径决定的。

假设这是你的 Markdown 文件所处的目录结构：

```
└─ docs
   ├─ guide
   │  ├─ getting-started.md
   │  └─ README.md
   ├─ contributing.md
   └─ README.md
```

将 `docs` 目录作为你的 [sourceDir](../reference/cli.md) ，例如你在运行 `vuepress dev docs` 命令。此时，你的 Markdown 文件对应的路由路径为：

|      相对路径      |       路由路径        |
|--------------------|----------------------|
| `/README.md`       | `/`                  |
| `/contributing.md` | `/contributing.html` |
| `/guide/README.md` | `/guide/`            |
| `/guide/page.md`   | `/guide/page.html`   |

## Frontmatter

Markdown 文件可以包含一个 [YAML](https://yaml.org/) Frontmatter 。Frontmatter 必须在 Markdown 文件的顶部，并且被包裹在一对三短划线中间。下面是一个基本的示例：

```yaml
---
lang: zh-CN
title: 页面的标题
description: 页面的描述
---
```

你肯定注意到 Frontmatter 中的字段和[配置文件](./configuration.md#config-file)中的[站点配置](./configuration.md#站点配置)十分类似。你可以通过 Frontmatter 来覆盖当前页面的 `lang`, `title`, `description` 等属性。因此，你可以把 Frontmatter 当作页面级作用域的配置。

同样的，VuePress 有一些内置支持的 Frontmatter 字段，而你使用的主题也可能有它自己的特殊 Frontmatter 。

:::tip
前往 [Frontmatter 参考](../reference/config.md) 查看 VuePress 支持的 Frontmatter 配置。

前往 [默认主题参考](../reference/default-theme.md#frontmatter) 查看默认主题的 Frontmatter 配置。
:::