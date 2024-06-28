[# orbslam-related

## 1.前端改进
|  特征点获取方式   | 描述子  | 匹配方式 | 缺点
|  ----  | ----  | ----  | ----  |
| superpoint  | superpoint | —— |  |
| superpoint  | superpoint | superGlue | - |

* superGlue

当两帧之间缺乏共同视野的时候SuperGlue仍会强行匹配

测试：在连续帧中插入一两帧完全无关的就可以证明

* loftr

匹配难以在多帧图像间持续

测试：在连续帧就可以证明

https://github.com/zju3dv/LoFTR/tree/master

【改进版】Efficient LoFTR

## 2.点云地图
### 2.1 RGB_D相机
生成点云的代码可以使用cuda实现

【参考工作】https://github1s.com/gaoxiang12/ORBSLAM2_with_pointcloud_map/blob/master/ORB_SLAM2_modified/src/pointcloudmapping.cc#L59

https://github1s.com/Rich-King395/ORB-SLAM3-with-dense-pointcloud-reconstruction/blob/HEAD/src/SlamDataPub.cc#L154

【参考工作】https://blog.csdn.net/crp997576280/category_8062389.html

【带八叉树】
* https://github1s.com/Ewenwan/ORB-SLAM-RGBD-with-Octomap/blob/HEAD/MapDrawer.cc
* https://github.com/ruoxi521/ORB_SLAM3_Sematic_Extension.git
* 安装Octomap：https://www.cnblogs.com/gaoxiang12/p/5041142.html
### 2.2 单目相机
https://www.bilibili.com/video/BV1LS4y1C7u2/?spm_id_from=333.788.recommend_more_video.16&vd_source=0ada5c95f58cb319a77c62f35a4c0057
https://www.bilibili.com/video/BV19Y41167Ww/?spm_id_from=333.788.recommend_more_video.7&vd_source=0ada5c95f58cb319a77c62f35a4c0057

zoedepth 和 metric3d
https://github.com/yvanyin/metric3d
## 3.检测，分割
https://github1s.com/YWL0720/YOLO_ORB_SLAM3/blob/master/src/YoloDetect.cpp#L67

* 用yolov8,其实应该是可以并行的https://github1s.com/YWL0720/YOLO_ORB_SLAM3/blob/master/src/YoloDetect.cpp#L67
* 动态检测写的太粗暴了，直接用类型筛选，可以挂一个sort/或者假设是静止的获得一个Rt和真实Rt作比较

## 4.初始化修改
https://github.com/lturing/ORB_SLAM3_FAST_IMU_INIT

## 5.地图保存
https://github.com/TUMFTM/orbslam-map-saving-extension

## 6.回环检测
## 6.1 深度方法
https://github1s.com/Mingrui-Yu/A-Simple-Stereo-SLAM-System-with-Deep-Loop-Closing/blob/master/src/loopclosing.cpp#L453
