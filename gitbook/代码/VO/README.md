# Visual Odometer :

## initialize

### readPreFrame

读取第一帧,作为previous frame

### processImage

处理previous frame

### ExtractFeature

从previous frame中提取特征点

## readCurrFrame

读取新的一帧，作为current frame

## processImage

处理current frame

## ExtractFeature

从current frame 提取特征点

## MatchFeature

将previous frame提取的特征点与current frame提取的特征点进行特征匹配，得到match

## FilterMatches

对匹配结果(match)进行过滤

## EstimatePose

利用匹配结果(match)进行位姿估计

## OptimizePose

利用match和原始数据(彩色图&&深度图)优化位姿

## UpdateMap

利用计算位姿生成current frame的世界坐标系点云，并将点云融入到地图map中，以完成map的更新

## ReadPreFrame

读取第一帧,作为previous frame

## ProcessImage

处理previous frame

## ExtractFeature

从previous frame中提取特征点

## creatCurrFrame

利用previous frame和预先确定的方法生成current frame