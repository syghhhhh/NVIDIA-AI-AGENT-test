# NVIDIA-AI-AGENT-test
2024年8月18日

AI-AGENT夏季训练营 — RAG智能对话机器人

## 项目概述

基于开源的embedding模型和大语言模型,使用es数据库搭建rag接口

## 技术方案与实施步骤

### 模型选择

embedding模型使用BAAI/bge-large-zh-v1.5

大模型使用qwen2:7b

### 数据构建

数据构建过程:

1. 文档读取之后分句,分块时token值超过512则结束这一分块,取overlap=0.25的句子放入下一个分块中

2. 进行分词,停用词去除

3. 调用BAAI/bge-large-zh-v1.5生成响应的向量并存储

### 实施步骤

#### 环境搭建 

docker安装 具体的库的版本在txt文件中

#### 代码实现

通过特征词和向量的混合评价找到超过阈值的相关存储块, 使用BAAI/bge-reranker-v2-m3重排之后送入大模型生成回复
![image](https://github.com/user-attachments/assets/f088a673-d0b0-4291-a77b-d11b35e33efb)

### 项目成果与展示
![image](https://github.com/user-attachments/assets/d30b4eaf-5491-4529-b334-5d5737dea19d)

![image](https://github.com/user-attachments/assets/81fe95d7-9176-4d6e-ba26-6dc09ea68f63)



