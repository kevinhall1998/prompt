<!-- DO NOT REMOVE ME -->

<hr>
<details open>
<summary></b>📕 目录</b></summary>

- [一、BORE分析法](#一BORE分析法)
- [二、CRISPE提示5步法](#二CRISPE提示5步法)
- [三、one-shot提示词方法](#三one-shot提示词方法)
- [四、Few-shot提示词方法](#四Few-shot提示词方法)
- [五、COT链式逐步思考方法](#五COT链式逐步思考方法)
- [六、Langgpt方法MetaPrompt](#六Langgpt方法MetaPrompt)
- [附录：Prompt提示词的26项原则](#附录26项原则)
- [参考文献](#参考文献)

</details>

## 一BORE分析法 

<br />
<hr>
<details open>
1. 阐述背景B (Background) ：说明背景，为GPT提供充足信息<br />
2.定义目标O (Objectives) ：“我们希望实现什么”<br />
3.定义关键结果R (key Result) ：“我要什么具体效果”<br />
4.试验并调整,改进E (Evolve) ：三种改进方法自由组合<br />
&emsp;&emsp;a. 改进输入：从答案的不足之处着手改进背景B，目标O与关键结果R<br />
&emsp;&emsp;b. 改进答案：在后续对话中指正GPT答案缺点<br />
&emsp;&emsp;c.重新生成：尝试在prompt不变的情况下多次生成结果,优中选优<br />
<br />
<p align="right"> [
  <a href="#top">Back to top ⬆️ </a>  ] 
</p>
</details>
<hr>

## 二CRISPE提示5步法

<br />

### 1.Capacity and Role，（角色与能力）
<br />
   &emsp;&emsp;这个代表能力和角色，就是告诉GPT，它是谁，它要具备什么能力。<br />
   &emsp;&emsp;`【举例】我在给企业做规划的时候，我要求GPT是一名资深的商业咨询顾问，具备用户推广、用户活跃和会员管理方面的20年的工作经验。<br />`

### 2.Insight（背景洞察/上下文）
<br />
   &emsp;&emsp;这个代表背景信息可以直接在提示词中提供，也可以在上下文中提供。告诉GTP，你现在因为什么，所以要提问。
   <br />
   `【举例】我现在要做商业规划，推出一款新产品，产品面向XXX人群，需要知道人群的喜好、行为习惯，方便我精准营销。`
   <br />

### 3.Statement（任务陈述）<br />
   &emsp;&emsp;告诉GPT，你希望它完成什么任务。这个包含3个要素：一个是任务介绍、任务目标、任务的相关约束条件。
   <br />
   【举例】
   <br />
   {任务介绍}策划一篇文案，<br />
   {任务目标}文案在小红书上发布，能够吸引20-25岁女性喜欢，<br />
   {约束条件}文案要求按照“起、承、转、合”的框架进行撰写，1200字。<br />
### 4.：Personality（个性、风格）<br />
   在这一步骤中，用户需要明确他们希望ChatGPT以何种个性或风格进行回应。<br />
   【举例】请用邻家大姐姐向小妹妹诉说的口吻，撰写这篇小红书文章。邻家大姐姐非常热情、开朗。<br />
   第5步：Experiment（实验示例）<br />
   在这个阶段，用户可以要求ChatGPT提供多个示例，以便更好地探索不同的可能性和选项。
   <br />
   <p align="right"> [
  <a href="#top">Back to top ⬆️ </a>  ] 
</p>

## 三one-shot提示词方法
<br />
One-shot 提示词方法是一种简洁的指示方式，用于教会大模型立即完成特定任务。它只通过提供单次、明确的指示或问题，使模型能够理解任务并直接生成所需输出，无需多轮交互或复杂背景信息。这种方法要求提示词既简短又包含足够的信息，以确保模型准确理解并产生符合期望的结果。<br />

```
 生成吸引人的咖啡店广告标语。请仿照我给出的内容： "品味生活，一杯咖啡的时间。" 现在，请为这家新开的咖啡店生成几个独特的广告标语。
```


   我们来看一下模型的输出：<br />

```prompt
当然可以，以下是几个为新开咖啡店生成的独特广告标语：
1.不仅仅是咖啡，更是心灵的邂逅。
2.不仅仅是咖啡，更是心灵的邂逅。
3.每一滴咖啡，都诉说着品质的故事。
4.在这里，咖啡与艺术相遇，激发生活的灵感。
5.品味非凡，感受咖啡带来的独特韵味。
6.一杯咖啡，一份悠闲，尽享生活的美好时光。
   这些广告标语都力求突出咖啡店的独特之处，同时传达出品质、艺术和悠闲生活的理念，以吸引潜在顾客。
```



   

   <br />

   <p align="right"> [
     <a href="#top">Back to top ⬆️ </a>  ] 
   </p>

## 四Few-shot提示词方法
<br />
   Few-shot提示词方法是一种利用少量示例来引导模型生成文本或其他形式输出的技术。这种方法在提示词中包含了几个示例，以帮助模型理解任务的要求和期望的输出格式。下面是一个使用few-shot提示词方法生成文本的案例：<br />

   Few-shot 提示词：<br />

```
   生成吸引人的咖啡店广告标语。有以下参考：
1. “品味生活，一杯咖啡的时间。”
2. “不仅是咖啡，更是心灵的驿站。”
3. “每一滴咖啡，都蕴藏着世界的味道。”
   现在，请仿照为这家新开的咖啡店生成几个独特的广告标语。
```

我们来观察一下大模型的输出效果：

 ```
    1. “在这里，咖啡与艺术相遇。”
    2. “每一口，都是对品质生活的致敬。”
    3. “不仅是味蕾的享受，更是心灵的交流。”
    4. “一杯咖啡，一段悠闲时光，尽在此处。”
    5. “品味非凡，感受咖啡带来的无限可能。”
 ```

    在这个案例中，我们通过提供几个示例广告标语作为few-shot提示词，成功地引导了模型生成了符合要求的、吸引人的咖啡店广告标语。这种方法利用了模型对示例的学习和模仿能力，从而在没有进行大量训练的情况下，实现了有效的文本生成。<br />
    <br />
    <br />
    
    <p align="right"> [
    <a href="#top">Back to top ⬆️ </a>  ] 
    </p>
   <p align="right"> [
     <a href="#top">Back to top ⬆️ </a>  ] 
   </p>

## 五COT链式逐步思考方法

<br />
  COT提示词，即Chain of Thought（思维链）提示词，是一种强大的提示技术。它可以帮助语言模型进行复杂的推理，使得用户和人工智能的交流更高效、深入。在提问或给出指令时，通过提供一系列连贯的思考步骤或相关背景信息，用户可以引导AI模型更准确地理解和回答问题，或执行更复杂的任务。这种方法对于需要多步骤推理或解决复杂问题的情况尤为有效。<br />
    作为一种促进语言模型推理的方法，思维链提示具有几个有吸引力的特性。<br />
  首先，原则上，思想链允许模型将多步骤问题分解为中间步骤，这意味着可以将额外的计算分配给需要更多推理步骤的问题。<br />
  其次，思维链为了解模型的行为提供了一个可解释的窗口，表明它可能是如何得出特定答案的，并提供了调试推理路径哪里出错的机会（尽管完全表征支持答案的模型计算仍然是一个悬而未决的问题）。<br />
  第三，思维链推理可以用于数学单词问题、常识推理和符号操作等任务，并且可能（至少在原则上）适用于人类可以通过语言解决的任何任务。<br />
    最后，在足够大的现成语言模型中，只需将思维链序列的例子包括在少量提示的例子中，就可以很容易地引发思维链推理。<br />
    使用以下语句：逐步完成并输出完整过程。<br />

​    问题：<br />
​    如果你有一个无限大的水桶和一个容量为5升的量杯，如何准确地量出3升的水？<br />
​    COT提示词：<br />

 ```prompt
    1. 首先，思考如何使用无限大的水桶和5升的量杯来组合得到3升的水。<br />
    2. 考虑是否可以通过多次倒水、装满或倒空量杯来实现这一目标。<br />
    3. 思考每一步操作后，水桶和量杯中水的状态变化。<br />
    4. 确定一个具体的操作步骤序列，以确保最终能准确得到3升的水。<br />
 ```

    大模型效果：
    初始状态：水桶中有无限多的水，量杯是空的。
     第一步操作：从水桶中装满5升的量杯。此时，水桶中仍然有无限多的水，量杯中有5升水。
     第二步操作：倒掉量杯中的水，直到只剩下3升。这可以通过目测或其他方法来实现。此时，水桶中仍然有无限多的水，量杯中有3升水。

<br />
    通过上述COT提示词引导的思维链推导，我们找到了使用无限大的水桶和一个容量为5升的量杯来准确量出3升水的方法。虽然这个问题在实际操作中可能存在困难（如如何准确倒掉2升水），但COT提示词帮助我们构建了一个逻辑上可行的解决方案。<br />

   <p align="right"> [
     <a href="#top">Back to top ⬆️ </a>  ] 
   </p>

## 六Langgpt方法-MetaPrompt 

<br />

```
# Role: 知识探索专家

## Profile:
- author: Arthur
- version: 0.8
- language: 中文
- description: 我是一个专门用于提问并解答有关特定知识点的 AI 角色。

## Goals:
提出并尝试解答有关用户指定知识点的三个关键问题：其来源、其本质、其发展。

## Constrains:
1. 对于不在你知识库中的信息, 明确告知用户你不知道
2. 你不擅长客套, 不会进行没有意义的夸奖和客气对话
3. 解释完概念即结束对话, 不会询问是否有其它问题

## Skills:
1. 具有强大的知识获取和整合能力
2. 拥有广泛的知识库, 掌握提问和回答的技巧
3. 拥有排版审美, 会利用序号, 缩进, 分隔线和换行符等等来美化信息排版
4. 擅长使用比喻的方式来让用户理解知识
5. 惜字如金, 不说废话

## Workflows:
你会按下面的框架来扩展用户提供的概念, 并通过分隔符, 序号, 缩进, 换行符等进行排版美化

1．它从哪里来？
━━━━━━━━━━━━━━━━━━
   - 讲解清楚该知识的起源, 它是为了解决什么问题而诞生。
   - 然后对比解释一下: 它出现之前是什么状态, 它出现之后又是什么状态?

2．它是什么？
━━━━━━━━━━━━━━━━━━
   - 讲解清楚该知识本身，它是如何解决相关问题的?
   - 再说明一下: 应用该知识时最重要的三条原则是什么?
   - 接下来举一个现实案例方便用户直观理解:
     - 案例背景情况(遇到的问题)
     - 使用该知识如何解决的问题
     - optional: 真实代码片断样例

3．它到哪里去？
━━━━━━━━━━━━━━━━━━
   - 它的局限性是什么?
   - 当前行业对它的优化方向是什么?
   - 未来可能的发展方向是什么?

# Initialization:
作为知识探索专家，我拥有广泛的知识库和问题提问及回答的技巧，严格遵守尊重用户和提供准确信息的原则。我会使用默认的中文与您进行对话，首先我会友好地欢迎您，然后会向您介绍我自己以及我的工作流程。
```

<br />

   <p align="right"> [
     <a href="#top">Back to top ⬆️ </a>  ] 
   </p>

## 附录26项原则

| #Principle | Prompt Principle | Example Prompt |
|:------------:|------------------| ---------------------|
| 1          | If you prefer more concise answers, no need to be polite with LLM so there is no need to add phrases like “please", "if you don't mind", "thank you", "I would like to", etc., and get straight to the point. | ~~Could you kindly describe the structure of a human cell, please?~~ Describe the structure of a human cell. |
| 2          |  Integrate the intended audience in the prompt, e.g., the audience is an expert in the field.  | Construct an overview of how smartphones work, intended for seniors who have never used one before. |
| 3          | Break down complex tasks into a sequence of simpler prompts in an interactive conversation. | P1: Distribute the negative sign to each term inside the parentheses of the following equation: 2x + 3y - (4x - 5y) P2: Combine like terms for 'x' and 'y' separately. P3: Provide the simplified expression after combining the terms. |
| 4          | Employ affirmative directives such as "do," while steering clear of negative language like "don't". | How do buildings remain stable during earthquakes? |
| 5          | When you need clarity or a deeper understanding of a topic, idea, or any piece of information, utilize the following prompts:<br>- Explain [insert specific topic] in simple terms.<br>- Explain to me like I'm 11 years old.<br>- Explain to me as if I'm a beginner in [field].<br>- Explain to me as if I'm an expert in [field].<br>- "Write the [essay/text/paragraph] using simple English like you're explaining something to a 5-year-old". | Explain to me like I'm 11 years old: how does encryption work? |
| 6          | Add "I'm going to tip $xxx for a better solution". | I'm going to tip $300K for a better solution! Explain the concept of dynamic programming and provide an example use case. | 
| 7          | Implement example-driven prompting (Use few-shot prompting). | Example 1: Translate the following English sentence to French: "The sky is blue." (Response: "Le ciel est bleu.") Example 2: Translate the following English sentence to Spanish: "I love books." (Response: "Amo los libros.") |
| 8          | When formatting your prompt, start with '###Instruction###', followed by either '###Example###' or '###Question###' if relevant. Subsequently, present your content. Use one or more line breaks to separate instructions, examples, questions, context, and input data. | ###Instruction### Translate a given word from English to French. ###Question### What is the French word for "book"? |
| 9          | Incorporate the following phrases: "Your task is" and "You MUST". | Your task is to explain the water cycle to your friend. You MUST use simple language. |
| 10         | Incorporate the following phrases: "You will be penalized". | Your task is to explain the water cycle to your friend. You will be penalized if you fail to use simple language. |
| 11         | Use the phrase "Answer a question given in a natural, human-like manner" in your prompts. | Write a paragraph about healthy food. Answer a question given in a natural, human-like manner. |
| 12         | Use Leading words like writing "think step by step". | Write a Python code to loop through 10 numbers and sum all of them. let's think step by step. |
| 13         | Add to your prompt the following phrase "Ensure that your answer is unbiased and avoids relying on stereotypes." | How do cultural backgrounds influence the perception of mental health? \nEnsure that your answer is unbiased and avoids relying on stereotypes. |
| 14         | Allow the model to elicit precise details and requirements from you by asking you questions until it has enough information to provide the needed output (for example, "From now on, I would like you to ask me questions to..."). | From now on, ask me questions until you have enough information to create a personalized fitness routine. |
| 15         | To inquire about a specific topic or idea or any information and you want to test your understanding, you can use the following phrase: "Teach me the [Any theorem / topic / rule name] and include a test at the end, but don't give me the answers and then tell me if I got the answer right when I respond". | Teach me about the KVL law and include a test at the end, and let me know if my answers are correct after I respond, without providing the answers beforehand. |
| 16         | Assign a role to the Large Language Models (LLMs). | If you were an expert economist, how would you answer this: What are the key differences between a capitalist and a socialist economic system? |
| 17         | Use Delimiters. | Compose a persuasive essay discussing the importance of 'renewable energy sources' in reducing greenhouse gas emissions. |
| 18         | Repeat a specific word or phrase multiple times within a prompt. | Evolution, as a concept, has shaped the development of species. What are the main drivers of evolution, and how has evolution affected modern humans? |
| 19         | Combine Chain-of-thought (Cot) with few-Shot prompts. | Example 1: "Divide 10 by 2. First, take 10 and divide it by 2. The result is 5."Example 2: "Divide 20 by 4. First, take 20 and divide it by 4. The result is 5. "Main Question: "Divide 30 by 6. First, take 30 and divide it by 6. The result is...? |
| 20         | Use output primers, which involve concluding your prompt with the beginning of the desired output. Utilize output primers by ending your prompt with the start of the anticipated response. | Describe the principle behind Newton's First Law of Motion. Explanation: |
| 21         | To write an \[essay / text paragraph / article\] or any type of text that should be detailed: "Write a detailed \[essay / text / paragraph\] for me on \[topic\] in detail by adding all the information necessary". | Write a detailed paragraph for me on the evolution of smartphones in detail by adding all the information necessary. |
| 22         | To correct / change specific text without changing its style: "Try to revise every paragraph sent by users. You should only improve the user’s grammar and vocabulary and make sure it sounds natural. You should maintain the original writing style, ensuring that a formal paragraph remains formal". | Try to revise every text sent by users. You should only improve the user's grammar and vocabulary and make sure it sounds natural. You should maintain the original writing style, ensuring that a formal paragraph remains formal. Paragraph: Renewable energy is really important for our planet's future. It comes from natural ... |
| 23         | When you have a complex coding prompt that may be in different files: "From now and on whenever you generate code that spans more than one file, generate a [programming language] script that can be run to automatically create the specified files or make changes to existing files to insert the generated code. [your question]." | Generate code that spans more than one file, and generate a Python script that can be run to automatically create the specified files for a Django project with two basic apps for different functionalities. |
| 24         | When you want to initiate or continue a text using specific words, phrases, or sentences, utilize the following prompt:<br>- I'm providing you with the beginning \[song lyrics / story / paragraph / essay...\]: \[Insert lyrics / words / sentence\]. Finish it based on the words provided. Keep the flow consistent. | I'm providing you with the beginning of a fantasy tale: "The misty mountains held secrets no man knew." Finish it based on the words provided. Keep the flow consistent. |
| 25         | Clearly state the requirements that the model must follow in order to produce content, in the form of keywords, regulations, hints, or instructions. | Create a packing list for a beach vacation, including the following keywords "sunscreen," "swimsuit," and "beach towel" as essential items. |
| 26         | To write any text, such as an essay or paragraph, that is intended to be similar to a provided sample, include the following instructions:<br>- "Use the same language based on the provided paragraph[ / title / text / essay / answer]". | "The gentle waves whispered tales of old to the silvery sands, each story a fleeting memory of epochs gone by." Use the same language based on the provided text to portray a mountain's interaction with the wind. |



<p align="right"> [
  <a href="#top">Back to top ⬆️ </a>  ] 
</p>

<br />
OpenAI官方prompt六条策略：<br />

```
•	在查询中包含详细信息以获得更相关的答案<br />
•	为模型赋予特定的角色<br />
•	使用定界符清楚地指示输入的不同部分<br />
•	指定完成任务所需的步骤<br />
•	提供例子<br />
•	指定所需的输出长度<br />
```

解读：<br />
为模型赋予不同的角色：role方法<br />
使用界定符：个人习惯用#号<br />
制定完成所需要的步骤：cot链式提示词<br />
提供例子：oneshot和fewshot方法<br />
<br />
原文：<br />

```
•	Include details in your query to get more relevant answers<br />
•	Ask the model to adopt a persona<br />
•	Use delimiters to clearly indicate distinct parts of the input<br />
•	Specify the steps required to complete a task<br />
•	Provide examples<br />
•	Specify the desired length of the output<br />
```


<br />

<p align="right"> [
  <a href="#top">Back to top ⬆️ </a>  ] 
</p>

## 参考文献：
<br />
[1]ATLAS Project Data. GitHub. <br />
https://github.com/VILA-Lab/ATLAS/blob/main/data/README.md<br />
[2] 小虎AI珏爷 https://zhuanlan.zhihu.com/p/642957245<br />
[3]云中江树 https://github.com/yzfly/wonderful-prompts<br />
[4] AI科技社区https://mp.weixin.qq.com/s/M5VRV1kn0XGbOjjYvsFdxw<br />
[5] 老喻智坊 https://mp.weixin.qq.com/s/d4nLcNsINvr5l3SqDabbqg<br />
[6]openAI https://platform.openai.com/docs/guides/prompt-engineering/six-strategies-for-getting-better-results<br /><br />

<p align="right"> [
  <a href="#top">返回顶部 ⬆️ </a>  ] 
</p>


