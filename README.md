# IMUCalibration-Gesture
calibration for Imu and show gesture

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=shenshikexmu/IMUCalibration-Gesture&type=Date)](https://star-history.com/#shenshikexmu/IMUCalibration-Gesture&Date)


#### 0.相关博客:

https://blog.csdn.net/shenshikexmu/article/details/80013444

#### 1.读入数据
```
load('caldata.mat')
```

#### 2.运行校正算法
```
[Ta,Ka,Ba,Tg,Kg,Bg,Tm2a,Bm,Vm,mag_strength]=ImuCalibration_Gesture(cal_data)
```

#### 3.校正部分

##### 加速度、角速度
   conference  **A Robust and Easy to implement method for imu calibration without External Equipments**
##### 磁力计
   算法mag2acc_matrix假设重力与磁向量的夹角不变，算法Cal_mag4acc_frame利用不同姿态下传感器感受的磁通向量的变化与姿态变化的相关性，计算参数。

#### 4.参数部分

#####  cal_acc=Ta*Ka*(raw_acc+Ba)
#####  cal_gyro=Tg*Kg*(raw_gyro+Bg)
#####  cal_mag=Tm2a*(raw_mag+Bm)
   
#### 5.姿态部分

 #####  Mahony filter
   conference **Nonlinear Complementery Filters on the Special Orthogonal Group**
   
   inspired by    http://blog.csdn.net/luoshi006/article/details/51513580
 #####  EKF
   derivation **A Double-Stage Kalman Filter for Orientation Tracking with an Integrated Processor in 9-D IMU**
 #####  high low pass
   high and low pass filter to Gyro atitude with Accelerate & Magnetic
 #####  ESKF
   conference **Quaternion kinematics for the error-state Kalman filter**
   
   inspired by https://github.com/yuzhou42/ESKF-Attitude-Estimation/blob/master/ESKF%20Attitude%20Algorithm.pdf
   
   
 #### 6.LM算法

 #####  Optimize_my_LM
   Levenberg-Marquardt algorithm written by myself 
   
   conference   https://ww2.mathworks.cn/help/optim/ug/least-squares-model-fitting-algorithms.html#brrx6vm
   
  

 ##### 滤波后的四元数
 
![滤波结果](https://img-blog.csdn.net/20180606120722833?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NoZW5zaGlrZXhtdQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/10)
##### 算法视频
[![视频]( https://i1.hdslb.com/bfs/archive/9d5e7893c77612498a023d58005a2ee6b03560ee.jpg)](https://www.bilibili.com/video/av78142069/)

##############we add 添加url
https://blog.csdn.net/shenshikexmu/article/details/70143455
https://blog.csdn.net/shenshikexmu/article/details/80013444
