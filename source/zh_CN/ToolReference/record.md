# 录像

## 概述

允许你将特效输出为精灵表单（Sprite Sheet）、gif动画、AVI等。可用于将特效发布到Twitter/博客/网站/其他场合，或者你无法通过运行时播放Effekseer制作的特效的情况。

<table>

<tbody>

<tr>

<td><img src="../../img/Reference/record_anim.jpg"/></td>

<td><img src="../../img/Reference/record_gifanim.gif"/></td>

</tr>

</tbody>

</table>

## 参数

### 分辨率

#### 宽度/高度

设置动画每帧的输出尺寸。

#### 缩放

录像区域相对于实际的屏幕放大。
例如，如果宽度和高度是256，且缩放为2，也就是在256的区域中以两倍的缩放比率录像，输出分辨率为512的图片。

#### 显示向导

勾选时，录像区域的边界会在屏幕上显示。向导区域内的一切都会被录像，区域之外的东西会被裁剪掉。

### 导出的帧

#### 开始帧

设置从第几帧开始录像。

#### 结束帧

设置从第几帧结束录像。

#### 频率（帧）

Sets the level of frame skipping in the file output. For example, for a value of 1, when 60 frames are recorded, 60 images will be output. For a value of 2, when 60 frames are recorded, only 30 images will be output (every other frame). If you increase the number like this, the file size will become smaller at the cost of choppier animations.

### 格式

There are 4 options: "Export as a single image", "Export images", "Export as a gif animation", and "Export as a AVI".

"Export as a single image" will create a sprite-sheet image with frames arranged from the upper left to the lower right. The number of frames arranged horizontally will be number specified under "X Count". Consequently, the number of frames arranged vertically will be the total number of recorded frames / X Count.

"Export images" outputs frames as individual files with numbers attached to each filename.

"Export as a gif animation" outputs the captured effect to a gif file.

"Export as a AVI" outputs the captured effect to an uncompressed animation file.

<table>

<tbody>

<tr>

<td>导出为单张图片</td>

<td>导出为连续多张图片</td>

<td>导出为gif动画</td>

</tr>

<tr>

<td><img src="../../img/Reference/record_single.jpg"/></td>

<td><img src="../../img/Reference/record_seq.jpg"/></td>

<td><img src="../../img/Reference/record_gifanim.gif"/></td>

</tr>

</tbody>

</table>

### 选项

### 透明

设置如何处理背景，gif动画除外。

#### 无

将背景设置为黑色。

```eval_rst
.. image:: ../../img/Reference/Recording/none.png
   :align: center
```

#### 使用原始图片

将背景设置为透明。
如果使用了黑色背景且混合方法为加法的图片，有时候会生成错误的图像。

```eval_rst
.. image:: ../../img/Reference/Recording/original.png
   :align: center
```

#### 生成alpha

自动生成alpha通道。
如果使用了深色且混合方法为混合的图片，有时候会生成错误的图像。

```eval_rst
.. image:: ../../img/Reference/Recording/generate.png
   :align: center
```

#### 生成alpha(Blend+Add)

By outputting the recorded results separately from blend and addition, 
the color when the background is changed can be reproduced in the possible range.
It can also record an effect which contains blend and additive particles.

```eval_rst
.. image:: ../../img/Reference/Recording/generate_blend_add.png
   :align: center
```

When using, draw the added image by addition after drawing the blended image by blending, 

```eval_rst
.. image:: ../../img/Reference/Recording/blend_add_desc.png
   :align: center
```

<iframe width="560" height="315" src="https://www.youtube.com/embed/XqhE_pllD90" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

#### 方法间的对比

From left to right, None, Original image, Generate alpha, Generate alpha(Blend+Add) images are displayed.

```eval_rst
.. image:: ../../img/Reference/Recording/compare.png
   :align: center
```

### 设置保存目标

It can specify whether to save the recording settings to the application or the project.
