# algo

将将整个三维重建(目前仅有视觉里程计)处理流程拆解成若干独立模块，每个模块均可自由选择具体的实现算法，例如”ExtractFeature“模块可选择的具体实现算法有：ORB，SIFT，SUFT。这样做的好处是方便进行算法组合测试，也容易添加新的算法。

### processImage

第一步：图片预处理算法

- cutImage

  剪切图片

### ExtractFeature

第二步：特征点提取算法

- ORB
- SIFT
- SURT

### matchFeature

第三步：特征匹配算法

- BFM
- flann

### FilterMatches

第四步：匹配筛选算法

- None

  不筛选

- GMS

- RANSAC

- maxDis

  剔除距离高于阈值(可配置)的匹配

### OptimizePose

第六：位姿优化算法

- None

  不适用任何方法，即使用给定的初始位姿作为估计结果

- sparse3D3D

  利用稀疏点云(仅特征点)配准误差优化位姿 (使用g2o实现图优化)

- sparse3D2D

  利用稀疏点云(仅特征点)重投影误差优化位姿 (使用g2o实现图优化)

- dense3D3D

  ICP

### EstimatePose

第五步：位姿估计算法

- None

  不使用任何方法，即使用给定的初始位姿作为估计结果

- 3D3DSVD

  将三维特征点匹配对带入观测方程，并利用SVD分解求解出估计位姿

- 3D2DPnp

  pnp(opencv接口)

- 3D2DPnpRansac

  pnp+ransac(opencv接口)

## 