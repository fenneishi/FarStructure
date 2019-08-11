# tool

一些工具算法：根据具体需要不断动态添加

### math

数学类：

- eigen2CV

  Eigen格式转成OpenCV格式

- cv2eigen

  OpenCV格式转成Eigen格式

- pcl2eigen

  pcl格式转成Eigen格式

- so32SO3

  李代数转换成李群

- float2double

  Eigen中不支持自动类型提升，所以需要手动转换

- Homogeneous

  齐次化与去其次化转换

- inv

  相机内参，外参(刚体转换矩阵求逆)求逆

- deep copy

  各种格式的数据的深拷贝通过模板重载统一实现

- pclCamera2Wold

  将PCL点云库的点云坐标或3D点坐标从相机系转换成世界系

- Rt2T

  由3*3旋转矩阵和3*1平移向量生成4*4的刚体变换矩阵

- T2Rt

  由4*4的刚体变换矩阵生成3*3旋转矩阵和3*1平移向量

- angle2radian

  角度转换成弧度，例如180°转换成π(pi)

- radia2angle

  弧度转换成角度，例如π(pi)转换成180°

- rθ2T[getT]

  由旋转半径r和旋转角度θ生成刚体变换矩阵

### cloud

点云类

- rgbd2cloud

  由配准好的color&&depth图生成点云

- saveCloud

  将点云保存到文件中

- printCloud

  逐个打印点云中的3D到log文件

- filterCloud

  点云滤波(未完成)

- segmentCloud

  点云分割(未完成)

- regisCloud

  点云配准(未完成)

### image

图片类

- pixel2Pixel

  像素配准：输入(u,v,d)&&内参&&变换矩阵，输出对应的(u,v)

- depth2color

  深度图配准到彩色图

- rgbd2rgbd

  一帧color&&depth配准到另一帧color&&depth

- imageCut

  图片剪切

- printColor

  逐点打印彩色图到log文件

- printDepth

  逐点打印深度图到log文件

### match

匹配类

- DrawInlier

  若是用GMS做的filterMatches,则在getImageMatches时候，需要调用DrawInlier.

- saveMatches

  图片形式保存Matches结果

- showMatches

  图片形式展示Matches结果

- getImageMatches

  获取ImageMatches(Matches结果的图片形式)

- getMatchPoints

  根据匹配结果，获取成功匹配的特征点(2D形式&&3D形式)