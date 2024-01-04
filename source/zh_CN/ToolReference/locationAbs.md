# 力场（Local）

## 概述

设定外力对粒子的影响。

## Parameters
<div align="center">
<img src="../../img/Reference/Atraction/panel_en.png">
<p>“力场（Local）”窗口</p>
</div>

## 力场

可以设置至多4种力场。

## 类型

### 无

粒子不受外力影响。

### 力

从指定的位置向外侧施加力。
也可以让远离指定位置的力场产生衰减。

<div class="video_center"><video autoplay loop="true" muted="true" src="../../movies/Reference/LocalForceField/Force.mp4"/></div>

### 风

朝向指定的方向施加力。
可以通过旋转改变方向。

<div class="video_center"><video autoplay loop="true" muted="true" src="../../movies/Reference/LocalForceField/Wind.mp4"/></div>

### 龙卷风

施加绕指定方向旋转的力。
可以通过旋转改变轴的方向。

The movement speed can be specified so that the rotation speed is the same for the outside, or so that the movement speed is constant regardless of the position.

<div class="video_center"><video autoplay loop="true" muted="true" src="../../movies/Reference/LocalForceField/Vortex.mp4"/></div>

### 湍流

施加具有湍流的力。

<div class="video_center"><video autoplay loop="true" muted="true" src="../../movies/Reference/LocalForceField/Turbulence.mp4"/></div>

#### 类型

你可以选择简单或复杂。
越复杂，视觉效果越好，但运算速度也更慢。

#### 随机种子

通过随机种子产生随机的湍流。

#### 粒度

值越大，湍流越宽。

#### 强度

The strength of turbulence on particles.

译注：似乎没有这个设置。也许是统一改成“力”了。

#### 复杂度

值越大，湍流越复杂。但也会增大计算负担。

### 粘滞阻力

施加一个阻碍运动的力。

<div class="video_center"><video autoplay loop="true" muted="true" src="../../movies/Reference/LocalForceField/Drag.mp4"/></div>

### 重力

在一个方向上施加加速度。重力可以朝向任意方向。且不会受到父节点的方向影响。

<iframe src='../../Effects/viewer_zh_CN.html#References/Attraction_Forces/gravity.efkefc'></iframe>

### 引力（需要设置引力点）

粒子向“行为”窗口中的“引力点”处移动。

![](../../img/Reference/locationAbs_attraction.gif)

#### 引力

一帧中向目标位置的速度增量。

#### 阻力

一帧中运动方向修正为目标方向的百分比，取值在0.00和1.00之间。

#### 最小范围

引力开始衰减的距离。

#### 最大范围

引力结束衰减的距离。当粒子的位置在0到最小范围之间时，引力为100%。如果位置大于最大范围，引力为0%。如果在最小范围和最大范围之间，引力线性插值。


## 力场的位置

设置力场中心的位置。
影响部分力场的行为。

## 力场的角度

设置力场的角度。
影响部分力场的行为。

## 衰减类型

在范围之外，力场的效果会衰减。
有几种方式指定范围。

### 球

This parameter is used to decay the effect of the force field as it approaches or moves away from the center.
The greater the decay force, the more the force field is decayed as you move outward.

<div class="video_center"><video autoplay loop="true" muted="true" src="../../movies/Reference/LocalForceField/FallOff_Sphere.mp4"/></div>

### 管道

This parameter is used to decay the effect of the force field as it approaches or moves away from the axis at the center of the cylinder to the outside.
The greater the decay force, the more the force field is decayed as you move outward.

<div class="video_center"><video autoplay loop="true" muted="true" src="../../movies/Reference/LocalForceField/FallOff_Column.mp4"/></div>

### 圆锥

The shape of the cone is a part of a sphere cut into a cone.
This parameter is used to decay the force field as it approaches or leaves the outside of the cone.
The larger the decay force, the more the force field will decay as it approaches the maximum angle.

<div class="video_center"><video autoplay loop="true" muted="true" src="../../movies/Reference/LocalForceField/FallOff_Cone.mp4"/></div>
