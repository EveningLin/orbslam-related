# orbslam-related

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
