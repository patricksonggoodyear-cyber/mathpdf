# mathpdf

这是一个面向 AI 数学讨论的临时公开材料中转站。数学内容以 Markdown 为唯一维护源，GitHub Pages 自动生成目录和阅读页面。

## 分类与文件名

- A：代数
- C：组合
- N：数论

文件名采用「分类-日期-当日序号」格式，例如 **problems/A-20261022-01.md**。同一分类、同一天的序号依次递增。编号只用于临时区分文件，不代表永久归档。

每个文件只选择一个主要分类。首页会自动读取文件中的 **title** 与 **category**，按 A、C、N 分组；不需要手动修改首页。

## 新增一份材料

1. 打开仓库的 **problems** 文件夹。
2. 点击 **Add file → Create new file**。
3. 文件名填写 **problems/A-YYYYMMDD-01.md**，并按当天实际日期与序号修改。
4. 将下方模板和数学正文粘贴进去。
5. 点击 **Commit changes** 保存。
6. 等 GitHub Pages 完成本次部署，再打开网站首页确认条目出现。

    ---
    layout: default
    title: "这里填写题目大致描述"
    category: A
    ---

    ## 题目

    在这里粘贴题目文字。

    $$ 
    在这里粘贴 LaTeX 公式
    $$

    ## 证明或讨论

    在这里粘贴整理稿。

请使用标准 Markdown 与 LaTeX。行内公式推荐 $...$，独立公式推荐 $$...$$。如果题目必须依赖图形，请将图片也上传到仓库，并在 Markdown 中用相对路径引用。

## 给 AI 使用的链接

- 首页：<https://patricksonggoodyear-cyber.github.io/mathpdf/>
- 首页每个条目都提供两个链接：「网页」用于浏览，「AI 原文」直接指向对应 Markdown 源文件。
- 与 AI 讨论具体题目时，优先提供「AI 原文」链接；如果 AI 无法访问网址，再复制相关 Markdown 正文到对话中。

## 删除材料

打开对应的 Markdown 文件，在 GitHub 文件页面选择 **Delete this file**，然后提交删除。网站目录会在下一次 Pages 部署后自动更新。不需要再编辑首页。

请只上传适合公开访问的内容。当前方案不包含自动删除；删除前由你自行决定即可。
