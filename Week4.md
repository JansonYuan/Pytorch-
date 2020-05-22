# PyTorch框架班 

## 🎯Week 4

### 🛴【任务1】

**任务名称：**  
权值初始化；损失函数（一）

**任务简介：**  
学习权值初始化的原理；介绍损失函数、代价函数与目标函数的关系，并学习交叉熵损失函数

**详细说明：**  
本节第一部分讲解权值初始化的必要性，首先分析神经网络中权值的方差过大导致梯度爆炸的原因，然后从方差一致性原则出发分析Xavier初始化方法与Kaiming初始化方法的由来，最后介绍pytorch提供的十种初始化方法。

本节第二部分介绍损失函数、代价函数与目标函数的联系与不同之处，然后学习人民币二分类任务中使用到的交叉熵损失函数，在讲解交叉熵损失函数时补充分析自信息、信息熵、相对熵和交叉熵之间的关系，最后学习四种损失函数：
1. nn.CrossEntropyLoss
2. nn.NLLLoss
3. nn.BCELoss
4. nn.BCEWithLogitsLoss

**作业名称（详解）：**  
1. Lossfunction依旧属于网络层的概念，即仍旧是Module的子类，为了对lossfunction有一个更清晰的概念，需要大家采用步进(Step into)的调试方法从loss_functoin = nn.CrossEntropyLoss()  语句进入函数，观察从nn.CrossEntropyLoss()到class Module(object)一共经历了哪些类，记录其中所有进入的类及函数。
例如：  
第一步：CrossEntropyLoss类，super(CrossEntropyLoss, self).__init__  
第二步：……  
第三步：……  
第n步：进入Module 类 

2. 损失函数的reduction有三种模式，它们的作用分别是什么？
当inputs和target及weight分别如以下参数时，reduction=’mean’模式时，loss是如何计算得到的？
inputs = torch.tensor([[1, 2], [1, 3], [1, 3]], dtype=torch.float)
target = torch.tensor([0, 1, 1], dtype=torch.long)
weights = torch.tensor([1, 2], dtype=torch.float）
- 本节代码下载：
🥛[模型构建步骤与nn.Module](https://github.com/JansonYuan/Pytorch-Camp/blob/master/%E4%BB%A3%E7%A0%81%E5%90%88%E9%9B%86/03-01-%E4%BB%A3%E7%A0%81-%E6%A8%A1%E5%9E%8B%E5%88%9B%E5%BB%BA%E6%AD%A5%E9%AA%A4%E4%B8%8Enn.Module/lesson-10-create_module.py)
🍸[模型容器与AlexNet](https://github.com/JansonYuan/Pytorch-Camp/blob/master/%E4%BB%A3%E7%A0%81%E5%90%88%E9%9B%86/03-02-%E4%BB%A3%E7%A0%81-%E6%A8%A1%E5%9E%8B%E5%AE%B9%E5%99%A8%E4%B8%8EAlexNet%E6%9E%84%E5%BB%BA/lesson-11-module_containers.py)
- 本节课件下载：
🥛[模型构建步骤与nn.Module](https://github.com/JansonYuan/Pytorch-Camp/blob/master/%E8%AF%BE%E4%BB%B6%E5%90%88%E9%9B%86/03-01-ppt--%E6%A8%A1%E5%9E%8B%E5%88%9B%E5%BB%BA%E6%AD%A5%E9%AA%A4%E4%B8%8Enn.Module.pdf)
🍸[模型容器与AlexNet](https://github.com/JansonYuan/Pytorch-Camp/blob/master/%E8%AF%BE%E4%BB%B6%E5%90%88%E9%9B%86/03-02-ppt-%E6%A8%A1%E5%9E%8B%E5%AE%B9%E5%99%A8%E4%B8%8EAlexNet%E6%9E%84%E5%BB%BA.pdf)
### 🛴【任务2】

**任务名称：**  
pytorch的14种损失函数；优化器optimizer的概念

**任务简介：**  
学习pytorch中剩下的14种损失函数；学习优化器optimizer的基本属性、基本方法和作用。

**详细说明：**  
本节第一部分学习pytorch的另外14种损失函数：
5. nn.L1Loss
6. nn.MSELoss
7. nn.SmoothL1Loss
8. nn.PoissonNLLLoss
9. nn.KLDivLoss
10. nn.MarginRankingLoss
11. nn.MultiLabelMarginLoss
12. nn.SoftMarginLoss
13. nn.MultiLabelSoftMarginLoss
14. nn.MultiMarginLoss
15. nn.TripletMarginLoss
16. nn.HingeEmbeddingLoss
17. nn.CosineEmbeddingLoss
18. nn.CTCLoss
本节第二部分学习优化器的基本概念，了解pytorch中optimizer的基本属性和方法 

**作业名称（详解）：**  
1. 总结所学习的18种损失函数，制作思维导图或总结表等

- 本节代码下载：
🍨[nn网络层-卷积层](https://github.com/JansonYuan/Pytorch-Camp/tree/master/%E4%BB%A3%E7%A0%81%E5%90%88%E9%9B%86/03-03-%E4%BB%A3%E7%A0%81-nn%E7%BD%91%E7%BB%9C%E5%B1%82-%E5%8D%B7%E7%A7%AF%E5%B1%82)
🍩[nn网络层-池化-线性-激活函数](https://github.com/JansonYuan/Pytorch-Camp/tree/master/%E4%BB%A3%E7%A0%81%E5%90%88%E9%9B%86/03-04-%E4%BB%A3%E7%A0%81-nn%E7%BD%91%E7%BB%9C%E5%B1%82-%E6%B1%A0%E5%8C%96-%E7%BA%BF%E6%80%A7-%E6%BF%80%E6%B4%BB%E5%87%BD%E6%95%B0)
- 本节课件下载：
🍨[nn网络层-卷积层](https://github.com/JansonYuan/Pytorch-Camp/blob/master/%E8%AF%BE%E4%BB%B6%E5%90%88%E9%9B%86/03-03-ppt-nn%E7%BD%91%E7%BB%9C%E5%B1%82-%E5%8D%B7%E7%A7%AF%E5%B1%82.pdf)
🍩[nn网络层-池化-线性-激活函数](https://github.com/JansonYuan/Pytorch-Camp/blob/master/%E8%AF%BE%E4%BB%B6%E5%90%88%E9%9B%86/03-04-ppt-nn%E7%BD%91%E7%BB%9C%E5%B1%82-%E6%B1%A0%E5%8C%96-%E7%BA%BF%E6%80%A7-%E6%BF%80%E6%B4%BB%E5%87%BD%E6%95%B0.pdf)

### 🛴【任务3】

**任务名称：**  
torch.optim.SGD

**任务简介：**  
学习最常用的优化器， optim.SGD

**详细说明：**
深入了解学习率和momentum在梯度下降法中的作用，分析LR和Momentum这两个参数对优化过程的影响，最后学习optim.SGD以及pytorch的十种优化器简介。

**作业名称（详解）：** 
1. 优化器的作用是管理并更新参数组，请构建一个SGD优化器，通过add_param_group方法添加三组参数，三组参数的学习率分别为 0.01， 0.02， 0.03， momentum分别为0.9, 0.8, 0.7，构建好之后，并打印优化器中的param_groups属性中的每一个元素的key和value（提示：param_groups是list，其每一个元素是一个字典）