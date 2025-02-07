# PyCharm 本地接入 DeepSeek R1 实现 AI 编程

大家好，欢迎来到本期的技术分享！今天我们将探讨如何使用 PyCharm 接入 DeepSeek R1，轻松实现 AI 编程。无论你是编程新手还是经验丰富的开发者，这篇教程都能帮助你快速上手。让我们开始吧！

## 为什么要在本地搭建 DeepSeek R1 模型？

在开始搭建之前，我们先了解一下本地搭建 DeepSeek R1 模型的好处，以帮助你更好地理解这一过程的价值。

1. **高效学习与知识库管理**  
   在本地搭建大模型不仅方便管理个人知识库，还能显著提升编程学习效率。无论你学习 Python、Java 还是其他编程语言，DeepSeek R1 都能成为你的得力助手。

2. **零成本搭建**  
   DeepSeek 最近开源了推理模型 R1，完全免费且性能强劲。我们使用的 Python 开发环境是 PyCharm 社区版，同样免费。此外，CodeGPT 插件也是免费的，UI 设计简洁美观，使用体验极佳。总的来说，本次搭建无需额外成本！

3. **低配置也能流畅运行**  
   考虑到大多数用户的电脑配置，我们对搭建方法进行了优化，尽可能降低了硬件要求。即使是普通电脑，也能流畅运行 DeepSeek R1，无需担心卡顿问题。

## 框架选择

本次搭建的框架组合为：DeepSeek - r1:1.5b + PyCharm 专业版 + CodeGPT 插件。  
DeepSeek - r1 共有 7 个不同版本，随着参数尺寸增大，对电脑的要求也会提高。对于没有大显存 GPU 的用户，强烈推荐安装 1.5b 版本。该版本在普通电脑上也能流畅运行，响应时间仅为 1-2 秒。此外，DeepSeek - r1 在小尺寸模型上的回答质量也非常出色。

![DeepSeek R1 示例](https://bbtdd.com/wp-content/uploads/img/967109079686.webp)

接下来，我们将进入具体的搭建步骤！

## 详细搭建步骤

为了让初学者也能顺利复现，以下步骤将尽可能详细。

### 安装 PyCharm

下载 PyCharm 后，按照默认设置进行安装即可，这里不再赘述。

### 下载 Ollama

安装 deepseek - r1:1.5b，执行以下命令：  
`ollama pull deepseek - r1:1.5b`  

完成下载后，打开软件并输入 `ollama list`，查看当前安装的本地大模型。

![Ollama 示例](https://bbtdd.com/wp-content/uploads/img/6831539449.webp)

### 接入 PyCharm

首先下载 CodeGPT 插件。打开 PyCharm，依次点击“文件(File)”-“设置(Settings)”-“插件(Plugins)”，搜索并安装 CodeGPT。

![CodeGPT 安装示例](https://bbtdd.com/wp-content/uploads/img/6203650224698.webp)

安装完成后，在“工具(Tools)”下找到 CodeGPT，点击“Providers”，选择 Ollama(Local)，然后选择刚刚安装的 deepseek - r1:1.5b，点击“OK”即可完成配置。

![CodeGPT 配置示例](https://bbtdd.com/wp-content/uploads/img/93546869310.webp)

现在，你可以在 PyCharm 中直接与 DeepSeek - r1 对话，加速编程学习！左侧是代码编辑界面，右侧是 r1 大模型，省去了页面切换的麻烦。

![DeepSeek 回复示例](https://bbtdd.com/wp-content/uploads/img/50145245769.webp)

需要注意的是，CodeGPT 插件显示的 Token 数仅为统计，不会产生任何费用，因为使用的是本地算力，可以放心使用。

👉 [野卡 | 一分钟注册，轻松订阅海外线上服务](https://bbtdd.com/yeka)

## 总结

通过本教程，我们成功在本地运行了 DeepSeek R1 大模型，实现了免费且便捷的编程学习与知识管理。以下是本次搭建的关键点：

1. **选型推荐**  
   deepseek - r1:1.5b + PyCharm 社区版 + CodeGPT 插件，这一组合性价比极高，适合大多数用户。

2. **便捷交互**  
   在 PyCharm 右侧直接与 DeepSeek - R1 对话，快速辅助编程，提升学习与工作效率。

3. **快速响应**  
   几乎 1-2 秒的响应时间，完全本地运行，无额外费用，使用体验极佳。

希望这篇教程对你有所帮助，我们下次再见！