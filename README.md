
# Long-tailed-Learning
Summary of the long-tailed learning algorithms
## Ensemble Learning(Mixture-of-Experts)
#### 1. LONG-TAILED RECOGNITION BY ROUTING DIVERSE DISTRIBUTION-AWARE EXPERTS（2020）[here](https://blog.csdn.net/weixin_41246832/article/details/126959807?spm=1001.2014.3001.5501)

提出了一个多专家的方法RIDE：采用多个专家来减少模型方差，并采用额外的分布多样性损失来减少模型偏差。并设计了一个专家分配模块来判断每一个样本需要多少个专家参与。

#### 2. Learning From Multiple Experts: Self-paced Knowledge Distillation for Long-tailed Classification（2020）

首先作者提出了评价“长尾性”的4个指标，发现将整体数据划分为更小的邻接子集会减少长尾性。所以作者设计了多个小数据集上的专家模型共同指导一个学生模型（软蒸馏），并通过自定进度的专家选择控制学生模型从每个专家上的学习程度。并设计了curriculum instance selection，让模型从简单到难逐步学习样本。

#### 3. Nested Collaborative Learning for Long-Tailed Visual Recognition（2022）

在表征学习中加入了自监督训练，之后设计了嵌套的个体学习和平衡的在线蒸馏，前者注重模型本身的学习，后者则是模型之间互相学习。两个阶段都通过使用全体样本和困难样本的两种方式嵌套学习。
## Contrastive Learning
#### 1. Balanced Contrastive Learning for Long-Tailed Visual Recognition (2023)

提出了平衡的有监督对比学习方法，网络包含了分类分支和对比学习分支，最后使用Logit Compensation优化输出。对同一张图片做三种不同的数据增强，同时输入模型，第一张得到使用logit compensation修改的CE loss，并对第一张的logit通过MLP非线性转换作为Prototype加入到和二三张图片的对比损失中。
#### 2. Contrastive Learning based Hybrid Networks for Long-Tailed Image Classification (2021)

针对对比学习内存问题，提出了prototypical supervised contrastive来减少内存。使用双分支框架从注重对比学习损失慢慢转移到分类损失。
#### 3. Self Supervision to Distillation for Long-Tailed Visual Recognition (2021)

提出了自监督、解耦、类别采样和蒸馏结合的4步框架。
#### 4. EXPLORING BALANCED FEATURE SPACES FOR REPRESENTATION LEARNING (2021)

自监督的对比学习，使用k个正样本集合代替增强的样本（KCL）。
#### 5. Targeted Supervised Contrastive Learning for Long-Tailed Recognition (2022)

Targeted supervised contrastive learning (TSC)，离线计算每个类别中心点位置，在训练中动态分陪每个样本。
#### 6. Prototype calibration for long tailed recognition (2023)

基于prototype的对比损失和特征增强。分类ce损失加上原型和从分类器得到的中心点之间的损失（和BCL相似），利用和尾部距离相近的头部原型数据增强尾部，使用Tukey’s Ladder of Powers transformation。

## Decouple
#### 1. Improving Calibration for Long-Tailed Recognition （2021）[For detailed](https://blog.csdn.net/weixin_41246832/article/details/127335796?spm=1001.2014.3001.5501)

引入了Expected calibration error的概念，通过在第一阶段使用mixup和LAS标签平滑可以有效地减低ECE。并在第二阶段只训练BN缓解两阶段数据的分布差异。

#### 2. Label-Aware Distribution Calibration for Long-Tailed Classification (2021,2024)

假设: 1.尾部分布可以从相似的头部类别中增强 2.相似的类别有相似的方差\均值

(LADC) method 观察到头部尾部类别的相似性. 第一阶段先训练 、第二阶段用最相似的m个头部类计算均值和方差用于更新尾部样本，应用采样技术提升分类器的能力，最后改进了lws-plus。

## Multi-Label Text Classification
#### 6. Label-aware Document Representation via Hybrid Attention for Extreme Multi-Label Text Classification (2019)

多标签的注意力机制来检测每个词对标签的贡献，交互的注意力机制来整合标签的共现性和文档内容，最后设计自适应的融合策略。

#### 1. Does Head Label Help for Long-Tailed Multi-Label Text Classification (2021)

HTTN能够有效地检测从少量样本学习到大量样本学习的模型转换策略（即关于学习的元知识）在头标签上的表现。借助元知识和头尾标签之间的标签依赖关系，HTTN能够高效地构建尾标签的分类器(数据集 AAPD、RCV1、EUR-Lex)。
#### 2. Balancing Methods for Multi-label Text Classification with Long-Tailed Class Distribution (2021)

在文本分类问题上引入了 FL、CB、DB三种loss（Reuters-21578、PubMed）。

#### 3. Meta-LMTC: Meta-Learning for Large-Scale Multi-Label Text Classification (2021)

第一个元学习框架（MIMIC-III、EURLEX57K，包含zero-shot数据）。
#### 4. Label-Specific Feature Augmentation for Long-Tailed Multi-Label Text Classification （2023）

普通的增强方法会加剧长尾现象，所以采用为尾部标签增加正特征标签对的方法。具体分类解耦的特征表征学习阶段和头到尾的特征增强阶段。
采用了label-specific encoder 和 prototypical 监督对比学习和Prototype-based Variational Autoencoder的增强方法。（AAPD RCV1 ERU_LEX）
## Semi-supervised Learning
#### 1. SimPro: A Simple Probabilistic Framework Towards Realistic Long-Tailed Semi-Supervised Learning (2024)

框架以概率模型为基础，通过显式地解耦条件和边际类分布的建模，创新地改进了期望最大化(EM)算法。并且无需预先假设无标签数据的分布情况。（图像的半监督数据集）

## Classifiers

#### 1.Learning Prototype Classifiers for Long-Tailed Recognition （2023）

通过使用到prototypes的距离作为logit scores来分类。

## Re-weighting(Loss)
#### 1. Curricular-balanced long-tailed learning (2024)

从Neural Collapse phenomenon出发，设计了CurB loss （Curricular Balanced Loss）。
## Mutual Information
#### 1. Mutual Learning for Long-Tailed Recognition


通过互信息框架，生成高质量的representation。推理时使用Post-Compensated Softmax。
#### 2. Long-Tailed Recognition by Mutual Information Maximization between Latent Features and Ground-Truth Labels

对比学习的本质是 ： 最大化潜在特征和输入数据的互信息。
长尾任务需要的是：最大化潜在特征和标签之间的互信息。

## Relation Extraction
#### 1. Learning Relation Prototype from Unlabeled Texts for Long-tail Relation Extraction (2023)


## Graph Classification

#### 1. Towards Long-Tailed Recognition for Graph Classification via Collaborative Experts(2023)

#### 2. Characterizing Long-Tail Categories on Graphs(2023)


## Scene Text Recognition
#### 1. Improving Scene Text Recognition for Character-Level Long-Tailed Distribution(2023)


## Recommend
#### 1. Empowering Long-tail Item Recommendation through Cross Decoupling Network (2023 kDD)

## Federated Learning 
#### 1. Federated Learning on Heterogeneous and Long-Tailed Data via Classifier Re-Training with Federated Features (2022)

#### 2、https://github.com/harrylee999/CRFDC/tree/main


#### 3、A federated learning method based on class prototype guided classifier for long-tailed data （2024）

1. **类原型引导的分类器重训练**：2. **全局原型的冻结机制**：防止头部过拟合

解耦方法用在联邦学习

## Distilling Long-tailed Datasets

#### 1、 Distilling Long-tailed Datasets （2024）

蒸馏长尾数据集

## Skeleton Based Action Recognition

[Shap-Mix: Shapley Value Guided Mixing for Long-Tailed Skeleton Based Action Recognition ](https://github.com/JHang2020/Shap-Mix?tab=readme-ov-file) 2024

## plug and play

#### 1、Escaping Saddle Points for Effective Generalization on Class-Imbalanced Data

锐度感知最小化(SAM)，一种鼓励收敛到平坦最小值的最新技术，可以有效地用于逃避少数类的鞍点。
