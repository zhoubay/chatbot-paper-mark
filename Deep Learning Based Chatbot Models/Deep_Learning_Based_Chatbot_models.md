# 论文阅读笔记【1】：基于深度学习的聊天机器人模型

## 一、文章相关情况

最近要做聊天机器人相关的项目，于是想找一些聊天机器人的综述文章。正好看到了这篇文章**基于深度学习的聊天机器人模型**（[Deep Learning Based Chatbot Models](https://arxiv.org/abs/1908.08835)），是2019年发布的，看起来还比较新，所以大概能代表最近的一些最新的研究进展，以下做一点小小的笔记。

## 二、摘要

- Modeling conversation是自然语言处理（NLP）和人工智能（AI）的一个重要的任务。
- 在过去，聊天机器人以来手写的规则、模板或者一些简单地统计学模型。

- 2015年左右这些模型被端对端可训练的神经网络（end-to-end trainable neural networks）取代。
- 循环编解码器模型（the recurrent encoder-decoder model [Cho et al., 2014]）主宰了对话模型（conversational modeling）任务。
- 那时起，a multitude of variations [Serban et al., 2016]和特征被提出，增强了聊天机器人产生的对话。
- 作者在阅读大量文献后认为，普通的对话领域需要不同于目前最新架构的方法。（the very nature of the general conversation domain demands approaches that are different from current state-of-art architectures.）
- 作者展示了为什么目前的聊天机器人模型在生成回答时难以考虑足够的前提（priors），以及这个如何影响对话的质量的。
- 在聊天机器人中，这些前提可能是一些对话依赖的外部信息，像聊天者的身份（persona）以及心情。（these priors can be outside sources of information that the conversation is conditioned on like the persona [Li et al., 2016a] or mood of the conversers.）
- 作者还会谈及最近的Transformer [Vaswani et al., 2017]在聊天机器人领域的应用。
- 作者使用的数据集是Cornell Movie-Dialog Corpus。
- 作者将问题视为一个编解码器来增强了初始的Transformer模型，作者增加了心情或者身份等信息到原对话数据中。
- 最后作者展示了一个很详细的分析，如何原始模型应用到对话数据。

## 三、论文目录

### 1 引入

### 2 聊天机器人的历史

#### 2.1 对话模型 

#### 2.2 早期的方法

#### 2.3 编解码模型

##### 2.3.1 循环神经网络

##### 2.3.2 Seq2seq模型

##### 2.3.3 深度Seq2seq模型

##### 2.3.4 解码和词汇

### 3 背景

#### 3.1 关于编解码模型更多的细节

##### 3.1.1 上下文

##### 3.1.2 目标方程

##### 3.1.3 评价方法

#### 3.2 对于编解码模型的增强

##### 3.2.1 注意力

##### 3.2.2 预训练

##### 3.2.3 附加的输入特征

##### 3.2.4 知识库和拷贝

#### 3.3 对对话模型不同的方法

##### 3.3.1 层级模型(Hierarchical Models)

##### 3.3.2 面向任务的对话系统

##### 3.3.3 强化学习

##### 3.3.4 不同的编解码模型

#### 3.4 讨论

##### 3.4.1 数据集

##### 3.4.2 损失函数

##### 3.4.3 内存

##### 3.4.4 评价度量

### 4 实验

#### 4.1  Transformer模型

##### 4.1.1 编解码网络

##### 4.1.2 注意力机制

##### 4.1.3 前向传播网络

##### 4.1.4 位置编码

##### 4.1.5 正则化和其他技巧

#### 4.2 数据集

##### 4.2.1 Cornell Movie-Dialog Corpus

##### 4.2.2 OpenSubtitles Corpus

#### 4.3 训练细节

##### 4.3.1 Tensor2Tensor

##### 4.3.2 Cornell Movie的训练

##### 4.3.3 带有说话者的Cornell Movie的训练

##### 4.3.4 OpenSubtitles训练

##### 4.3.5 用Cornell Movie数据微调后的OpenSubtitles训练

### 5 结果

#### 5.1 定量分析（Quantitative Analysis）

#### 5.2 定性分析（Qualitative Analysis）

### 6 将来的工作

#### 6.1 对于解决损失函数问题的想法

#### 6.2 时序调节以及内存（Temporal Conditioning and Memory）

#### 6.3 其他的想法

### 7 总结

## 四、论文正文

### 1、引入

- 首先
