# Cursor 安装与使用指南

## 1. Cursor 简介

Cursor 是一款集成 GPT-4 的 IDE 开发工具（部分用户表示可能基于 ChatGPT-3.5），能够根据用户需求自动生成代码，极大提升了开发效率和便捷性。

## 2. 下载 Windows 版本 Cursor

以下是 Windows 版本 Cursor 的下载链接：

- **网盘链接**：[https://pan.baidu.com/s/1Zsmu5dCbP-APwtmiSVBCpA](https://pan.baidu.com/s/1Zsmu5dCbP-APwtmiSVBCpA)  
- **提取码**：otum

## 3. 安装步骤

### 步骤 1：启动安装程序
双击下载的安装包，启动安装程序。

### 步骤 2：跳过 Copilot 连接
在安装界面中，选择“Skip connect Copilot”，然后点击“Continue”继续。

![跳过 Copilot 连接](https://bbtdd.com/img/4774293426834.webp)

### 步骤 3：配置 GitHub 连接
1. 点击右上角的齿轮按钮进入设置界面。  
2. 在弹出的窗口中，点击“Connect to GitHub”按钮。  
3. 记住生成的 Code，并点击链接跳转至 GitHub 登录页面。  
4. 输入 GitHub 账号密码登录。  

![配置 GitHub 连接](https://bbtdd.com/img/6631800286268507.webp)

### 步骤 4：完成安装
登录 GitHub 后，点击绿色按钮完成授权，最后点击“Done”完成安装。

## 4. Cursor 使用指南

### 功能 1：代码生成
按下 `Ctrl+K`，在弹出的窗口中输入需求，Cursor 将自动生成代码。例如，以下是生成的 AlexNet 模型代码：

python
import torch.nn as nn

class AlexNet(nn.Module):
    def __init__(self, num_classes=1000):
        super(AlexNet, self).__init__()
        self.features = nn.Sequential(
            nn.Conv2d(3, 64, kernel_size=11, stride=4, padding=2),
            nn.ReLU(inplace=True),
            nn.MaxPool2d(kernel_size=3, stride=2),
            nn.Conv2d(64, 192, kernel_size=5, padding=2),
            nn.ReLU(inplace=True),
            nn.MaxPool2d(kernel_size=3, stride=2),
            nn.Conv2d(192, 384, kernel_size=3, padding=1),
            nn.ReLU(inplace=True),
            nn.Conv2d(384, 256, kernel_size=3, padding=1),
            nn.ReLU(inplace=True),
            nn.Conv2d(256, 256, kernel_size=3, padding=1),
            nn.ReLU(inplace=True),
            nn.MaxPool2d(kernel_size=3, stride=2),
        )
        self.avgpool = nn.AdaptiveAvgPool2d((6, 6))
        self.classifier = nn.Sequential(
            nn.Dropout(),
            nn.Linear(256 * 6 * 6, 4096),
            nn.ReLU(inplace=True),
            nn.Dropout(),
            nn.Linear(4096, 4096),
            nn.ReLU(inplace=True),
            nn.Linear(4096, num_classes),
        )

    def forward(self, x):
        x = self.features(x)
        x = self.avgpool(x)
        x = x.view(x.size(0), 256 * 6 * 6)
        x = self.classifier(x)
        return x


### 功能 2：代码解释
按下 `Ctrl+L`，输入代码段，Cursor 将提供代码的解释（目前为英文）。

![代码解释功能](https://bbtdd.com/img/02244391084.webp)

---

👉 [WildCard | 一分钟注册，轻松订阅海外线上服务](https://bbtdd.com/WildCard)  

Cursor 作为一款功能强大的 IDE 工具，值得每一位开发者尝试，提升您的开发效率！