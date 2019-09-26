# Object_Detection
深度学习之目标检测


----
###  **目标检测是在图片中对可变数量的目标进行查找和分类**
-   目标种类与数量的问题
-   目标尺度的问题
-   外在环境干扰的问题
### 目标检测与目标分割
1.  image classification
2.  object localization
3.   semantic segmentation
4.  instance segmentation
![在这里插入图片描述](https://img-blog.csdnimg.cn/2019092707111276.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3ptamFtZXMyMDAw,size_16,color_FFFFFF,t_70)

###  传统目标检测
1. viola-jones
2. HOG+SVM
3. DPM

####  传统目标检测方法基本流程
**输入-->候选框-->特征提取-->分类器判定（目标or背景）-->NMS-->输出**
-  soft-NMS（非极大值抑制算法）
1. **基本流程**
<p>1.1 input-->CNN-->1.Lreg, 2.Lcls</p>
2. **常见算法**
<p>2.1  YoloV1/V2/V3 </p>
<p>2.2 SSD/DSSD等 </p>
<p>2.3 Retina-Net </p>
<p>2.4 等等 </p>

3.  **核心组件**
<p>3.1  CNN网络</p>
<p>3.2  回归网络（区域回归(置信度，位置，类别）， 区域推荐Anchor机制</p>


####  深度学习目标检测方法
1.  One-stage(YOLO和SSD系列）
2. Two-stage(Faster RCNN系列）
2.1  input-->Conv&pooling--> [ conv-->proposal-->roi_pooling]*n --> fc--> 1.cls  2.reg
2.2  **Two-stage常见算法**
<p>2.2.1  RCNN</p>
<p>2.2.2 Fast RCNN</p>
<p>2.2.3 Faster RCNN</p>
<p>2.2.4 Faster RCNN 变种</p>
2.3  **核心组件**
<p>2.3.1  CNN网络</p>
<p>2.3.2  RPN网络（ 区域推荐，ROI Pooling, 分类和回归）</p>
 
  
####  one-stage VS Two-stage
1.  one-stage
  1.1  **优点**
  1.2  速度快
  1.3  避免背景错误，产生false positives
  2.1 **缺点**
  2.2  精度低（定位，检出率）
  2.3 小物体的检测效果不好（ 速度太快）
2.  Two-stage
1.1 **优点**
1.2  精度高（定位，检出率）
1.3  Anchor机制
1.4  共享计算量
2.1 **缺点**
2.2  速度慢
2.3  训练时间长
2.4  误报高


