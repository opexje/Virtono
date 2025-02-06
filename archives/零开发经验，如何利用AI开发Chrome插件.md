# 零开发经验，如何利用AI开发Chrome插件

🧑🏻‍💻

**TL;DR:** 通过AI技术，我成功开发了一款Chrome插件，实现了在浏览器中直接记笔记并同步至Obsidian的功能。本文将分享整个过程，并介绍使用的工具和经验。

## 1. 发现需求

在梳理自己的知识管理系统时，我发现从印象笔记时代起，我习惯将笔记剪藏到软件中，**但剪辑后很少再去阅读和消化**。稍后读软件（如简悦、cubox、readwise）的渐进式阅读模式虽适合划线+笔记，却不适合卡片笔记。

**稍后读软件的问题：**
1. **样式问题：** 原文样式可能丢失，抓取后渲染的样式在某些网站上显得难看。
2. **不适合卡片笔记：** 划线+笔记模式，不太适合“用自己的话”写卡片。
3. **与Obsidian联动麻烦：** Cubox有自定义动作可保存划线到Obsidian，但步骤繁琐。

**于是，我开始思考：为什么不能在浏览器中看文章时直接写笔记？**

## 2. 用Google和GPT寻找解决方案

要在浏览器中直接写笔记，方法有很多：
1. 开两个软件分屏，如Chrome+备忘录/Obsidian/Drafts。
2. 使用支持分屏的浏览器，搭配在线笔记，如Arc+flomo。
3. 使用Chrome插件分屏，搭配在线笔记，如Anything Copilot插件+flomo。

由于我的主力笔记软件是Obsidian，我尝试寻找现成的note to Obsidian的Chrome插件。用Google搜索后发现，现有的Obsidian插件主要用于剪辑网页并保存到Obsidian，这与我的卡片笔记思路不符。但我发现了一个本地API项目（[coddingtonbear/obsidian-local-rest-api](https://github.com/coddingtonbear/obsidian-local-rest-api)），其接口刚好符合我的需求。

## 3. 使用AI编写插件代码

### 3.1 使用GPT-4完成0.1版本
我没有纠结于Prompt结构，直接开始提问。GPT提供了Chrome插件的项目结构及各文件内容，我按照提示在本地创建目录，使用VSCode进行开发。

以下GPT回复内容省略。

### 3.2 使用GPT和Claude的经验
**联网能力：** GPT有联网能力，可读取第三方文档作为代码参考。而Claude暂时没有联网能力，我使用[r.jina.ai](https://r.jina.ai/)获取LLM更易读取的格式，手动贴给Claude。

**编程能力：** Claude的代码出错较少，输出简洁，直接指出需要修改的部分。GPT则偏好输出全部代码，即使Prompt中强调只输出修改部分，也常超出Token限制，导致代码混乱。

**提供清晰的范例：** 由于AI模型的时效性跟不上第三方库的迭代速度，我会提供官方文档和示例代码，或提供产品原型及界面截图，帮助AI更精确地编写代码。

**关于使用Claude的建议：**
1. 使用IP干净的代理，可通过[whoer.net/zh](https://whoer.net/zh)检查IP地址和DNS地址。
2. 每次登录尽量使用同一地区的节点。
3. 避免使用Gmail和微软邮箱，推荐使用小众邮箱。
4. Claude的使用限制可通过多个账号、浏览器和节点解决，高频用户可考虑付费。

**关于付费方式：**
👉 [WildCard | 一分钟注册，轻松订阅海外线上服务](https://bbtdd.com/WildCard)

## 4. 测试和修改程序

AI写的代码常有bug，需不断调试。调试时，尽量将Chrome控制台输出的log、页面点击效果的反馈告诉AI，就像QA提bug一样，**清楚地描述环境、操作步骤、结果、期望结果，并提供截图**。

## 5. 发布插件到Github（非必须）

开发完成后，我选择将插件分享到Github。如果想发布到Chrome扩展市场，需花$5注册开发者账号，可使用[WildCard](https://bbtdd.com/WildCard)付费。若不想付费，用户可打开Chrome扩展程序的开发者模式，直接加载解压好的插件。

**学会使用git和Github：** 有了AI的加持，可以直接让AI教我们如何使用git和Github。例如，使用以下Prompt：

我有一个Chrome插件开发好了，我想把它发布到Github上该如何操作，一步一步教我。


**让AI帮忙改写readme：** 先写中文版的readme，让GPT帮忙改写成中英双语。若想支持更多语种，可创建不同语言的readme文件。

## 6. 发布到Chrome扩展商店

在刷即刻时，我发现了一篇详细的教程，介绍了如何将插件发布到Chrome扩展商店。审核资料时，关于插件权限的说明可用中文写，再用GPT润色成英文，方便审核人员阅读。隐私声明可通过Claude生成文案，修改名称和联系方式后，发布到Github并用Vercel绑定域名。

**关于提审的经验：**
- 审核资料：中文撰写插件权限说明，用GPT润色成英文。
- 隐私声明：Claude生成文案，修改后发布到Github。
- 审核时间：Chrome审核较快，通常2个工作日完成。

## 7. 最后

通过这个项目，我不仅掌握了Chrome插件的开发流程，还体验到了利用AI工具简化开发的乐趣。如果你对这个插件感兴趣，欢迎访问以下链接下载使用：

📎

**Chrome商店版本：** [Simple Obsidian Note](https://chromewebstore.google.com/detail/simple-obsidian-note-exte/flohnmomnafamkgbjonnjcjggkhiokkn)  
**Github地址：** [moyuguy/sidenote2obsidian](https://github.com/moyuguy/sidenote2obsidian)