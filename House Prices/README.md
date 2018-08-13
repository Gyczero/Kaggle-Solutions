##问题背景
Kaggle ：https://www.kaggle.com/c/house-prices-advanced-regression-techniques

问题描述：根据房屋的不同信息预测放假

数据源：

	数据量：
	
	训练集：1468
	预测数据：1459
	特征数：79个特征


得分情况：

分数评估指标：RSME

阶段| 方法      |    Score
:--| :-------- | --------:
S1| 基础机器学习框架搭建,采用PCA降维，采用Random Forest | 0.21863
S2| 去除PCA     |   0.18129	
S3| Xgboost+所有特征      |    0.14339
S4 | 特征：（采用同目标变量相关性强的数值特征 + Label coder所有类别特征 + 对数处理目标变量） | 0.14628
S5 | 特征：部分**数值**特征转化为类别特征（Msubclass等）| 0.13902
S6 | 特征：部分**类别**特征Label coder，部分独热编码 | 0.13814
S7 | 特征：处理倾斜特征和目标变量 | 0.13811
S8 | 特征：部分类别特征缺失值采用众数 | 0.13806
S9 | Xgboost调参 | 0.12979
S10 | stacking集成方法 | 0.11512（Top 5%）

