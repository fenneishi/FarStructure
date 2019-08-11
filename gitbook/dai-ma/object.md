# object

数据结构

## Camera

管理相机数据

* colorM

  彩色相机内参

* DepthM

  深度相机内参

* d2c

  相机外参：深度相机到彩色相机的转换矩阵

## Frame

管理每一帧数据

* color

  彩色图

* depth

  深度图

* regisColor

  经过processImage模块处理过后，用于位姿估计和位姿优化的彩色图

* regisDepth

  经过processImage模块处理过后，用于位姿估计和位姿优化的深度图

* realT

  当前帧相对上一帧的真实转换矩阵：若当前帧是由creatCurrFrame生成的，则可得到具体的realT,否则自动置为单位矩阵

* realPose

  当前帧真实位姿：若当前帧是由creatCurrFrame生成的，则可得到具体的realPose,否则自动置为单位矩阵

* estimatedT

  当前帧相对上一帧的估计转换矩阵：由EstimatePose和OptimizePose模块计算得出.

* estimatedPose

  估计位姿：由EstimatePose和OptimizePose模块计算得出.

* readFrame\(\)

  重要接口：从硬盘中读取1张彩色图和1张深度图作为新的一帧

  * preprocessColor\(\)

    读取时需要对彩色图做一些预处理，例如通道转换

    * regis:changeChannel \(\)

      通道转换

  * preprocessDepth\(\)

    读取时需要对彩色图做一些预处理，例如深度图对齐到彩色图

    * regis:depth2color\(\)

      深度图对齐到彩色图

* creatFrame\(\)

  重要接口：利用previous frame和预先确定的方法生成current frame

## Feature

管理每一帧的特征点数据

* kps

  特征点\(std::vector\)

* desp

  描述子

* keyPointsUV

  经过FilterMatches模块筛选后的特征点的2D形式\(std::vector&lt;\(cv::Point2f&gt;\)

* keyPointsXYZ

  经过FilterMatches模块筛选后的特征点特征点3D形式\(std::vector\)

## Match

管理相邻两帧特征匹配结果

* matches

  匹配结果\(std::vector\)

## Map

管理全局点云

* cloud

  点云

* addPoints\(\)

  重要接口：向点云中添加特征点

_XMind: ZEN - Trial Version_

