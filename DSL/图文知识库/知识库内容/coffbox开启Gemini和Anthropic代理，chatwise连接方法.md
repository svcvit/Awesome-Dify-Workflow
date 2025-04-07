## coffbox开启Gemini和Anthropic代理，chatwise连接方法

今天升级了一下 [coffbox](https://one.coffbox.com/) One API 服务，开启了 Claude API 和 Gemini API 的代理服务。原始的 OpenAI-compatible 的方式访问照旧，如果使用代理服务，调用 gemini-2.0-flash-exp 的生图功能，可能会有更好的兼容性。对应 chatwise 客户端配置参考如下：

使用 `Gemini API` 的接口地址:


https://one.coffbox.com/gemini/v1beta  

[![](https://blog.vcvit.me/images/obsidian/Xnip2025-04-07_10-06-08.jpg)](https://blog.vcvit.me/images/obsidian/Xnip2025-04-07_10-06-08.jpg)

使用 `Claude API` 的接口地址:


https://one.coffbox.com/claude/v1  

[![](https://blog.vcvit.me/images/obsidian/Xnip2025-04-07_10-05-57.jpg)](https://blog.vcvit.me/images/obsidian/Xnip2025-04-07_10-05-57.jpg)

API Key 依旧和原来一样，当然，也只有 coffbox 开放的模型可以使用。