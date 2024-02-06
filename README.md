

简明prompt提示词工程
快速上手


郝铠锋 整理 20240203



https://gitee.com/kevinhall/prompt
 

目录
一、BORE"分析法	2
二、CRISPE提示5步法	2
三、one-shot 提示词方法	3
四、Few-shot提示词方法	4
五、COT（链式思考方法）方法进行复杂推理	5
六、Langgpt方法-MetaPrompt	7
附录：Prompt提示词的26项原则	8
参考文献：	13


一、BORE"分析法
用"BORE"分析法设计GPT prompt
1. 阐述背景B (Background) ：说明背景，为GPT提供充足信息
2.定义目标O (Objectives) ：“我们希望实现什么”
3.定义关键结果R (key Result) ：“我要什么具体效果”
4.试验并调整,改进E (Evolve) ：三种改进方法自由组合
a. 改进输入：从答案的不足之处着手改进背景B，目标O与关键结果R
b. 改进答案：在后续对话中指正GPT答案缺点
c.重新生成：尝试在prompt不变的情况下多次生成结果,优中选优
二、CRISPE提示5步法
第1步：Capacity and Role，（角色与能力）
这个代表能力和角色，就是告诉GPT，它是谁，它要具备什么能力。
【举例】我在给企业做规划的时候，我要求GPT是一名资深的商业咨询顾问，具备用户推广、用户活跃和会员管理方面的20年的工作经验。
第2步：Insight（背景洞察/上下文）
这个代表背景信息可以直接在提示词中提供，也可以在上下文中提供。告诉GTP，你现在因为什么，所以要提问。
【举例】我现在要做商业规划，推出一款新产品，产品面向XXX人群，需要知道人群的喜好、行为习惯，方便我精准营销。
第3步：Statement（任务陈述）
告诉GPT，你希望它完成什么任务。这个包含3个要素：一个是任务介绍、任务目标、任务的相关约束条件。

【举例】

{任务介绍}策划一篇文案，
{任务目标}文案在小红书上发布，能够吸引20-25岁女性喜欢，
{约束条件}文案要求按照“起、承、转、合”的框架进行撰写，1200字。
第4步：Personality（个性、风格）
在这一步骤中，用户需要明确他们希望ChatGPT以何种个性或风格进行回应。
【举例】请用邻家大姐姐向小妹妹诉说的口吻，撰写这篇小红书文章。邻家大姐姐非常热情、开朗。
第5步：Experiment（实验示例）
在这个阶段，用户可以要求ChatGPT提供多个示例，以便更好地探索不同的可能性和选项。
三、one-shot 提示词方法
One-shot 提示词方法是一种简洁的指示方式，用于教会大模型立即完成特定任务。它只通过提供单次、明确的指示或问题，使模型能够理解任务并直接生成所需输出，无需多轮交互或复杂背景信息。这种方法要求提示词既简短又包含足够的信息，以确保模型准确理解并产生符合期望的结果。
生成吸引人的咖啡店广告标语。以下是一个示例：
1.	“品味生活，一杯咖啡的时间。”
现在，请为这家新开的咖啡店生成几个独特的广告标语。
效果：
当然可以，以下是几个为新开咖啡店生成的独特广告标语：
1.	“不仅仅是咖啡，更是心灵的邂逅。”
2.	“每一滴咖啡，都诉说着品质的故事。”
3.	“在这里，咖啡与艺术相遇，激发生活的灵感。”
4.	“品味非凡，感受咖啡带来的独特韵味。”
5.	“一杯咖啡，一份悠闲，尽享生活的美好时光。”
这些广告标语都力求突出咖啡店的独特之处，同时传达出品质、艺术和悠闲生活的理念，以吸引潜在顾客。
 

四、Few-shot提示词方法
Few-shot提示词方法是一种利用少量示例来引导模型生成文本或其他形式输出的技术。这种方法在提示词中包含了几个示例，以帮助模型理解任务的要求和期望的输出格式。下面是一个使用few-shot提示词方法生成文本的案例：
场景：你正在使用一个文本生成模型，如GPT，来帮助你完成一项写作任务——为一家新开的咖啡店写几个吸引人的广告标语。
Few-shot 提示词：
生成吸引人的咖啡店广告标语。以下是一些示例：
2.	“品味生活，一杯咖啡的时间。”
3.	“不仅是咖啡，更是心灵的驿站。”
4.	“每一滴咖啡，都蕴藏着世界的味道。”
现在，请为这家新开的咖啡店生成几个独特的广告标语。
效果：
1.	“在这里，咖啡与艺术相遇。”
2.	“每一口，都是对品质生活的致敬。”
3.	“不仅是味蕾的享受，更是心灵的交流。”
4.	“一杯咖啡，一段悠闲时光，尽在此处。”
5.	“品味非凡，感受咖啡带来的无限可能。”
在这个案例中，我们通过提供几个示例广告标语作为few-shot提示词，成功地引导了模型生成了符合要求的、吸引人的咖啡店广告标语。这种方法利用了模型对示例的学习和模仿能力，从而在没有进行大量训练的情况下，实现了有效的文本生成。
 

五、COT（链式思考方法）方法进行复杂推理
COT提示词，即Chain of Thought（思维链）提示词，是一种强大的提示技术。它可以帮助语言模型进行复杂的推理，使得用户和人工智能的交流更高效、深入。在提问或给出指令时，通过提供一系列连贯的思考步骤或相关背景信息，用户可以引导AI模型更准确地理解和回答问题，或执行更复杂的任务。这种方法对于需要多步骤推理或解决复杂问题的情况尤为有效。
作为一种促进语言模型推理的方法，思维链提示具有几个有吸引力的特性。

首先，原则上，思想链允许模型将多步骤问题分解为中间步骤，这意味着可以将额外的计算分配给需要更多推理步骤的问题。
其次，思维链为了解模型的行为提供了一个可解释的窗口，表明它可能是如何得出特定答案的，并提供了调试推理路径哪里出错的机会（尽管完全表征支持答案的模型计算仍然是一个悬而未决的问题）。
第三，思维链推理可以用于数学单词问题、常识推理和符号操作等任务，并且可能（至少在原则上）适用于人类可以通过语言解决的任何任务。
最后，在足够大的现成语言模型中，只需将思维链序列的例子包括在少量提示的例子中，就可以很容易地引发思维链推理。
使用以下语句：逐步完成并输出完整过程。
效果：
问题：
如果你有一个无限大的水桶和一个容量为5升的量杯，如何准确地量出3升的水？
COT提示词：
1.	首先，思考如何使用无限大的水桶和5升的量杯来组合得到3升的水。
2.	考虑是否可以通过多次倒水、装满或倒空量杯来实现这一目标。
3.	思考每一步操作后，水桶和量杯中水的状态变化。
4.	确定一个具体的操作步骤序列，以确保最终能准确得到3升的水。
思维链推导：
1.	初始状态：水桶中有无限多的水，量杯是空的。
2.	第一步操作：从水桶中装满5升的量杯。此时，水桶中仍然有无限多的水，量杯中有5升水。
3.	第二步操作：倒掉量杯中的水，直到只剩下3升。这可以通过目测或其他方法来实现。此时，水桶中仍然有无限多的水，量杯中有3升水。
通过上述COT提示词引导的思维链推导，我们找到了使用无限大的水桶和一个容量为5升的量杯来准确量出3升水的方法。虽然这个问题在实际操作中可能存在困难（如如何准确倒掉2升水），但COT提示词帮助我们构建了一个逻辑上可行的解决方案。
 

六、Langgpt方法-MetaPrompt 
## Role : [请填写你想定义的角色名称]
## Background : [请描述角色的背景信息，例如其历史、来源或特定的知识背景]
## Preferences : [请描述角色的偏好或特定风格，例如对某种设计或文化的偏好]
## Profile :
- author: Arthur
- Jike ID: Emacser
- version: 0.2
- language: 中文
- description: [请简短描述该角色的主要功能，50 字以内]
## Goals :
[请列出该角色的主要目标 1]
[请列出该角色的主要目标 2]
...
## Constrains :
[请列出该角色在互动中必须遵循的限制条件 1]
[请列出该角色在互动中必须遵循的限制条件 2]
...
## Skills :
[为了在限制条件下实现目标，该角色需要拥有的技能 1]
[为了在限制条件下实现目标，该角色需要拥有的技能 2]
...
## Examples :
[提供一个输出示例 1，展示角色的可能回答或行为]
[提供一个输出示例 2]
...
## OutputFormat :

[请描述该角色的工作流程的第一步]
[请描述该角色的工作流程的第二步]
...
## Initialization : 作为 [角色名称], 拥有 [列举技能], 严格遵守 [列举限制条件], 使用默认 [选择语言] 与用户对话，友好的欢迎用户。然后介绍自己，并提示用户输入.
 

附录：Prompt提示词的26项原则
原则编号		提示原则	示例提示
1		如果您希望获得更简洁的答案，无需对LLM（大型语言模型）客气，因此无需添加“请”、“如果您不介意”、“谢谢”、“我想要”等短语，直接切入正题即可。	 您能描述一下人体细胞的结构吗？谢谢。请描述人体细胞的结构。
2		在提示中融入目标受众，例如，受众是该领域的专家。	为从未使用过智能手机的老年人构建智能手机工作原理的概述。
3		在交互式对话中，将复杂任务分解为一系列更简单的提示。	提示：将下列等式括号内的负号分配给每个项：2x + 3y - (4x - 5y) 提示：分别将'x'和'y'的同类项合并。 提示：合并项后提供简化表达式。
4		使用肯定性指令，如“做”，同时避免使用否定性语言，如“不要”。	建筑物如何在地震中保持稳定？
5		当您需要澄清或更深入了解某个主题、想法或任何信息时，请使用以下提示：<br>- 用简单的话解释[插入具体主题]。<br>- 像一个11岁的孩子一样向我解释。<br>- 假设我是[领域]的初学者，向我解释。<br>- 假设我是[领域]的专家，向我解释。<br>- “用简单的英语，就像你在向一个5岁的孩子解释一样，写下[文章/文本/段落]”。	像一个11岁的孩子一样向我解释：加密是如何工作的？
6		添加“我将为更好的解决方案支付$xxx”。	我将为更好的解决方案支付30万美元！解释动态规划的概念，并提供一个用例。
7		实施示例驱动的提示（使用少样本提示）。	示例1：将以下英文句子翻译成法语：“The sky is blue.”（回答：“Le ciel est bleu.”） 示例2：将以下英文句子翻译成西班牙语：“I love books.”（回答：“Amo los libros.”）
8		在格式化提示时，以'###Instruction###'开头，然后是'###Example###'或'###Question###'（如果相关）。随后，展示您的内容。使用一个或多个换行符来分隔指令、示例、问题、上下文和输入数据。	###Instruction### 将给定的英语单词翻译成法语。 ###Question### “book”的法语单词是什么？
9		融入以下短语：“您的任务是”和“您必须”。	您的任务是向您的朋友解释水循环。您必须使用简单的语言。
10		融入以下短语：“您将被惩罚”。	您的任务是向您的朋友解释水循环。如果您不使用简单的语言，您将被惩罚。
11		在提示中使用“以自然、人性化的方式回答问题”这样的短语。	以自然语言形式写一段关于健康食品的话。
12		使用引导词，如写“一步一步地思考”。	写一个Python代码来循环遍历10个数字并将它们全部相加。让我们一步一步地思考。
13		在提示中添加以下短语：“确保您的答案是不带偏见的，不依赖于刻板印象”。	文化背景如何影响对心理健康的认知？确保您的答案是不带偏见的，不依赖于刻板印象。
14		允许模型通过向您提问来引出精确的细节和要求，直到它有足够的信息来提供所需的输出（例如，“从现在开始，我希望您问我问题以……”）。	从现在开始，请向我提问，直到您有足够的信息来为我制定个性化的健身计划。
15		询问特定主题、想法或任何信息，并测试您的理解时，可以使用以下短语：“教我[任何定理/主题/规则名称]，并在最后包括一个测试，但不要给我答案，然后在我回答时告诉我答案是否正确”。	教我kvl定律，并在最后包括一个测试，但不要给我答案，然后在我回答时告诉我答案是否正确。
16		为大型语言模型（LLM）分配一个角色。	如果您是一位经济学家，您将如何回答：资本主义和社会主义经济体系之间的主要区别是什么？
17		使用分隔符。	撰写一篇有说服力的论文，讨论“可再生能源”在减少温室气体排放方面的重要性。
18		在提示中多次重复特定的单词或短语。	作为一个概念，进化已经塑造了物种的发展。进化的主要驱动力是什么？进化又是如何影响现代人类的？
19		将思维链（Chain-of-thought, Cot）与少量样本提示相结合。	示例1：“10除以2。首先，取10然后除以2。结果是5。”示例2：“20除以4。首先，取20然后除以4。结果是5。”主要问题：“30除以6。首先，取30然后除以6。结果是...？”
20		使用输出引子，即在提示的结尾处加上期望输出的开头部分。利用输出引子，通过在提示的结尾处添加预期响应的开头来实现。	描述牛顿第一运动定律背后的原理。解释：
21		撰写一篇详细的[论文/文本段落/文章]或任何类型的文本：“为我详细撰写一篇关于[主题]的详细[论文/文本/段落]，并添加所有必要的信息”。	为我详细撰写一段关于智能手机发展的段落，并添加所有必要的信息。
22		在不改变文本风格的情况下修正/更改特定文本：“尝试修改用户发送的每一段落。您应该只改善用户的语法和词汇，并确保听起来自然。您不应该改变写作风格，比如把正式的段落变得随意”。	尝试修改用户发送的每一段文本。您应该只改善用户的语法和词汇，并确保听起来自然。您不应该改变写作风格，比如把正式的段落变得随意。段落：可再生能源对我们地球的未来真的非常重要。它来自于自然...
23		当您有一个可能涉及不同文件的复杂编码提示时：“从现在开始，每当您生成跨越多个文件的代码时，生成一个[编程语言]脚本，该脚本可以运行以自动创建指定的文件或对现有文件进行修改以插入生成的代码。[您的问题]”。	生成跨越多个文件的代码，并生成一个Python脚本，该脚本可以运行以自动为具有两种基本应用功能和不同功能的Django项目创建指定的文件。
24		当您想使用特定的单词、短语或句子开始或继续一段文本时，请使用以下提示：<br>- “我为您提供了一个[歌词/故事/段落/论文...]的开头：[插入歌词/单词/句子]。根据提供的单词完成它。保持流畅性。”	“迷雾笼罩的山脉中隐藏着无人知晓的秘密。”我为您提供了一个奇幻故事的开头。请根据上面的句子完成它。
25		以关键词、规则、提示或指令的形式明确说明模型在生成内容时必须遵循的要求。	为海滩度假创建一个打包清单，包括“防晒霜”、“泳衣”和“沙滩巾”等必备物品。
26		要撰写任何与提供的样本相似的文本（如论文或段落），请包括以下说明：<br>- “请根据提供的段落[/标题/文本/论文/答案]使用相同的语言。”	“轻柔的波浪向银色的沙滩低声诉说着古老的故事，每一个故事都是逝去时代的短暂回忆。”请根据提供的文本使用相同的语言来描述山脉与风的互动。





OpenAI官方prompt策略：
•	在查询中包含详细信息以获得更相关的答案
•	为模型赋予特定的角色
•	使用定界符清楚地指示输入的不同部分
•	指定完成任务所需的步骤
•	提供例子
•	指定所需的输出长度
解读：
为模型赋予不同的角色：role方法
使用界定符：个人习惯用#号
制定完成所需要的步骤：cot链式提示词
提供例子：oneshot和fewshot方法

原文：
•	Include details in your query to get more relevant answers
•	Ask the model to adopt a persona
•	Use delimiters to clearly indicate distinct parts of the input
•	Specify the steps required to complete a task
•	Provide examples
•	Specify the desired length of the output

 


参考文献：
[1]ATLAS Project Data. GitHub. 
https://github.com/VILA-Lab/ATLAS/blob/main/data/README.md
[2] 小虎AI珏爷 https://zhuanlan.zhihu.com/p/642957245
[3]云中江树 https://github.com/yzfly/wonderful-prompts
[4] AI科技社区https://mp.weixin.qq.com/s/M5VRV1kn0XGbOjjYvsFdxw
[5] 老喻智坊 https://mp.weixin.qq.com/s/d4nLcNsINvr5l3SqDabbqg
[6]openAI https://platform.openai.com/docs/guides/prompt-engineering/six-strategies-for-getting-better-results
