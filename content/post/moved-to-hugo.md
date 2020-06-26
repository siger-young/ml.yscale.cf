---
title: "博客从 Typecho 搬迁至 Hugo"
date: 2020-05-30T22:37:13+08:00
draft: false
categories:
- default
---
使用了早有耳闻的 Hugo，但是遇到了不少坑，下面总结一下
<!--more-->
* 数学公式

    Hugo 新采用的 Markdown 解析器 Goldmark 对 LaTeX 中的一些特殊字符不能正确处理，几种解决方法：

    - 在 front-matter 处添加 `markup: mmark` 强制使用 mmark 作为解析器，代价是无法生成 TOC 目录
    - 使用 shortcode 来对 LaTeX 部分转义，如 Minimo 主题中就添加了 `<katex></katex>` 的 shortcode
    - （被采用的）Goldmark 官方已经有 `goldmark-mathjax` 的扩展，其能够正确处理 LaTeX 部分，因此只需要向 Hugo 源代码中添加该扩展，并手动编译即可

    可以参照 [修复 Hugo 对 LaTeX 与 Markdown 转义字符冲突的问题](https://cs.yscale.cf/2020/05/29/hugo-fix-markup-math/).

* TOC 目录层级

    之前用了一款主题，会自动展开目录层级，但是始终对不上号，发现 Hugo 返回的目录不完整，少了某些层级，需要在 `config.toml` 中加入

    ```toml
    [markup]
        [markup.tableOfContents]
            startLevel = 1
            endLevel = 6
    ```

    之后看了一下源代码，发现了默认的配置

    ```go
    var DefaultConfig = Config{
        StartLevel: 2,
        EndLevel:   3,
        Ordered:    false,
    }
    ```

    我感觉默认配置这样写总归有点问题，会给用户带来一种很奇怪的体验……

* 一部分主题的 shortcode 无法使用

    Even 主题有一个网易云音乐部件的 shortcode，不过直接使用的话是看不到效果的，在 Hugo 某个版本中针对安全加入了一个选项，默认行为会过滤一部分 HTML tag. 而该主题使用的网易云音乐部件的 shortcode 含有 `iframe` 标签，就被过滤掉了. 在查看渲染后的 HTML 内容可以发现 `<!-- raw HTML omitted -->` 的字样，需要在 `config.toml` 加入如下选项.

    ```toml
    [markup]
        [markup.goldmark]
            [markup.goldmark.renderer]
                unsafe = true
    ```
* 更改主题 SASS / SCSS 不生效

    原因在于 Hugo 还有一个扩展版，扩展版能够编译 SASS / SCSS，可以在官方仓库的 [releases](https://github.com/gohugoio/hugo/releases) 处看到. AUR 里面反正没找到……

    然后问题回来了，如果还要解决公式问题的话，手动编译需要加上一个 tag，使得编译出来的为 Extended 版，可以参照 [修复 Hugo 对 LaTeX 与 Markdown 转义字符冲突的问题](https://cs.yscale.cf/2020/05/29/hugo-fix-markup-math/) 文章尾部的更新.