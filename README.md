# Wechat Big Data competition - Baseline（Pytorch）

代码实现基于[DeepCTR](https://github.com/shenweichen/DeepCTR-Torch)

## 1.环境配置
- python3
- torch 1.6
- deepctr-torch 0.2.6
- pandas 1.0.1
- scikit-learn 0.22.1

## 2.数据集

#### 原始数据集
1. user_action.csv: 用户行为表
2. feed_info.csv: Feed信息表
3. feed_embeddings.csv: Feed向量表
4. test_a.csv: A榜测试集
5. submit_demo_初赛a.csv: A榜提交结果demo

####生成数据集
1. train_data_for_click_avatar.csv
2. train_data_for_forward.csv
3. train_data_for_like.csv
4. train_data_for_read_comment.csv
5. test_data.csv

## 2.运行配置
- CPU/GPU均可
- 最小内存要求
  - 特征/样本生成：6G
  - 模型训练及评估：4G

## 3.目录结构
- prepare_data.py 数据集生成
- baseline.py: 模型训练，评估，提交

## 4.运行流程
- 新建data目录，下载比赛数据集，放在data目录下并解压，得到wechat_algo_data1目录
- 数据集生成：运行prepare_data.py
- 模型训练，评估，提交：运行baseline.py

## 5.模型及参数
模型：DeepFM

参数：
batch_size: 512

optim: Adagrad

num_epochs: 5

learning_rate: 0.1


## 6.模型结果
我的线下验证集评价指标还没有改成和官网一致的方法，所以参考意义不大，需要大家重写评估方法

线上：
| weight_uauc | read_comment | like    | click_avatar | forward  |
| ----------- | ------------ | ------- | ------------ | -------- |
| 0.640712    | 0.624132     | 0.61151 | 0.705983     | 0.664097 |

## 7.相关文献
Guo H, Tang R, Ye Y, et al. Deepfm: a factorization-machine based neural network for ctr prediction[J]. arXiv preprint arXiv:1703.04247, 2017.
