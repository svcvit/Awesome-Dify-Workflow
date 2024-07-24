# Awesome-Dify-Workflow

<p align="center">
  <a href="./README_EN.md"><img alt="README in English" src="https://img.shields.io/badge/English-d9d9d9"></a>
  <a href="./README.md"><img alt="简体中文版自述文件" src="https://img.shields.io/badge/简体中文-d9d9d9"></a>
</p>

分享一些好用的 Dify 工作流程，自用、学习两相宜，请使用 Dify 0.6.14 及以上版本导入。

所有的 Workflow 基本都可以 **免费** 使用，不需要对接第三方平台 API，模型使用 Deepseek，主要是因为便宜，注册即送 500 万 Token。

更多 Workflow 收集整理中……

## 参考截图

所有 DSL 都为工作流模式，可以方便的发布为工具后，嵌入 ChatBot 流程。工作流会包含基础的输入、条件判断、变量聚合器、输出等内容。

# DSL 目录

你可以参考下面每个 yml 的描述，找到你需要的 Workflow，然后在 DSL 文件夹中找到对应的文件，复制文件的 URL，导入自己的 Dify 账号即可。

## 翻译

| 文件 <div style="width:50px">                            | 描述                                                                                                                          | 来源                                                                |
| -------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `中译英.yml`                 | 通过宝玉的 Prompt，直译->反思->意译，将中文翻译成高质量的英文。 ![](./snapshots/Xnip2024-07-24_13-04-11.jpg)                                                                  | 暂无                                                                |
| `DuckDuckGo 翻译+LLM 二次翻译.yml` | 与三步翻译类似，但是把第一步的直译变成传统翻译引擎翻译，节省 Token，提高翻译效率，同时提高翻译质量。   ![](./snapshots/Xnip2024-07-16_13-42-06.jpg)                        | 暂无                                                                |
| `translation_workflow.yml`         | 使用吴恩达提出 Agentic Workflow 制作的翻译工具，录入`输入语言`、`目标语言`、`国家`、`原始文本` 4 个参数，提供更细致的翻译结果 ![snap](./snapshots/Xnip2024-07-16_16-58-05.jpg) | [translation-agent](https://github.com/andrewyng/translation-agent) |

## 工具

| 文件 <div style="width:50px">     | 描述                                            | 来源                                                      |
| -------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `SEO Slug Generator.yml`     | 给自己的博文生成 url slug，参考来源于宝玉的 X  ![](./snapshots/Xnip2024-07-24_13-06-35.jpg) | [twitter](https://x.com/dotey/status/1801280536125608265) |
| `Document_chat_template.yml` | 一个通过知识库聊天的模版  ![](./snapshots/Xnip2024-07-24_13-08-49.jpg)                      | [Winson-030](https://github.com/Winson-030/dify-DSL)      |
| `搜索大师.yml`               | 通过 SearXNG 进行搜索，再通过 jina 获取搜索内容 ![](./snapshots/Xnip2024-07-24_13-07-55.jpg)| [Winson-030](https://github.com/Winson-030/dify-DSL)      |
| `标题党创作.yml`               | 一位爆款网文作家 | [ghostviper](https://github.com/ghostviper/dify-workflow)      |
| `文章仿写-单图_多图自动搭配.yml`       | 文章仿写 | [ghostviper](https://github.com/ghostviper/dify-workflow)      |
| `Text to Card Iteration.yml`       | 自动生成小红书这种卡片。 | 🔥Dify Workflow-Agent 设计交流  @Arthur     |

## 聊天机器人

| 文件  <div style="width:50px">    | 描述                                            | 来源                                                      |
| -------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `根据用户的意图进行回复.yml`     | 根据用户的聊天内容，进行意图判定，根据意图选择不同的工作流路径进行回复，再风格化聊天机器人话术 ![](./snapshots/WechatIMG4894.jpg)  | 无 |
| `mem0ai`     | 一个有记忆的聊天流程，完整代码见来源链接 ![mem0ai](./snapshots/WechatIMG6110.jpg)  | [dify-plugin-mem0ai](https://github.com/tonori/dify-plugin-mem0ai) |

## 代码

| 文件  <div style="width:50px">   | 描述                             | 来源                                                                                                                               |
| -------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `Python Coding Prompt.yml` | 通过聊天对话方式生成 Python 代码 | [Sonnet 3.5 for Coding 😍 - System Prompt](https://www.reddit.com/r/ClaudeAI/comments/1dwra38/sonnet_35_for_coding_system_prompt/) |

# 使用方法

注册 [Dify](https://cloud.dify.ai/) 账号，添加 Deepseek 模型。

![snap](./snapshots/Xnip2024-07-16_13-17-53.jpg)

![snap](./snapshots/Xnip2024-07-16_13-17-10.jpg)

复制 Workflow 的 URL，导入 DLS 文件即可，发布你自己的 Workflow，既可以使用。当然，你可以进行必要的调整，例如模版的调整，或提示词的调整。

![snap](./snapshots/Xnip2024-07-16_13-15-39.jpg)

![snap](./snapshots/Xnip2024-07-16_12-45-29.jpg)

![snap](./snapshots/Xnip2024-07-16_12-45-37.jpg)
