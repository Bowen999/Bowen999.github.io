# DDI入门笔记
Key Word：DDI，Transformers，CNN，BERT

# 常见概念
molecular fingerprint（分子指纹）：The molecular fingerprint is a way to describe a molecular structure that can convert a molecular structure into a bit string 

# 描述经典workflow的论文
PMID：[33098410](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8289381/)
基本思路：从文献和数据库中获取药物描述和分子结构，用于预测药物间的相互作用。

## 模型
数据来源：数据库中的药物描述和分子结构信息
预训练：Bidirectional Encoder Representations from Transformers (BERT)
baseline model：CNN based DDI extraction model
药物描述的获取：SciBERT（无监督预训练）
分子结构：GNN

## DDI label：
mechanism（药代动力学机制）
effect
advice（同时使用的建议）
interaction(只提到了interaction，没有说明详细信息）
negative

## Workflow
文本中提取信息——输入的句子用contexualized embeddings表示——从数据库中获得目标药物信息——用BERT和CNN表示药物描述——用GNN表示分子结构——Training——Ensemble——评估

## 评估
precision (P)
recall (R)
F-score (F)
