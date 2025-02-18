# 配置

## 配置文件路径

\[工程主目录\]/file/parameters.txt

## 配置文件内容

* vo参数

```text
#开始帧
startIndex=0

#结束帧
endIndex=1

#VO运行类型
voType=read
#read:逐帧读取
#creat:生成帧)
```

* test参数

```text
# mix测试结果保存位置
mixDir=/Users/longqi/Desktop/project/data/goodScanSlam/FarStructure/tuyang1/mix/
```

* object参数

```text
# camera参数
    # 相机参数文件所在文件夹
  calib_find_dir=/Users/longqi/Desktop/project/data/goodScanSlam/FarStructure/tuyang1/camera/
    # 相机参数文件名
    calib_find_preName=calib
    # 相机参数文件名后缀
    calib_find_extName=.txt
```

```text
    # 相机参数文件格式：内参是否是先rgb后depth
    Interior_rgbThenDepth=true
    # 相机参数文件格式：外参是否是depth2rgb
    Extrinsic_depth2rgb=false
```

```text
# frame参数
    # readFream:读取图片时相关参数
        # rgb
            # color图所在文件夹
            rgb_read_dir=/Users/longqi/Desktop/project/data/goodScanSlam/FarStructure/tuyang1/frame/
            # color图文件名前半部分(固定部分)
            rgb_read_preName=color
            # color图文件名后半部分(变化部分)
            rgb_read_formatName=%5i
            # color图文件名后缀(文件格式)
            rgb_read_extName=.png

        # depth
            # depth图所在文件夹
            depth_read_dir=/Users/longqi/Desktop/project/data/goodScanSlam/FarStructure/tuyang1/frame/
            # depth图文件名前半部分(固定部分)
            depth_read_preName=depth
            # depth图文件名后半部分(变化部分)
            depth_read_formatName=%5i
            # depth图文件名后缀(文件格式)
            depth_read_extName=.png
    # creatFream:生成图片时候相关参数
        # 角度，单位是°
        angle=45
        # 半径，单位mm
        r=700

# matches参数
    #before filter:筛选前
        #  matches结果保存位置
        matches_save_dir=/Users/longqi/Desktop/project/data/goodScanSlam/FarStructure/tuyang1/match/
        #  matches结果文件名
        matches_save_preName=MatchesBeforeFilter
        #  matches结果文件后缀
        matches_save_extName=.jpg
    #after filter:筛选后
         #  matches结果保存位置
        matches_filter_save_dir=/Users/longqi/Desktop/project/data/goodScanSlam/FarStructure/tuyang1/match/
        #  matches结果文件名
        matches_filter_save_preName=MatchesAfterFilter
        #  matches结果文件后缀
        matches_filter_save_extName=.jpg
# map参数
    #  map结果保存位置
    map_save_dir=/Users/longqi/Desktop/project/data/goodScanSlam/FarStructure/tuyang1/map/
    #  map结果文件名
    map_save_preName=map
    #  map结果文件后缀
    map_save_extName=.pcd
    #  map文件尺度
    map_CoordinateSystem_scale=1
```

* step参数

```text
# processImage参数
    # 是否进行图片剪切
    ifCut=true
    # 左剪切大小(像素数)
    leftCutPixels=650
    # 右剪切大小(像素数)
    rightCutPixels=650

# extractFeature参数
    # "特征提取"实现方法
    extractFeatureMethod=ORB
    # ORB
    # SIFT
    # SURT
    # "特征提取"数量
    featureNums=100000
# MatchFeature参数
    # "特征匹配"方法
    matchFeatureMethod=BFM
    # BFM
    # flann
# filterMatches参数
    # "匹配过滤"方法
    filterMatchMethod=GMS
    ## None:不过滤
    ## GMS
    ## RANSAC
    ## maxDis:极大值抑制
    # 极大值抑制阈值
    maxDisThreshold=4
# estimatePose参数
    # 位姿估计
    estimatePoseMethod=3D3DSVD
    ## none:不估计，输出位姿等于输入位姿
    ## 3D3DSVD:将三维特征点匹配对带入观测方程，并利用SVD分解求解出估计位姿
    ## 3D2DPnp:pnp(opencv接口)
    ## 3D2DPnpRansac:pnp+ransac(opencv接口)
# OptimizePose参数
    # 位姿优化
    optimizePoseMethod=dense3D3D
    ## None:不适用任何方法，即使用给定的初始位姿作为估计结果
    ## sparse3D3D:利用稀疏点云(仅特征点)配准误差优化位姿 (使用g2o实现图优化)
    ## sparse3D2D:利用稀疏点云(仅特征点)重投影误差优化位姿 (使用g2o实现图优化)
    ## dense3D3D:ICP
```

* 其他

```text
# log参数
# 参数文件保存文件夹路径
log_save_dir=/Users/longqi/Desktop/project/data/goodScanSlam/FarStructure/tuyang1/log/
```

