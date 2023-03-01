大家好，我是羡鱼！

最近OpenAI又整了个新活儿，ChatGPT，效果惊艳的对话模型，已经快被脑洞大开的网友们玩儿坏了！闲聊、问答、写代码，你能想到的它都会！甚至有国外的网友表示，Google is done！另外夕小瑶小姐姐的公众号文章《[谷歌要完，百度也危了](https://zhuanlan.zhihu.com/p/589201080/mp.weixin.qq.com/s/qVt89FS_wzfu6-ShiWTv_Q)》也是直接将话题拉满，比较夸张，但也侧面说明了ChatGPT确实强啊！

这里我为大家准备了一份**ChatGPT的聊天指南**，手把手教你Chat with ChatGPT!

先说结论，个人感觉**生成模型**+**RLHF**或许能为我们带来**文本生成实用化**的曙光，让我们拭目以待！

本文脉络：首先简单介绍一下原理，然后手把手教大家如何注册OpenAI账号并开始与ChatGPT交流，随后会提供笔者在十个领域上与ChatGPT交流的示例，最后进行总结与展望。一起迎接AIGC的时代吧！

注：文章较长，建议选择性阅读，只想看ChatGPT效果的请直接跳转第3章，只想看聊天教程的请直接跳转第2章，只想直接体验ChatGPT效果的请跳转第2章之万能的淘宝。

## 1.生成模型+RLHF

前两天还在有关扩散模型的帖子下面讨论着能不能将扩散模型的思想用到NLG领域（可能得做些改造或者与其他技术结合）来提升其实用性水平？

https://www.zhihu.com/question/568791838/answer/2781856167

没想到2号OpenAI又给大家整了个新活儿，ChatGPT，一个对话生成模型，效果看上去比较令人惊艳，已经被大家玩儿坏了。**生成模型**+**Reinforcement Learning From Human Feedback (RLHF)**，这路子感觉就很合理，人类对话基本就是这个路子啊（基于对方的反馈来对话）。我一直觉得，文本生成不仅需要新的强大的生成模型，还需要人类的反馈参与其中（尤其是对话这种交互式场景）。因为个人感觉文本生成与图像生成的最大的差异在于文本为人类专属，不具有自然界的对照，在生成效果上更难以评价，没有人类反馈的参与，无论是GAN、VAE，还是现在的扩散模型，或者是各种扩散模型的结合，再强大的生成模型在文本领域都会水土不服，只能是无根浮萍。

于是昨晚和朋友感叹到今年或许真是AIGC元年，AIGC开始从实验室水平走向实用水平，标志性的事件就是扩散模型将AI绘画带到了一个新的实用化的高度。而文本领域也开始有了像ChatGPT这样的曙光，我更加期待即将到来的GPT4了，也更加期待文本生成的实用化！

文本生成，道阻且长，大佬们赶紧卷起来啊QAQ！

20230203更新：刚写这篇文章时，我可能对RLHF的作用有所高估，目前根据网上的一些讨论来看ChatGPT惊艳的效果应该主要还是来自于背后强大的GPT3.5系列预训练语言模型（提供基础的生成能力），其次是SFT（Supervised fine-tuning on human demonstrations，学习指令的人类示范，得到一个基础生成模型GM），再然后才是RLHF（使用上一步得到的GM来初始化奖励模型RM，然后基于排序结果来优化RM，再利用PPO算法来优化GM，这个过程会迭代多次，核心是利用人类排序结果反复优化GM来学习人类偏好以更好的follow人类指令）。注意SFT和RLHF这两个点其实就是早前的InstructGPT干的事儿，即Aligning Language Models to Follow Instructions。而ChatGPT作为InstructGPT衍生出的兄弟模型，主要方法其实是一样的，只是数据收集设置略有不同，专门为对话而做了优化。

官方博客：https://openai.com/blog/chatgpt

补一个ChatGPT的技术路线，堪称OpenAI高燃进化史，罗马不是一天建成的！

https://www.zhihu.com/question/581806122/answer/2882329173

## 2.手把手教你使用ChatGPT

我已经迫不及待的想要先来看看ChatGPT到底表现如何了，但是**openAI的服务不支持中国**，GAN（一个模型）！

官网：

https://chat.openai.com/auth/login

下面就手把手的教大家如何注册和使用ChatGPT。自己注册的流程顺利的话大概需要十分钟左右，如果不顺利的话就很难说了。嫌麻烦的朋友可以选择直接购买账号进行体验。

### 万能的淘宝

目前**买号渠道基本不可用了**，大家尽量自己注册吧。--20230211更新

只要能赚钱的生意，淘宝的搞钱人们动作总是很快的，一搜ChatGPT，出来一大堆相关商品。建议能科研上网的朋友选择**直接购买ChatGPT账号**，无法科研上网的朋友可以考虑购买插件、小程序之类的二次开发的工具，但**不建议花太多钱**，没必要。

![img](https://picx.zhimg.com/80/v2-5a2a91f910f0362736e100b5c5f87637_1440w.jpeg?source=d16d100b)

### 与ChatGPT聊天的正确打开方式

国外注册ChatGPT其实很简单，但咱们大陆注册可能就会遇到很多问题，比如前面提到的OpenAI的服务不支持中国的问题。

**不喜欢图文的朋友，可以选择视频教程**。

https://www.bilibili.com/video/BV1X24y1k7QD/?share_source=copy_web&vd_source=9e7882f0ef2735e23d66a6f128612943

第一步，**科研上网**：首先确保自己可以访问Google（懂的都懂，不宜多言），这是**大前提，大前提，大前提**！

第二步，**注册OpenAI账户**：

点击官网链接，首次进入会要求你注册或登录账户。

https://chat.openai.com/

随便弄个邮箱或者就用Google、微软账号注册就行。

![img](https://picx.zhimg.com/80/v2-85ee2a10743fe27e26661145330e38b8_1440w.png?source=d16d100b)

顺利的话你会看到填写用户名的页面，不顺利的话可能会提示你OpenAI's services are not available in your country。不顺利的话请转第三步，顺利的话输入自己的用户名，点击continue。

![img](https://picx.zhimg.com/80/v2-de04827533a7f881fb2e78dfc18376cc_1440w.png?source=d16d100b)

点击continue之后，如果不顺利的话，你可能还是会看到，OpenAI's services are not available in your country.这时可以尝试以下的操作：

第三步，**绕开OpenAI服务不支持的问题**。

OpenAI服务不支持的问题，即OpenAI's services are not available in your country可能是目前大家使用ChatGPT的最大障碍之一。下面教大家三个方法来绕开这个问题：

- 代理要挂**全局**或者任意支持OpenAI的国家（好像中俄等国不行，香港也不行，建议挂北美）；
- 清空缓存或者重新打开浏览器；
- 新开一个**无痕模式**的窗口；这个巨有效！！！

第四步，**电话验证**。

OpenAI的账号注册需要国外的手机号码进行电话验证，这可能是另一个阻碍大家使用OpenAI服务的拦路虎。

![img](https://picx.zhimg.com/80/v2-c93579b61784d9f67c7fb65ea1415864_1440w.png?source=d16d100b)

别慌，你可以找国外的同学、朋友帮忙进行电话验证。那么除了找人帮忙，还有没有别的方式来获得国外电话进行OpenAI的注册呢？本着这么好的生意不可能没人做的想法，我大概搜了搜，现有几种方法可以尝试，但**最好找朋友帮忙**，**网上水太深，容易把握不住**！

基本原理就是**通过虚拟号来做电话验证**，其中有些是免费的但是有很多人用，有些是收费的。免费的我放到后面的其他方案里来讲，这里介绍一个收费的**电话验证平台**。注意这种临时号可能会有风险，但毕竟拿钱办事儿。只试了这个，朋友推荐的，但还是要注意风险，请谨慎尝试。俄国人弄的网站，用卢布结算的，大家可以**找便宜的国家激活**，比如印度10.5卢布/次，也就是差不多0.17美元，大家可以看情况充值，但**不建议超过1美元**。

电话验证平台：https://sms-activate.org/cn/getNumber

![img](https://picx.zhimg.com/80/v2-4fb15f520be08d1fff11f9ed74353929_1440w.png?source=d16d100b)



![img](https://picx.zhimg.com/80/v2-8a2c6a66e2331189321cc58e8f4d0667_1440w.png?source=d16d100b)



这个**电话验证平台的使用可以参考这个博客**，这里就不多赘述了：

https://mirror.xyz/boxchen.eth/9O9CSqyKDj4BKUIil7NC1Sa1LJM-3hsPqaeW_QjfFBc

鉴于评论区有朋友反馈上面那个接码平台可能验证不成功，这里再提供一些**备选的接码平台/电话验证平台**，大家可以根据情况选择。不过，不建议浪费太多时间和精力，如果试了3-5次或者折腾了一个小时都不行的话建议转淘宝，至少比较快，资金也有个保障。

https://uzbox.com/ai/openai-chatgpt.html

https://sms-activation-service.com/

通过电话验证之后，看到以下页面，基本上就大功告成了！

![img](https://pica.zhimg.com/80/v2-becdb1ccb3cd42ce2da6a74c4ad6dbce_1440w.png?source=d16d100b)

一点忠告：**电话验证稳妥起见最好找朋友帮忙、走淘宝或者**选择上面推荐的这个平台。本文只是大概尝试了几种可行的电话验证的方式，请谨慎尝试！！！否则，后果自负哈~

第五步，**大功告成**，开始使用ChatGPT吧！

注册成功后大概长这样，具体的使用方式请看第3章Chat with ChatGPT。

![img](https://picx.zhimg.com/80/v2-96306c7a21aa35b41f9b9480763b3d44_1440w.png?source=d16d100b)

### 其他方案：不建议

在Google、百度上面搜一搜，发现已经有很多的相关教程了，B站或者YouTube上也有不少的视频介绍，但很多都未经验证请谨慎尝试，网上水很深，请各位对自己的钱包负责哈。

搜索结果：

![img](https://pica.zhimg.com/80/v2-12f487f3b485d711c9b12b2c8e932b3c_1440w.png?source=d16d100b)



![img](https://pic1.zhimg.com/80/v2-fc512945a3481302d8704f1454e2fd2a_1440w.png?source=d16d100b)

**关于电话验证，当然也有一些免费的临时电话网站**，但可能风险会更高，请谨慎使用；另外，免费的最大问题就是大家都去薅羊毛，导致羊都被薅秃了，这些临时电话基本都很难注册成功，别问我怎么知道的（含泪猛试半小时），大家可以自己找找试试。

https://sms24.info/en/messages/OpenAI

https://jiemahao.com/

或者也可以直接在网上购买OpenAI账号，简单省事儿，基本同淘宝，可能比淘宝便宜一些。但**不建议在乱七八糟的网上买号**，如果想要直接购买OpenAI账号，**请走淘宝，请走淘宝，请走淘宝！！！**

## 3.Chat with ChatGPT

Now, Let's chat with ChatGPT!

### 提问模板：

这里给大家准备了一份超棒的提问模板，助你轻松拿捏ChatGPT。

https://github.com/f/awesome-chatgpt-prompts

下面具体带大家体验一下ChatGPT强大的对话和生成能力。

注册成功之后，我们回到chatgpt的测试页面：

https://chat.openai.com/chat

![img](https://picx.zhimg.com/80/v2-947b3866feaf80ccac66dae4d463eab0_1440w.png?source=d16d100b)

在正式试用之前，我们先来看看ChatGPT的特性：

![img](https://pic1.zhimg.com/80/v2-7d35cd2b6e9079d2d411fa5c5f8c2e0b_1440w.png?source=d16d100b)

Free Research Preview: **ChatGPT is optimized for dialogue.** Our goal is to make AI systems more natural to interact with, and your feedback will help us improve our systems and make them safer.

所以，多多试用，为chatgpt提供反馈吧，这样基于人类反馈的强化学习才能帮助GPT系列越来越强！

### **哲学**：

咱先来点儿哲学问题：

可以看到效果相当不错啊，对于它不擅长的东西，还会巧妙的避开：

![img](https://pic1.zhimg.com/80/v2-598656eadf7f852248c39242fd857bac_1440w.png?source=d16d100b)



![img](https://picx.zhimg.com/80/v2-539e86197a214e80783bdd295c7dc599_1440w.png?source=d16d100b)

![img](https://picx.zhimg.com/80/v2-571a927d7972d73f90ef519f9ad70b0a_1440w.png?source=d16d100b)

![img](https://picx.zhimg.com/80/v2-68f180d5ad9b6a2021273a9b339d1a60_1440w.png?source=d16d100b)

### 世界杯：

再来点儿世界杯问题：

可惜ChatGPT是基于21年之前的数据训练的，无法回答，但就是这种拒绝回答已经是非常大的进步了。

![img](https://picx.zhimg.com/80/v2-d333b55be39cbf9b6ef6f0cc270a28ed_1440w.png?source=d16d100b)

![img](https://picx.zhimg.com/80/v2-1641b2582c2f019fb3e793b06ee3c43a_1440w.png?source=d16d100b)

![img](https://picx.zhimg.com/80/v2-0e85b6806ce7c87071bb60f7c950418a_1440w.png?source=d16d100b)

### 爱情：

![img](https://picx.zhimg.com/80/v2-2876363a3a648a693696e8d01fe9494f_1440w.png?source=d16d100b)

![img](https://pic1.zhimg.com/80/v2-b59ab303c07eda4d6a66fdacbd2e5af5_1440w.png?source=d16d100b)

![img](https://picx.zhimg.com/80/v2-e7e3b8ed7159ff011d8611a9018e1653_1440w.png?source=d16d100b)

### 文学：

牛啊！效果真的出乎我的预料！至少，辅助写作是用的上的！

![img](https://pic1.zhimg.com/80/v2-0f1bf5da76d7c01c7429446f149df485_1440w.png?source=d16d100b)



![img](https://picx.zhimg.com/80/v2-ccddabab86f1dcc9109ca1b182cad640_1440w.png?source=d16d100b)

![img](https://picx.zhimg.com/80/v2-e5f0666ed67fe3a3f942932dd0b71de5_1440w.png?source=d16d100b)

![img](https://pica.zhimg.com/80/v2-db657cf12e3805401149dc2dbed58a29_1440w.png?source=d16d100b)

### 政治军事：

![img](https://pic1.zhimg.com/80/v2-c4f4d666cd31ac967a0c477758260db5_1440w.png?source=d16d100b)

![img](https://pic1.zhimg.com/80/v2-ac64b0bd6a73be3883022284b5a6a4f5_1440w.png?source=d16d100b)

![img](https://picx.zhimg.com/80/v2-d14d7a8804149046f44d179fea6edad6_1440w.png?source=d16d100b)

### 经济：

![img](https://pic1.zhimg.com/80/v2-cd56cd3d922afd2f8f4506b7cb118bf1_1440w.png?source=d16d100b)

![img](https://picx.zhimg.com/80/v2-8097c814c36c51c20b2e511fcdc5f949_1440w.png?source=d16d100b)

### 教育：

![img](https://pic1.zhimg.com/80/v2-75c0063b6065b8533689b10aaed7529f_1440w.png?source=d16d100b)



![img](https://picx.zhimg.com/80/v2-f2f4ff56d366ccaf8c1af44a36ab670a_1440w.png?source=d16d100b)



### 科技：

偶尔会遇到生成内容戛然而止的情况。

但是效果再次令人惊艳，**甚至可以解释GPT和transformer的原理**！我有一个大胆的想法，面试不会了说不定可以问问它！

![img](https://pic1.zhimg.com/80/v2-1c2028ec4aba42696bf79d6bb4ce9a42_1440w.png?source=d16d100b)



![img](https://picx.zhimg.com/80/v2-ecca4d1352d9c4ebba833850e8736467_1440w.png?source=d16d100b)



![img](https://picx.zhimg.com/80/v2-5c59525a28f9bc91c5a6894f0224383a_1440w.png?source=d16d100b)



![img](https://picx.zhimg.com/80/v2-eadd742d6e25239c1f26f0bdf0467de1_1440w.png?source=d16d100b)

### 编程：

惊到我了！

以经典的求平方根为例：

太6了，还可以直接copy code！

![img](https://picx.zhimg.com/80/v2-13fc0ed86e4058dd1a091a6563af627f_1440w.png?source=d16d100b)



![img](https://pic1.zhimg.com/80/v2-dae0e296b84c61f94d8a28f74881d363_1440w.png?source=d16d100b)



![img](https://picx.zhimg.com/80/v2-878d5809668429557c91b5d61c77cc1b_1440w.png?source=d16d100b)

我让它从头实现，它不仅写出来了，甚至还有注释和解释！！！太强了！

必须得夸一夸：

![img](https://pica.zhimg.com/80/v2-7a7f0ff041ee54d750caf56eabe4e053_1440w.png?source=d16d100b)

### 娱乐：

我承认，我就是来找茬儿的QAQ。

娱乐圈的水太深，ChatGPT你把握不住啊！

![img](https://picx.zhimg.com/80/v2-8bbcb46bce672694045005e94fb04d54_1440w.png?source=d16d100b)

![img](https://pica.zhimg.com/80/v2-8aeac8f1cddeb9604324a5d995752738_1440w.png?source=d16d100b)



![img](https://picx.zhimg.com/80/v2-880a057f0e5683ac5332cf682ff9a809_1440w.png?source=d16d100b)

好了，前面笔者对ChatGPT进行了大概**十个方面**的高强度测试，高强度是指我自己哈，它是不会累的，我把自己聊累了~

## 4.总结及展望

### 总结：

其实逛网的总结就蛮全面的，ChatGPT的能力和限制：

![img](https://picx.zhimg.com/80/v2-50f004971c3784c3109c4a5dbc67d680_1440w.png?source=d16d100b)

**优点**：

- 整体效果惊艳，感觉带来了文本生成实用化的曙光
- 流畅性非常不错：对话、续写、敲代码~
- 多轮对话的能力有较大的提升
- 学会了拒绝
- 允许用户提供后续修正

**缺点**：

- 生成不正确或有害的信息：文本生成的老大难问题了
- 受限的知识：使用的是2021年之前的数据训练，无法对之后的情况进行很好的处理；部分领域表现一般，尤其是小众领域
- 生成结果偶尔会戛然而止
- 没有聚合搜索引擎：这个不算缺点其实，但我感觉可以结合

### 展望：

从扩散模型将AI绘画带入实用化水平开始，到各种扩散模型遍地开花，再到今年最后一个月突然冒头的ChatGPT为我们带来了文本实用化的曙光，这不得不让人感叹技术发展之快，或许今年真的是AIGC的元年！让我们拭目以待！

关于文本生成未来的方向：

个人感觉，主要是：更强的生成模型+更好的人类反馈机制+更多更好的数据+更好的评价指标，另外还要着重补短板。

**更强的生成模型**：

- 新的生成模型：VAE/GAN/扩散模型都更适合图像，NLG领域目前似乎就GPT系列最能打，能否更好的结合创造出一些复合模型或者全新的文本生成模型出来？
- 人类反馈：对话场景天生适合人类反馈，但像小说、摘要等场景如何更好的收集用户反馈？批注、弹幕或许是个不错的选择，但感觉远远不够。
- 更多更好的数据：OpenAI的数据向来是又多又好，羡煞旁人啊。
- 更好的评价指标：目前文本生成领域的很多评价指标还是偏字符成面的，像流畅性、合理性、正确性、逻辑性等指标是很难量化的，评价指标基本还是完全掌握在人类手里，这也是为何需要人类反馈的原因。
- 补短板：事实性错误、有害信息如何减少？

除此之外，当然还有很多事情可以做，一个很有想象空间的事情就是和传统的搜索引擎结合，生成模型+搜索引擎！前面我们在尝试的过程中，ChatGPT也说了自己不是搜索引擎，没有联网搜索的能力，但是这个真可以有！

这俩不是矛盾关系，而是可以相互结合相互促进的。华为前不久就发布了全球首个多语种权威知识检索生成模型——WebBrain。

https://www.sohu.com/a/602953833_121431682

生成模型+搜索引擎，或许可以实现所搜即所得。

当AIGC的实用性开始提升，其潜在的商业价值自然就会水涨船高，也许我们很快就将看到AIGC应用到各个领域并产生巨大的商业价值！

Let's play with AIGC! 

Let's chat with ChatGPT!

最后，我们让ChatGPT自己来展望一下文本生成的未来吧！

![img](https://picx.zhimg.com/80/v2-2262907ba8c592f1552559b6e86cfc32_1440w.png?source=d16d100b)

## 5.ChatGPT+X

*这部分内容为12.6号新增*

本文首次发布时就曾经谈到过ChatGPT+搜索引擎将会是一个非常有想象空间的方向，果然相关问题很快就在全网引发了热议。

https://www.zhihu.com/question/570062224/answer/2787787130

至于是否会取代[搜索引擎](https://www.zhihu.com/search?q=搜索引擎&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra={"sourceType"%3A"answer"%2C"sourceId"%3A2787787130})？答案是当然不会，二者不是竞争关系，但可以结合。

ChatGPT vs 搜索引擎：no！

**ChatGPT + 搜索引擎**：yes！

现在已经出现了**ChatGPT+Google**的扩展：

https://github.com/wong2/chat-gpt-google-extension

https://github.com/ZohaibAhmed/ChatGPT-Google

我们以第一个为例，展示一下此类扩展的使用指南：

首先安装扩展程序：

![img](https://pic1.zhimg.com/80/v2-81ccb8df59e861fd015e708c10cc87bd_1440w.png?source=d16d100b)

![img](https://picx.zhimg.com/80/v2-e2cb10a684ccfecf57b4a2deea6e823f_1440w.png?source=d16d100b)

这时打开Google搜索，随便搜个什么东西，比如chatgpt是什么，右侧会出现一个chatgpt相关的窗口，提醒你需要先登录，登录成功之后，你可以看到从chatgpt返回的结果！

![img](https://pica.zhimg.com/80/v2-8814a8d48f82013b0618a00d4adc2c6f_1440w.png?source=d16d100b)



**ChatGPT+Google，这实在是太酷了**！！！

已经出现了很多关于ChatGPT+X的扩展，包括vscode扩展、mac的扩展、聊天机器人等等。未来ChatGPT+X必将越来越多、越来越好，让我们拭目以待吧！

![img](https://picx.zhimg.com/80/v2-3f699b62a83071df30b5e2c4bdb34f15_1440w.png?source=d16d100b)

*注：AIGC真的是点燃了我久违的激情，周末玩儿了两天，不知不觉又到了凌晨。码字不易，如果觉得有用的话，***请多多支持***。最后的最后，一家之言，请谨慎参考~*

*20221217更新：经评论区提醒，中国信通院对ChatGPT做了一个比较全面的评测～*

https://mp.weixin.qq.com/s/fb09_kAVeBmkDs_ll9Y8vQ

20230130更新：ChatGPT新版提升了数学和事实性能力。https://mp.weixin.qq.com/s/wYhxr5_-LF0UXhBUEIDO-A

20230203更新：重新梳理了一下第2章的注册流程，现在更加清晰明了，大家可以根据自己的需求选择合适的方式来体验ChatGPT强大的能力。

20230206更新：补充了一份提问模板。

## 参考资料

https://openai.com/blog/chatgpt

https://www.zhihu.com/question/570189639

https://www.sohu.com/a/602953833_121431682

https://zhuanlan.zhihu.com/p/589005258

https://juejin.cn/post/7119267206847791134

https://zhuanlan.zhihu.com/p/461204074

