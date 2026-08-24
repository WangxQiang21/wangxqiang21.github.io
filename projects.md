---
layout: page
permalink: /projects/index.html
title: 项目
---

## 项目名称：SPMT自动驾驶控制算法开发

<p style="text-indent:2em;">
项目背景：针对湖北三江航天万山特种车辆有限公司无人平板车智能化需求，面向 SPMT 特种多轴车辆自动驾驶项目， 围绕低速重载、 路径循迹、 后部对接等典型场景， 完成组合导航接入、 控制点坐标补偿、 路径跟踪控制， 提升车辆多工况循迹稳定性和对接可靠性。
</p>

- 本人贡献：

- 负责 SPMT 特种多轴车辆自动驾驶项目中的组合导航接入、安装标定与定位数据校验，基于导远5711话题获取经纬度、航向角、速度等车辆状态信息。
- 参与完成WGS84经纬度到UTM坐标的转换，并结合车辆尺寸对导航安装点、车头、后轴及后部控制点进行坐标补偿，提升前进、倒车和对接工况下的控制点一致性。
- 基于Spline2D设计参考路径，参与路径跟踪控制调试，覆盖直线、圆形、八字、双移线、倒车和对接等典型实车工况。
- 基于现有CAN遥控接口完成控制闭环适配：横向控制采用Pure Pursuit路径跟踪算法；纵向控制采用PID速度控制思路，完成预瞄距离、等效轴距、转向比例、速度指令、限幅和停车阈值等参数的实车整定与数据复盘。

- 成果：产出一篇软著

<!-- **详细版**

- 负责导远组合导航设备的安装、标定和 ROS 数据接入，基于 `ASENSING.msg` 中的 `latitude`、`longitude`、`azimuth`、`north_velocity`、`east_velocity`、`ground_velocity` 等字段完成车辆位置、航向和速度状态校验。
- 参与定位坐标处理链路开发与调试，使用 `pyproj` 将 WGS84 经纬度转换为 UTM 坐标，并结合现场坐标偏移量完成局部坐标对齐，支撑 `Path.csv` 轨迹点和实车定位数据统一到同一坐标系。
- 针对组合导航安装点与车辆实际控制点不一致的问题，在 `wanshan_carv*.py`、`TrackController.py`、`DuijieControl.py` 等控制脚本中调试车体几何偏置补偿，实现从导航点到车头、后轴或后部对接控制点的坐标转移。
- 基于 `CubinSpline.py` 中的 `Spline2D` 生成平滑参考线，并利用 `cartesian_to_frenet1D`、`calc_yaw`、`calc_curvature` 等方法计算纵向进度、横向误差、航向误差和曲率信息，用于路径跟踪控制。
- 参与 Pure Pursuit 横向控制调试，结合 `WheelBase`、`LookAheadDistance` 和前进/倒车 `Direction` 逻辑，整定预瞄距离、等效轴距、转向比例和转向限幅，适配直线、圆形、八字、双移线及倒车路径。
- 参与 LQR/PID 控制模块调试，基于 `LatController`、`Longitudinal_PID_controller` 完成横向误差反馈、曲率前馈和速度指令整定，提升车辆低速跟踪和末端停车稳定性。
- 在车辆底层接口未完全开放的情况下，基于 `cantrasmit.msg` 适配 CAN 遥控模拟接口，通过 `/car_contrl` 发布 `mode_option`、`level_option`、`isdoublecar`、`turn_velocity`、`acc_velocity` 等指令，并结合 `/can_read` 反馈的转角信息进行闭环调参。
- 参与对接和工装场景控制逻辑调试，结合 `/camera_0_pose`、`/camera_1_pose` 相机位姿信息、停止距离阈值和路径终点判断，完成倒车对接、停车和姿态微调相关工况验证。
- 负责现场 rosbag/CSV 数据复盘和可视化分析，对比参考轨迹、实车轨迹、Frenet 误差、航向误差和控制指令，定位路径偏差、航向符号、控制点选择和参数不匹配等问题。 -->



<img src="/images/wanshan.jpg" style="display:block; margin:0 auto; width:600px; max-width:100%; height:auto;">

> 本人右三

<!--
论文条目示例：

- [论文标题](论文链接)<br>
  **Qiang Wang**, Author B, Author C<br>
  会议或期刊名称，年份。<br>

如果不需要某个小节，可以直接删除对应标题和“待补充”。
-->
