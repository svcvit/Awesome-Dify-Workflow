在大语言模型发展的这几年，因为工作原因，接触 DIFY 时间比较长一点点，总结一下自己的一些想法。包括选择什么样的模型，为什么众多应用层的开发工具/产品选择了 DIFY，DIFY 能做什么？

[](https://blog.vcvit.me/2025/03/14/how-to-use-dify/#%E5%85%B3%E4%BA%8E%E6%A8%A1%E5%9E%8B "关于模型")关于模型
-----------------------------------------------------------------------------------------------------

模型大体可以分为**文本模型**和**多模态模型**，我们以 OPENAI 的模型为例，gpt 3.5，gpt 4 这些都是文本模型。O1 是多模态模型。多模态常规意义上主要就是支持视觉的模型。但是 gemini 的多模态，其实还支持更多格式、包括视频、音频、pdf 等。选择合适的模型，对于整个 AI 流程影响巨大。例图，你想做一个从 PDF 提取文本的 AI 助手。

如果你只能用 qwen-VL 的视觉模型。那么你的方案路径是这样的：用 python 代码，写一个脚本，将 PDF 转换成一页页的图片，再将每个图片传给 qwen-VL 的模型进行识别，最后再将识别好的内容拼接起来。最终获得 PDF 提取到的文本内容。

[![](https://blog.vcvit.me/images/obsidian/Pasted%20image%2020250314143532.png)](https://blog.vcvit.me/images/obsidian/Pasted%20image%2020250314143532.png)

但是如果你用 Google 的 Gemini 2.0 Flash-Lite，它的多模态默认就支持文档。

[![](https://blog.vcvit.me/images/obsidian/Pasted%20image%2020250314143618.png)](https://blog.vcvit.me/images/obsidian/Pasted%20image%2020250314143618.png)

你就可以直接提交 pdf，即可完成解析，整个流程就会简化特别多。

[![](https://blog.vcvit.me/images/obsidian/Pasted%20image%2020250314143332.png)](https://blog.vcvit.me/images/obsidian/Pasted%20image%2020250314143332.png)

再加上每个公司对模型选择的要求，需要从合法、合规、价格等各方面考虑。模型的选择就会影响到后面的实现方案，包括最终效果，例如 gemini 识别手写文字，强于 qwen-VL，这些只有多试试效果，才能做决定。

[](https://blog.vcvit.me/2025/03/14/how-to-use-dify/#%E5%85%B3%E4%BA%8E%E5%B7%A5%E5%85%B7 "关于工具")关于工具
-----------------------------------------------------------------------------------------------------

现在做 AI 流程编排的工具很多，dify、fastgpt、maxkb、ragflow 等等，这里有篇挺新的文章推荐给大家阅读，[AI 流程平台对比——Dify、Fastgpt、Ragflow](https://zerozzz.win/ai-%E6%B5%81%E7%A8%8B%E5%B9%B3%E5%8F%B0%E5%AF%B9%E6%AF%94dify%E3%80%81fastgpt%E3%80%81ragflow) 。看完你会有自己的选择，这里少提了一个 maxkb，这是由 1panel 的公司推出的基于大模型和 RAG 的开源知识库问答系统。他们各自有各自的侧重点，你需要根据你自己的业务需求做选择。如果你还是不知道如何选，可以看看这些观点：

1.  [Ossinsight 的 LLM Tools 排名](https://ossinsight.io/collections/llm-tools/)，DIFY 是有压倒性的优势。  
    [![](https://blog.vcvit.me/images/obsidian/Pasted%20image%2020250314144930.png)](https://blog.vcvit.me/images/obsidian/Pasted%20image%2020250314144930.png)
    
2.  如果你是一个非开发者，只是希望用一些工具，完成一些特定场景的任务，例如：翻译、意图识别、根据不同条件编排流程、做一个聊天机器人嵌入自己的网站、或者和朋友分享你自己做的一个流程，你选任何工具都可以，你甚至可以都用用，体验这些产品，感受产品设计的差异。
    
3.  如果你是一个开发者，DIFY 的工程化设计比所有其他平台多很多，包括调试、性能追踪、1.0 开放的插件，你如果未来有更多自定义的需求，自己也会写一点点代码，DIFY 会有更多想象空间。如果你是一个开发者，你最终都绕不开 DIFY，你一定会用上的。
    

[](https://blog.vcvit.me/2025/03/14/how-to-use-dify/#%E4%B8%BA%E4%BB%80%E4%B9%88%E6%88%91%E7%94%A8-DIFY "为什么我用 DIFY")为什么我用 DIFY
-------------------------------------------------------------------------------------------------------------------------------

我在 24 年初开始接触 AI 流程编排相关工作，当时最主要的 2 个选项就是 DIFY 和 COZE，coze 中国版刚上线不久，只有网页版，API 还在内测中，也没有完全接入火山引擎，对于租户管理，都还在起步阶段，只支持字节系的云雀模型（后更名为豆包）、后来加入了 moonshoot，当然，这些特性与 COZE 的目标用户完全面向 C 端有关。后来字节花了几个月，才做完企业版的开发，接入火山引擎，一步步完善 coze 企业版。

同期，字节内部也有面向企业的 LLMOPS，我**个人感觉**就是借鉴了 DIFY 的 UI，再加上 coze 的流程编排画布，非开源，支持私有化部署。他们当时应该名字都还没想好，商业版部署报价 50 万起步，模型另外算钱，开发对接文档都还是在群里发 pdf 的方式进行，下面是 2024 年 4 月的一些截图，试用了一圈之后，果断放弃了字节。

[![](https://blog.vcvit.me/images/obsidian/Pasted%20image%2020250314150306.png)](https://blog.vcvit.me/images/obsidian/Pasted%20image%2020250314150306.png)  
[![](https://blog.vcvit.me/images/obsidian/Pasted%20image%2020250314150445.png)](https://blog.vcvit.me/images/obsidian/Pasted%20image%2020250314150445.png)

而当时的 DIFY 没有现在这么多的 star，但是已经是国内排第一的 workflow 编排平台了，加上社区版开源免费，模型自己想接哪家接哪家，不需要任何商务对接就可以用。于是，我们选择了 DIFY。

[](https://blog.vcvit.me/2025/03/14/how-to-use-dify/#DIFY-%E8%83%BD%E5%81%9A%E4%BB%80%E4%B9%88%EF%BC%9F "DIFY 能做什么？")DIFY 能做什么？
-------------------------------------------------------------------------------------------------------------------------------

这里我会尽可能用官方提供的示例，告诉大家 DIFY 能做什么，这些都可以在官方探索中找到。  
[![](https://blog.vcvit.me/images/obsidian/Pasted%20image%2020250314151937.png)](https://blog.vcvit.me/images/obsidian/Pasted%20image%2020250314151937.png)

### [](https://blog.vcvit.me/2025/03/14/how-to-use-dify/#%E7%9B%B4%E8%AF%91-%E5%8F%8D%E6%80%9D-%E6%84%8F%E8%AF%91%E7%BF%BB%E8%AF%91%E5%8A%A9%E6%89%8B "直译 +反思+意译翻译助手")直译 +反思+意译翻译助手

这个方案的来源在这里[直译、反思、意译：提升 GPT 翻译质量的一种新策略](https://baoyu.io/blog/prompt-engineering/translator-gpt-prompt-v2)  
[![](https://blog.vcvit.me/images/obsidian/Pasted%20image%2020250314154703.png)](https://blog.vcvit.me/images/obsidian/Pasted%20image%2020250314154703.png)

### [](https://blog.vcvit.me/2025/03/14/how-to-use-dify/#%E5%AE%9E%E6%97%B6%E6%90%9C%E7%B4%A2%E7%9A%84%E8%81%8A%E5%A4%A9%E6%9C%BA%E5%99%A8%E4%BA%BA "实时搜索的聊天机器人")实时搜索的聊天机器人

[![](https://blog.vcvit.me/images/obsidian/Pasted%20image%2020250314154721.png)](https://blog.vcvit.me/images/obsidian/Pasted%20image%2020250314154721.png)

### [](https://blog.vcvit.me/2025/03/14/how-to-use-dify/#%E9%82%AE%E4%BB%B6%E5%9B%9E%E5%A4%8D%E5%8A%A9%E6%89%8B "邮件回复助手")邮件回复助手

[![](https://blog.vcvit.me/images/obsidian/Pasted%20image%2020250314155046.png)](https://blog.vcvit.me/images/obsidian/Pasted%20image%2020250314155046.png)

[](https://blog.vcvit.me/2025/03/14/how-to-use-dify/#%E6%BC%94%E7%A4%BA "演示")演示
-------------------------------------------------------------------------------

*   如何安装 DIFY，或者是用云端版本
    
*   Dify 1.0 的重大更新有哪些
    
*   Workflow 和 chatflow 有什么区别
    
*   DIFY 每个节点，有什么作用，可以如何使用
    
*   我为什么做了 dify-sandbox-py，什么时候会用到？