# FAQ

### SURF和SIFT特征点为什么无法使用

SURF和SIFT因为专利原因，在OpenCV3以后被放置在opencv\_contrib，且必须在编译时候打开相应开关，才能使用，所以必须要确保两点

1. 确保安装了opencv\_contrib。
2. 确保打开了SURF和SIFT所在模块的编译开关

具体参见：

* [OpenCV3.4.X中Nonfree模块的使用-SURF为例](https://blog.csdn.net/zhoukehu_CSDN/article/details/83145026)
* [Mac上编译安装 opencv和opencv\_contrib](https://blog.csdn.net/sdlypyzq/article/details/78155685)

### GMS为什么无法使用

目前必须是ORB特征点+BFS特征匹配才能使用GMS，后期会根据需要解决这个问题

### 相机参数为什么会读取错误

默认的相机参数读取格式如下：

![calib.png](../.gitbook/assets/calib.png)

常见的相机参数错误如下

* 内参格式错误：先depth相机后color相机。
* 外参格式错误：是color2depth，而非color2depth。
* 外参单位错误：单位不是mm，而是m。

有时候必须要调整相机参数默认读取方式，可以通过配置文件进行修改\(详见“上手/配置”章节\)

```cpp
# 相机参数文件格式：内参是否是先rgb后depth
Interior_rgbThenDepth=true
# 相机参数文件格式：外参是否是depth2rgb
Extrinsic_depth2rgb=false
```

### 为什么图片读取不进来

图片无法读取的可能原因如下

* 图片格式不对：默认格式后缀为.ppm和.pgm，若是其他个格式，可直接在配置文件里修改：\(详见“上手/配置”章节\)

```cpp
        # color图文件名后缀(文件格式)
        rgb_read_extName=.png
        # depth图文件名后缀(文件格式)
        depth_read_extName=.png
```

* 图片名称不对：默认图片命名格式如下,若是其他个格式，可直接在配置文件里修改：\(详见“上手/配置”章节\)
  * 深度图：
    * depth00000.pgm
    * depth00001.pgm
    * depth00002.pgm ...

      对应的配置为：

      **color图文件名前半部分\(固定部分\)**

      rgb\_read\_preName=color

      **color图文件名后半部分\(变化部分\)**

      rgb\_read\_formatName=%5i

      **color图文件名后缀\(文件格式\)**

      rgb\_read\_extName=.pgm
  * 彩色图：
    * color00000.ppm
      * color00001.ppm
      * color00002.ppm

        ...

        对应的配置为：

        **depth图文件名前半部分\(固定部分\)**

        depth\_read\_preName=depth

        **depth图文件名后半部分\(变化部分\)**

        depth\_read\_formatName=%5i

        **depth图文件名后缀\(文件格式\)**

        depth\_read\_extName=.ppm

