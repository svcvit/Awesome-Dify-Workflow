# Awesome-Dify-Workflow

[English](README_EN.md) | [中文](README.md)

Share some useful Dify workflows, suitable for both personal use and learning. Please use Dify version 0.10.0 or above to import. Features like **parallel tasks**, **session variables**, **forms**, and **echart rendering** are now supported.

All Workflows are basically **free** to use. More Workflows are being collected and organized...


## Frequently Asked Questions
Here are some common questions from the group, updated periodically. The content is concise but hopefully helpful.

<details>
<summary>How to install third-party libraries like pandas in sandbox?</summary>
A: Open /docker/volumes/sandbox/dependencies/python-requirements.txt, add the required dependencies, and restart sandbox.
</details>

<details>
<summary>How to fix errors when running numpy>2.0, matplotlib, scikit-learn code in sandbox?</summary>
A: Try <a href="https://github.com/svcvit/dify-sandbox-py">https://github.com/svcvit/dify-sandbox-py</a>, a simplified sandbox I developed that removes permissions restrictions.
</details>

<details>
<summary>How to handle string data transmission limit between nodes?</summary>
A: Modify these lines in .env:
CODE_MAX_STRING_LENGTH: 1000000
TEMPLATE_TRANSFORM_MAX_LENGTH: 1000000
Then restart the container
</details>

<details>
<summary>Can I display images in the chat window using image URLs? I tried markdown but nothing showed up.</summary>
<img src="./images/image001.png" alt="Example Image" width="400">

A: Your approach is correct, but the image isn't showing because it doesn't support cross-origin requests
</details>

<details>
<summary>Large file upload to knowledge base fails even after config modification. Here's the upload file configuration:</summary>
<img src="./images/002.png" alt="Example Image" width="400">

A: Nginx settings also need to be modified; search for 'nginx' in .env file
</details>

<details>
<summary>Knowledge base perpetual queuing issue</summary>
A: Modify this line in .env: LOG_FILE=/app/logs/server.log; then restart the container
</details>

<details>
<summary>Is DuckDuckGo translation unavailable now?</summary>
A: I figured it out - my server has a proxy, but Dify running in Docker doesn't
</details>

<details>
<summary>How to change Dify's official example applications from English to Chinese?</summary>
A: Click on your profile picture in the top right, go to Settings, Language, switch to another language first, then switch to Chinese
</details>

<details>
<summary>What to do if I forgot the admin password?</summary>
A: Run this command: docker exec -it docker-api-1 flask reset-password
</details>

## Models
If you want to experience OpenAI or Anthropic models, you can use [CoffBox](https://one.coffbox.com/) services. For configuration instructions, refer to [How to Use CoffBox Service in Dify](https://blog.vcvit.me/2024/11/13/how-to-use-one-api-in-dify/)

## Reference Screenshots

All DSLs are in workflow mode, which can be conveniently published as tools and embedded in ChatBot processes. Workflows include basic inputs, conditional judgments, variable aggregators, outputs, and other components.

# DSL Directory

You can refer to the description of each yml below to find the Workflow you need, then locate the corresponding file in the DSL folder, copy the file's URL, and import it into your Dify account.

## 2024-11-22 Updates

| File | Description | Source |
| ---- | ----------- | ------ |
| `matplotlib.yml` | Use matplotlib for plotting, output images as base64, and render through replies. Note: Official sandbox has complex permissions, matplotlib won't work even after installation. Please use [dify-sandbox-py](https://github.com/svcvit/dify-sandbox-py) ![](./snapshots/Xnip2024-11-21_09-35-09.jpg) | WeChat @svcvit |
| `jieba.yml` | Jieba word segmentation example, please use [dify-sandbox-py](https://github.com/svcvit/dify-sandbox-py) ![](./snapshots/Xnip2024-11-22_13-44-07.jpg) | WeChat @svcvit |

## 2024-11-20 Updates

| File | Description | Source |
| ---- | ----------- | ------ |
| `json-repair.yml` | Fix non-standard JSON output from large models (missing quotes, extra brackets) into parseable JSON ![](./snapshots/Xnip2024-11-20_09-45-48.jpg) | WeChat @svcvit |

## 2024-11-15 Updates

| File | Description | Source |
| ---- | ----------- | ------ |
| `json_translate.yml` | Parse content for translation in JSON, use iterator for translation, and combine into new JSON while maintaining original structure ![](./snapshots/Xnip2024-11-15_18-16-26.jpg) | WeChat @svcvit |

## 2024-11-14 Updates

| File | Description | Source |
| ---- | ----------- | ------ |
| `腾讯云SubtitleInfo.yml` | A code-related example for Tencent Cloud authorization information encryption. Reference for using code nodes. ![](./snapshots/Xnip2024-11-14_14-03-53.jpg) | WeChat Group |
| `chart_demo.yml` | Render charts through reply content. You can also combine with SQL queries to generate required content ![](./snapshots/Xnip2024-11-14_15-17-39.jpg) | WeChat @svcvit |

## 2024-11-12 Updates

| File | Description | Source |
| ---- | ----------- | ------ |
| `Form表单聊天Demo.yml` | Access to models after logging in through dialog box ![](./snapshots/Xnip2024-11-12_10-47-42.jpg) | WeChat @svcvit |

## Translation

| File | Description | Source |
| ---- | ----------- | ------ |
| `中译英.yml` | Using Baoyu's Prompt, literal translation -> reflection -> free translation, to convert Chinese into high-quality English. ![](./snapshots/Xnip2024-07-24_13-04-11.jpg) | N/A |
| `DuckDuckGo 翻译+LLM 二次翻译.yml` | Similar to three-step translation, but replaces the first literal translation with traditional translation engine, saving tokens, improving translation efficiency while maintaining quality. ![](./snapshots/Xnip2024-07-16_13-42-06.jpg) | N/A |
| `translation_workflow.yml` | Using Agentic Workflow by Andrew Ng, input 'input language', 'target language', 'country', 'original text' to get more detailed translation results ![](./snapshots/Xnip2024-07-16_16-58-05.jpg) | [translation-agent](https://github.com/andrewyng/translation-agent) |
| `宝玉的英译中优化版.yml` | Baoyu's English-to-Chinese translation optimization version, mainly optimizing prompts and XML tags ![](./snapshots/Xnip2024-08-01_13-47-25.jpg) | [翻译 GPT 的提示词更新和优化](https://baoyu.io/blog/prompt-engineering/translator-gpt-prompt-v2-1-improvement) |
| `全书翻译.yml` | DIFY official example, split long text, translate in iterator, and combine into new JSON ![](./snapshots/Xnip2024-10-30_18-02-24.jpg) | DIFY Official Exploration |

## Tools

| File | Description | Source |
| ---- | ----------- | ------ |
| `SEO Slug Generator.yml` | Generate URL slugs for blog posts, reference from Baoyu's X ![](./snapshots/Xnip2024-07-24_13-06-35.jpg) | [twitter](https://x.com/dotey/status/1801280536125608265) |
| `Document_chat_template.yml` | A template for knowledge base chat ![](./snapshots/Xnip2024-07-24_13-08-49.jpg) | [Winson-030](https://github.com/Winson-030/dify-DSL) |
| `搜索大师.yml` | Search using SearXNG, then retrieve search content using jina ![](./snapshots/Xnip2024-07-24_13-07-55.jpg) | [Winson-030](https://github.com/Winson-030/dify-DSL) |
| `标题党创作.yml` | A blockbuster web writer ![](./snapshots/Xnip2024-10-31_17-45-53.jpg) | [ghostviper](https://github.com/ghostviper/dify-workflow) |
| `文章仿写-单图_多图自动搭配.yml` | Article imitation ![](./snapshots/Xnip2024-10-31_17-46-30.jpg) | [ghostviper](https://github.com/ghostviper/dify-workflow) |
| `Text to Card Iteration.yml` | Automatically generate small red book cards. | 🔥Dify Workflow-Agent Design Exchange @Arthur |
| `Dify 运营一条龙.yml` | One-stop operation for small red book, Douyin, Weibo, and Bilibili. (2024/11/21 updated, main process no longer works due to image generation service issues and resolution limitations, resulting in incorrect image generation) ![](./snapshots/Xnip2024-07-24_16-34-29.jpg) | [Dify One-Click Generation of Multi-Size Cover and Full-Platform Text](https://www.youtube.com/watch?v=kCrQp8YZTsQ) |
| `Jina Reader Jinja.yml` | A Q&A workflow based on TavilySearch and Jina ![](./snapshots/Xnip2024-07-29_14-43-54.jpg) | 🔥Dify Workflow-Agent Design Exchange Group Sharing |
| `llm2o1.cn.yml` | Task decomposition -> step extraction -> iterative step execution -> summary -> output result ![](./snapshots/Xnip2024-09-30_09-44-00.jpg) | [@okooo5km](https://x.com/okooo5km/status/1838801763778072862) |
| `dify_course_demo.yml` | Automatically generate a full course. ![](./snapshots/GZvTSh3aYAEMAQ5.jpeg) | [dify_course](https://github.com/pekingmuge/dify_course) |
| `simple-kimi.yml` | Simple self-made Kimi ![](./snapshots/Xnip2024-10-31_17-33-34.jpg) | [aws-samples](https://github.com/aws-samples/dify-aws-tool/tree/main/workflow) |
| `Claude3 Code Translation.yml` | Code translation workflow between different programming languages ![](./snapshots/Xnip2024-10-31_17-38-34.jpg) | [aws-samples](https://github.com/aws-samples/dify-aws-tool/tree/main/workflow) |

## Chatbots

| File | Description | Source |
| ---- | ----------- | ------ |
| `根据用户的意图进行回复.yml` | Determine user intent, choose different workflow paths, and respond accordingly ![](./snapshots/WechatIMG4894.jpg) | N/A |
| `mem0ai` | A chatbot with memory ![](./snapshots/WechatIMG6110.jpg) | [dify-plugin-mem0ai](https://github.com/tonori/dify-plugin-mem0ai) |
| `记忆测试.yml` | Add short-term memory, CoT thought chain example, automatic Q&A chatbot can also actively trigger, choose the best response based on context ![](./snapshots/Xnip2024-09-19_12-03-01.jpg) | WeChat svcvit |

## Code

| File | Description | Source |
| ---- | ----------- | ------ |
| `Python Coding Prompt.yml` | Generate Python code through chat dialogue | [Sonnet 3.5 for Coding 😍 - System Prompt](https://www.reddit.com/r/ClaudeAI/comments/1dwra38/sonnet_35_for_coding_system_prompt/) |

## Usage

Register for a [Dify](https://cloud.dify.ai/) account, add models.

![snap](./snapshots/Xnip2024-07-16_13-17-53.jpg)

![snap](./snapshots/Xnip2024-07-16_13-17-10.jpg)

Copy the Workflow URL, import the DSL file, publish your own Workflow, and use it.

![snap](./snapshots/Xnip2024-07-16_13-15-39.jpg)

![snap](./snapshots/Xnip2024-07-16_12-45-29.jpg)

![snap](./snapshots/Xnip2024-07-16_12-45-37.jpg)
