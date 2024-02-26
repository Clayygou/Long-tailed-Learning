
# Long-tailed-Learning
Summary of the long-tailed learning algorithms
## Ensemble Learning(Mixture-of-Experts)
#### 1. LONG-TAILED RECOGNITION BY ROUTING DIVERSE DISTRIBUTION-AWARE EXPERTS（2020）[here](https://blog.csdn.net/weixin_41246832/article/details/126959807?spm=1001.2014.3001.5501)

提出了一个多专家的方法RIDE：采用多个专家来减少模型方差，并采用额外的分布多样性损失来减少模型偏差。并设计了一个专家分配模块来判断每一个样本需要多少个专家参与。

#### 2. Learning From Multiple Experts: Self-paced Knowledge Distillation for Long-tailed Classificatio（2020）

## Decouple
#### 1. Improving Calibration for Long-Tailed Recognition （2021）[For detailed](https://blog.csdn.net/weixin_41246832/article/details/127335796?spm=1001.2014.3001.5501)

引入了Expected calibration error的概念，通过在第一阶段使用mixup和LAS标签平滑可以有效地减低ECE。并在第二阶段只训练BN缓解两阶段数据的分布差异。

## Multi-Label Text Classification
#### 1. Does Head Label Help for Long-Tailed Multi-Label Text Classification (2021)

HTTN能够有效地检测从少量样本学习到大量样本学习的模型转换策略（即关于学习的元知识）在头标签上的表现。借助元知识和头尾标签之间的标签依赖关系，HTTN能够高效地构建尾标签的分类器(数据集 AAPD、RCV1、EUR-Lex)。
#### 2. Balancing Methods for Multi-label Text Classification with Long-Tailed Class Distribution (2021)

在文本分类问题上引入了 FL、CB、DB三种loss（Reuters-21578、PubMed）。

#### 3. Meta-LMTC: Meta-Learning for Large-Scale Multi-Label Text Classification (2021)

第一个元学习框架（MIMIC-III、EURLEX57K，包含zero-shot数据）。

## Long-Tailed semi-supervised Learning
#### 1. SimPro: A Simple Probabilistic Framework Towards Realistic Long-Tailed Semi-Supervised Learning (2024)

框架以概率模型为基础，通过显式地解耦条件和边际类分布的建模，创新地改进了期望最大化(EM)算法。并且无需预先假设无标签数据的分布情况。（图像的半监督数据集）

## Relation Extraction
#### 1. Learning Relation Prototype from Unlabeled Texts for Long-tail Relation Extraction (2023)


## Graph Classification

#### 1. Towards Long-Tailed Recognition for Graph Classification via Collaborative Experts(2023)

#### 2. Characterizing Long-Tail Categories on Graphs(2023)


## Scene Text Recognition
#### 1. Improving Scene Text Recognition for Character-Level Long-Tailed Distribution(2023)


## Recommend
#### 1. Empowering Long-tail Item Recommendation through Cross Decoupling Network (2023 kDD)
