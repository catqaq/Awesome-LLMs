大家好，我是羡鱼！

最近OpenAI又整了个新活儿，ChatGPT，效果惊艳的对话模型，已经快被脑洞大开的网友们玩儿坏了！闲聊、问答、写代码，你能想到的它都会！甚至有国外的网友表示，Google is done！另外夕小瑶小姐姐的公众号文章《[谷歌要完，百度也危了](mp.weixin.qq.com/s/qVt89FS_wzfu6-ShiWTv_Q)》也是直接将话题拉满，比较夸张，但也侧面说明了ChatGPT确实强啊！

这里我为大家准备了一份**ChatGPT的实践指南**，手把手教你Chat with ChatGPT!

先说结论，个人感觉**生成模型**+**RLHF**或许能为我们带来**文本生成实用化**的曙光！

本文脉络：首先简单介绍一下原理，然后手把手教大家如何注册OpenAI账号并开始与ChatGPT交流，随后会提供笔者在十个领域上与ChatGPT交流的示例，最后进行总结与展望。一起迎接AIGC的时代吧！

## 1.生成模型+RLHF

前两天还在有关扩散模型的帖子下面讨论着能不能将扩散模型的思想用到NLG领域（可能得做些改造或者与其他技术结合）来提升其实用性水平？

https://www.zhihu.com/question/568791838/answer/2781856167

没想到2号OpenAI又给大家整了个新活儿，ChatGPT，一个对话生成模型，效果看上去比较令人惊艳，已经被大家玩儿坏了。**生成模型**+**Reinforcement Learning From Human Feedback (RLHF)**，这路子感觉就很合理，人类对话基本就是这个路子啊（基于对方的反馈来对话）。我一直觉得，文本生成不仅需要新的强大的生成模型，还需要人类的反馈参与其中（尤其是对话这种交互式场景）。因为个人感觉文本生成与图像生成的最大的差异在于文本为人类专属，不具有自然界的对照，在生成效果上更难以评价，没有人类反馈的参与，无论是GAN、VAE，还是现在的扩散模型，或者是各种扩散模型的结合，再强大的生成模型在文本领域都会水土不服，只能是无根浮萍。

于是昨晚和朋友感叹到今年或许真是AIGC元年，AIGC开始从实验室水平走向实用水平，标志性的事件就是扩散模型将AI绘画带到了一个新的实用化的高度。而文本领域也开始有了像ChatGPT这样的曙光，我更加期待即将到来的GPT4了，也更加期待文本生成的实用化！

文本生成，道阻且长，大佬们赶紧卷起来啊QAQ！

## 2.手把手教你注册OpenAI

我已经迫不及待的想要先来看看ChatGPT到底表现如何了，但是openAI的服务不支持中国，GAN（一个模型）！

官网：

https://chat.openai.com/auth/login

注册：基本流程可以参考这篇博客，不过作者是在英国，咱们大陆注册会遇到很多问题。

https://zhuanlan.zhihu.com/p/589005258

注册账户：随便弄个邮箱或者就用Google、微软账号注册就行。然后可能会提示你OpenAI's services are not available in your country.

首先需要**学术上网**，顺利的话你会看到填写用户名的页面：

![image-20221204183045795](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221204183045795.png)

**最麻烦的部分**：需要国外的手机账号来注册和接收验证码。无奈之下，只好找国外的同学帮忙绑了一个账号。

注册成功后大概长这样：

![image-20221204233440752](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221204233440752.png)

那么除了找人帮忙，还有没有别的方式来获得国外电话进行OpenAI的注册呢？本着这么好的生意不可能没人做的想法，我大概搜了搜，现有几种方法可以尝试，但**最好找朋友帮忙**，**网上水太深，容易把握不住**！

#### （1）万能的淘宝

![image-20221204234056555](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221204234056555.png)

#### （2）Google/百度找找

有些博客上有相关教程了，B站上也有些视频教程。基本原理就是通过虚拟号来做电话验证，其中有些是免费的但是有很多人用，有些是收费的。

![image-20221204234801049](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221204234801049.png)

![image-20221204234226472](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221204234226472.png)

**免费的临时电话网站**，可能会有风险，请谨慎使用；另外，免费的最大问题就是大家都去薅羊毛，导致羊都被薅秃了，这些临时电话基本都很难注册成功，别问我怎么知道的（含泪猛试半小时）：

https://sms24.info/en/messages/OpenAI

https://jiemahao.com/

**收费的临时电话网站**，这种临时号同样可能会有风险，但毕竟拿钱办事儿。只试了这个，朋友推荐的，但还是要注意风险，请谨慎尝试。俄国人弄的网站，用卢布结算的，大家可以找便宜的国家激活，比如印度10.5卢布/次，也就是差不多0.17美元，大家可以看情况充值，但不建议超过1美元。

https://sms-activate.org/cn/getNumber

![image-20221204231806413](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221204231806413.png)

![img](https://pic2.zhimg.com/v2-4fb15f520be08d1fff11f9ed74353929_r.jpg)

这个接码平台的使用可以参考这个博客，这里就不多赘述了：

https://mirror.xyz/boxchen.eth/9O9CSqyKDj4BKUIil7NC1Sa1LJM-3hsPqaeW_QjfFBc

#### （3）直接购买OpenAI账号

简单省事儿，基本同淘宝，但是比淘宝便宜。

![image-20221204235658610](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221204235658610.png)



通过验证之后，页面长这样，基本上就大功告成了！

![image-20221204232425386](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221204232425386.png)

一点忠告：**电话验证稳妥起见最好找朋友帮忙或者走淘宝**。本文只是大概尝试了几种可行的电话验证的方式，并不构成建议，电话验证部分请谨慎尝试！！！否则，后果自负哈~

## 3.Chat with ChatGPT

Now, Let's chat with ChatGPT!

注册成功之后，我们回到chatgpt的测试页面：

https://chat.openai.com/chat

![image-20221205001318585](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205001318585.png)

在正式试用之前，我们先来看看ChatGPT的特性：

![image-20221205001650560](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205001650560.png)

Free Research Preview: **ChatGPT is optimized for dialogue.** Our goal is to make AI systems more natural to interact with, and your feedback will help us improve our systems and make them safer.

所以，多多试用，为chatgpt提供反馈吧，这样基于人类反馈的强化学习才能帮助GPT系列越来越强！

#### **哲学**：

咱先来点儿哲学问题：

可以看到效果相当不错啊，对于它不擅长的东西，还会巧妙的避开：

![image-20221205002149165](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205002149165.png)

![image-20221205002225317](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205002225317.png)

![image-20221205002434275](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205002434275.png)

![image-20221205002542113](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205002542113.png)

#### 世界杯：

再来点儿世界杯问题：

可惜ChatGPT是基于21年之前的数据训练的，无法回答，但就是这种拒绝回答已经是非常大的进步了。

![image-20221205002705072](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205002705072.png)

![image-20221205002853215](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205002853215.png)

![image-20221205002952091](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205002952091.png)

#### 爱情：

![image-20221205003103556](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205003103556.png)

![image-20221205003225361](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205003225361.png)

![image-20221205003653663](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205003653663.png)

![image-20221205003944207](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205003944207.png)

#### 文学：

牛啊！效果真的出乎我的预料！至少，辅助写作是用的上的！

![image-20221205004148884](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205004148884.png)

![image-20221205004252637](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205004252637.png)

![image-20221205004400942](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205004400942.png)

![image-20221205004626561](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205004626561.png)

#### 政治军事：

![image-20221205004828922](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205004828922.png)

![image-20221205005010092](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205005010092.png)

![image-20221205005113527](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205005113527.png)

#### 经济：

![image-20221205005241946](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205005241946.png)

![image-20221205005356240](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205005356240.png)

#### 教育：

![image-20221205005505239](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205005505239.png)

![image-20221205005615607](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205005615607.png)

#### 科技：

偶尔会遇到生成内容戛然而止的情况。

但是效果再次令人惊艳，**甚至可以解释GPT和transformer的原理**！我有一个大胆的想法，面试不会了说不定可以问问它！

![image-20221205005804578](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205005804578.png)

![image-20221205010022258](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205010022258.png)

![image-20221205010211891](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205010211891.png)

![image-20221205010338968](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205010338968.png)

#### 编程：

惊到我了！

以经典的求平方根为例：

太6了，还可以直接copy code！

![image-20221205010730137](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205010730137.png)

![image-20221205010919948](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205010919948.png)

![image-20221205010957606](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205010957606.png)

我让它从头实现，它不仅写出来了，甚至还有注释和解释！！！太强了！

必须得夸一夸：

![image-20221205011218402](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205011218402.png)

#### 娱乐：

我承认，我就是来找茬儿的QAQ。

娱乐圈的水太深，ChatGPT你把握不住啊！

![image-20221205011437674](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205011437674.png)

![image-20221205011523144](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205011523144.png)

![image-20221205011719548](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205011719548.png)

好了，前面笔者对ChatGPT进行了大概**十个方面**的高强度测试，高强度是指我自己哈，它是不会累的，我把自己聊累了~

## 4.总结及展望

#### 总结：

其实逛网的总结就蛮全面的，ChatGPT的能力和限制：

![image-20221205012604678](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205012604678.png)

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



#### 展望：

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

![image-20221205020910257](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221205020910257.png)

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

![image-20221206233117005](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221206233117005.png)

![image-20221206233032867](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221206233032867.png)

这时打开Google搜索，随便搜个什么东西，比如chatgpt是什么，右侧会出现一个chatgpt相关的窗口，提醒你需要先登录，登录成功之后，你可以看到从chatgpt返回的结果！

![image-20221206233237330](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221206233237330.png)

**ChatGPT+Google，这实在是太酷了**！！！

已经出现了很多关于ChatGPT+X的扩展，包括vscode扩展、mac的扩展、聊天机器人等等。未来ChatGPT+X必将越来越多、越来越好，让我们拭目以待吧！

![image-20221206233732297](https://xianyunlp.oss-cn-hangzhou.aliyuncs.com/uPic/image-20221206233732297.png)

*注：AIGC真的是点燃了我久违的激情，周末玩儿了两天，不知不觉又到了凌晨。码字不易，如果觉得有用的话，**请多多支持**。最后的最后，一家之言，请谨慎参考~*

## 参考资料

https://openai.com/blog/chatgpt/

https://www.sohu.com/a/602953833_121431682

https://juejin.cn/post/7119267206847791134

https://zhuanlan.zhihu.com/p/589005258

https://www.zhihu.com/question/570189639

https://zhuanlan.zhihu.com/p/461204074

https://mirror.xyz/0x6E12A28086548B11dfcc20c75440E0B3c10721f5/9O9CSqyKDj4BKUIil7NC1Sa1LJM-3hsPqaeW_QjfFBc

