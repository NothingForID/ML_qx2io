# 项目简介 Introduction
关于 谦行Aling (qx2io) 制作的《机器学习》系列视频的学习笔记以及复现代码  

> - 内容链接 Source:  
>   https://space.bilibili.com/291215958/lists/7468039  
> - 内容作者 Author:  
>   [谦行Aling](https://github.com/qx2io)  
> - 发布时间 Release:   
>   2026.02 - 2026.05

# 目录结构 Directory Structure
- [视频目录 Videos](https://space.bilibili.com/291215958/lists/7468039)
  1. [什么是智能，机器是怎么学会思考的](https://www.bilibili.com/video/BV13bZYBREgr/)
  2. [机器学习是什么：通过数据学习规律，对未来预测](https://www.bilibili.com/video/BV1BnZZBTEcL/)
  3. [机器学习类型：监督学习、非监督学习、强化学习](https://www.bilibili.com/video/BV1n3fzBsEu6/)
  4. [线性回归——机器学习的第一个模型](https://www.bilibili.com/video/BV1xrNGzrEJx/)
  5. [梯度下降——模型如何自己学会找最优参数](https://www.bilibili.com/video/BV1cpwuz7EgF/)
  6. [数据处理全攻略](https://www.bilibili.com/video/BV1cGA3zREMA/)
  7. [拟合前提——线性回归模型评估](https://www.bilibili.com/video/BV1nRXVBBEc4/)
  8. [欠拟合问题诊断与解决](https://www.bilibili.com/video/BV1Hb9EB9ESo/)
  9. [逻辑回归——最常用的分类模型](https://www.bilibili.com/video/BV1gZDVBUEqC/)
  10. [决策树——会 if...else 就能懂的机器学习算法](https://www.bilibili.com/video/BV1M8D7BWEVQ/)
  11. [随机森立——决策树模型升级版](https://www.bilibili.com/video/BV1NgQuBFEVY/)
  12. [集成学习之Boosting模型——XGBoost、LightGBM、CatBoost](https://www.bilibili.com/video/BV1QdQJBTEGV/)
  13. [K-Means 聚类](https://www.bilibili.com/video/BV17Nd5BrEQS/)
  14. [PCA 主成分分析，机器学习的最后一个模型](https://www.bilibili.com/video/BV1YMoDBuEm2/)
  15. [机器学习课程总结与深度学习展望](https://www.bilibili.com/video/BV1GsofB8Eej/)

- [文档目录 Documents](https://www.yuque.com/qx2io/machine-learning)
  1. [智能是什么、从何而来](https://www.yuque.com/qx2io/machine-learning/hc2wiugnucpryfgg)
  2. [什么是机器学习](https://www.yuque.com/qx2io/machine-learning/lw4ycvt11803qu84)
  3. [机器学习类型](https://www.yuque.com/qx2io/machine-learning/cfzp9g3uga9azcux)
  4. [线性回归](https://www.yuque.com/qx2io/machine-learning/ae9tduy1ixmry3yl)
  5. [梯度下降](https://www.yuque.com/qx2io/machine-learning/drrieqsqls94gz6n)
  6. [数据预处理](https://www.yuque.com/qx2io/machine-learning/qiiexxntlhcdklt2)
  7. [模型评估](https://www.yuque.com/qx2io/machine-learning/vcqzedxf0slg89sq)
  8. [欠拟合与过拟合](https://www.yuque.com/qx2io/machine-learning/xi3329io7sg1zor1)
  9. [逻辑回归](https://www.yuque.com/qx2io/machine-learning/ewwg2w1drdc460i5)
  10. [决策树](https://www.yuque.com/qx2io/machine-learning/nng8aecfuponryus)
  11. [随机森立](https://www.yuque.com/qx2io/machine-learning/rqfyegube8yg6tkh)
  12. [Boosting 模型](https://www.yuque.com/qx2io/machine-learning/bbldhagiyeszmnd0)
  13. [K-Means 聚类](https://www.yuque.com/qx2io/machine-learning/gt0x5gv29g7t4alv)  
  14. [PCA 降维](https://www.yuque.com/qx2io/machine-learning/dpyabrm468qh1z05)  
  15. [机器学习总结](https://www.yuque.com/qx2io/machine-learning/fucmye3a4q6di1bz)  

- 仓库结构
  ```
  ROOT
    ├─ environment.yml  # 复现代码所需的环境配置
    ├─ Note.md          # 学习笔记
    ├─ data             # 部分或需下载的数据集
    ├─ materials        # Note.md 内的图片素材
    └─ scripts          # 按章复现的 ipynb 脚本 
  
  ```

# 环境配置 Environment Setup
详见文件 [`environment.yml`](environment.yml)，主要内容如下
- `python 3.10`
- `matplotlib`
- `numpy`
- `pandas`
- `scikit-image`
- `scikit-learn`
- `scipy`
- `xgboost`

# 轻量指南 Simple Guide
- 快速开始
  ```
  git clone https://github.com/NothingForID/ML_qx2io.git
  cd ML_qx2io
  conda env create -f environment.yml -n aling
  conda activate aling
  conda env list
  ```

- 数据集加载
  1. `titanic.csv`  
    在章节数据预处理中，需要加载泰坦尼克的相关数据  
    如果无法下载，可以尝试科学上网  
    或者按需加载仓库文件 `./data/titanic.csv`  
      ```python
      import pandas as pd
      PATH = "../data/titanic.csv"
      df = pd.read_csv(PATH)
      ```

  2. `sklearn.datasets.fetch_california_housing`   
      在多个章节中，需要加载加利福尼亚房价的相关数据  
      如果无法下载，可以尝试科学上网  
      或者按需加载仓库文件 `./data/cal_housing.py3.pkz`  
      ```python
      # --- 1. 直接通过仓库路径加载数据 ---
      from sklearn.datasets import fetch_california_housing
      DIR = "../data"
      data = fetch_california_housing(data_home = DIR, download_if_missing=False)

      # --- 2. 手工将数据移动至默认路径 ---
      from sklearn.datasets import get_data_home
      print(get_data_home()) # 获取 SCIKIT_LEARN_DATA 路径
      ```
- 原作其他博客  
  https://juejin.cn/user/237150240001639/posts

- 欢迎留言讨论  
  若有复现问题或者学习心得，欢迎移步 [Discussions](https://github.com/NothingForID/ML_qx2io/discussions) 留言进行交流分享
  
