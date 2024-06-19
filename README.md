# MatGPT


MatGPT 是一款 MATLAB 应用程序，可让您轻松访问 OpenAI 的 ChatGPT API。使用该应用程序，您可以加载特定用例的提示列表并轻松进行对话。如果您不熟悉 ChatGPT 和提示工程，MatGPT 是一种很好的学习方式。 

该应用程序仅充当 ChatGPT API 的接口。您应该熟悉与使用该技术以及 [OpenAI 条款和政策](https://openai.com/policies) 相关的限制和风险。您有责任支付 OpenAI 可能因使用其 API 而收取的任何费用。

MatGPT 已更新为在 MathWorks 维护的“[使用 MATLAB 的大型语言模型 (LLM)](https://github.com/matlab-deep-learning/llms-with-matlab/)”存储库的框架上运行。

[MATLAB AI Chat Playground](https://www.mathworks.com/matlabcentral/playground/) 是 MATLAB Central 上 MatGPT 的绝佳替代品。

## What's New

* MatGPT 在“LLMs with MATLAB”框架上运行，该框架需要 MATLAB R2023a 或更高版本。 
* MatGPT 支持流 API，其中响应令牌在传入时显示。
* MatGPT 检测提示中包含的 URL，并将其 Web 内容检索到聊天中。
* MatGPT 允许您将 .m、.mlx、.csv 或 .txt 文件导入聊天中。如果文本分析工具箱可用，也支持 PDF 文件。
* MatGPT 支持带有 Vision 的 GPT-4 Turbo。您可以将 URL 传递给图像，或者本地图像文件路径询问有关图像的问题。
* MatGPT 允许您通过 DALL·E 3 API 生成图像。 
* MatGPT 支持通过 Whisper API 进行语音聊天。

请注意：

* 如果超出上下文窗口限制，导入的内容将被截断。
* 必须禁用流媒体才能通过 DALL·E 3 使用图像生成。

## Requirements

* **MathWorks 产品 (https://www.mathworks.com)**：使用 MatGPT 在附带的 [MATLAB Online](https://www.mathworks.com/products/matlab-online.html) 上运行最常用的工具箱。要在桌面上使用它，您的计算机上必须安装 MATLAB R2023a 或更高版本。
* **OpenAI API 密钥**：此外，您还需要从 [https://platform.openai.com/account/api-keys](https://platform.openai.com/account/api -键）。如果您不想使用 OpenAI 设置 API 访问，[MATLAB AI Chat Playground](https://www.mathworks.com/matlabcentral/playground/) 是更好的选择。 
* GPT-4模型[适用于所有有成功支付历史的API用户](https://openai.com/blog/gpt-4-api-general-availability)。如果您尚未向 OpenAI 支付任何费用，则无法访问 GPT-4 模型。

## Installation

### MATLAB Online
在 MATLAB Online 上使用 MatGPT, 点击 [![Open in MATLAB Online](https://www.mathworks.com/images/responsive/global/open-in-matlab-online.svg)](https://matlab.mathworks.com/open/github/v1?repo=toshiakit/MatGPT&file=MatGPT.mlapp)

#### MATLAB Desktop

1. 将此存储库的内容下载到 MATLAB 路径中。 
2. 启动 MATLAB 
3.在命令窗口中输入“MatGPT”

## How to use: MatGPT app

![MatGPT Chat Tab](images/MatGPT.gif)
1. 单击左侧导航栏中的“+ 新聊天”以添加新聊天。这将打开“设置”选项卡。 
2. 在“设置”选项卡中，选择预设来填充设置或自行自定义。完成设置后，点击“开始新聊天”即可发起聊天。这将带您返回“Main”选项卡。 
* 预设从 [Presets.csv](contents/presets.csv) 加载 - 请随意自定义您的提示。 
3. 在“Main”选项卡中，已经根据您选择的预设提供了示例提示，但您可以随意将其替换为您自己的预设。当您单击“发送”按钮时，回复将显示在“聊天”选项卡中。 
* 回形针按钮可让您在聊天中包含 m 文件、实时脚本文件或 csv 文件的内容。
* 如果提示包含 URL，MatGPT 会要求您确认是否要打开该页面。 
* 在“设置”选项卡中配置聊天之前，“发送”按钮和回形针按钮将被禁用。
* 如果您想在回复中提出后续问题的建议，请选中“建议后续问题”复选框。建议的问题显示为可单击的按钮。您可以通过单击建议问题将其复制到提示框中。
* 如果您的提示旨在生成 MATLAB 代码，请选中“测试生成的 MATLAB 代码”复选框以测试返回的代码。
* “使用情况”选项卡显示当前聊天会话中使用的令牌数量。 
* 在“高级”选项卡中添加停止序列，以指定 API 将停止生成更多令牌的序列。
4. 继续添加更多提示并单击“发送”来继续对话。 
5. 您可以在左侧导航面板中右键单击或双击聊天，以重命名、删除聊天或将聊天保存到文本文件。 
6. 当您关闭应用程序时，聊天内容将被保存，并在您重新启动应用程序时重新加载到左侧导航栏中。
### Note:

* 您可以在“设置”中增加连接超时时间。您可以通过 MATLAB 中的 [Web Preferences](https://www.mathworks.com/help/matlab/ref/preferences.html) 添加代理。
* 默认情况下启用流媒体，但您可以在“设置”选项卡中将其关闭。使用数据在流模式下不​​可用。
## What happened to chatGPT class?

chatGPT 类已被“[使用 MATLAB 的大型语言模型 (LLM)](https://github.com/matlab-deep-learning/llms-with-matlab/)”存储库提供的框架取代。新框架支持函数调用和其他最新功能。请参阅存储库中的文档以了解如何使用它。
## Acknowledgements
This code is adapted from [this MATLAB Answers comment](https://www.mathworks.com/matlabcentral/answers/1894530-connecting-to-chatgpt-using-api#answer_1154780) by [Hans Scharler](https://www.mathworks.com/matlabcentral/profile/authors/5863695) and uses [Brian Buechel](https://github.com/brianbuechel)'s [CodeChecker](helpers/CodeChecker.m) and other great contributions. The video shown above was created by [Angel Gonzalez Llacer](https://www.mathworks.com/matlabcentral/profile/authors/12391728). 
   
## License
The license for MatGPT is available in the [LICENSE.txt](LICENSE.txt) file in this GitHub repository.
