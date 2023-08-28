# 动态参数

## 概述

DynamicParameter specifies a parameter to rewrite refresh (during game) effect parameters during effect playback.
It controls parameters with simple code. Parameters can be given externally.

## 使用方法

### 基础

#### 面板

打开动态参数面板。

```eval_rst
.. image:: ../../img/Reference/DynamicParameter/menu_en.png
   :align: center
```

#### 添加表达式

你可以单击“添加”按钮添加一个表达式。
你可以编辑表达式的名称和内容。

```eval_rst
.. image:: ../../img/Reference/DynamicParameter/add_en.png
   :align: center
```

#### 编写表达式

例如，要将第一个参数修改为2.0，可写为如下形式。

```
@O.x = 2.0
```

然后点击编译。如果没出现问题，会显示OK。如果出现问题，会显示出错的原因。

```
@O.x = 2.0
```


#### 使用表达式

右键要使用表达式的参数并选择动态。
然后会显示一个选择表达式的文本框。

```eval_rst
.. image:: ../../img/Reference/DynamicParameter/select_dynamic_en.png
   :align: center
```

Then, select the expression you entered earlier and the expression is applied.

```eval_rst
.. image:: ../../img/Reference/DynamicParameter/apply_dynamic_en.png
   :align: center
```

The parameter of the position is (0, 0, 0). But a particle is shown on 2 because the expression changes positions into 2

```eval_rst
.. image:: ../../img/Reference/DynamicParameter/move2.png
   :align: center
```

### Functions of an expression

#### Change multiple parameters

x, y, z, w, each parameter can be changed.
Entering the following changes the values ​​to 2, 3, 4, and 5, respectively.
If the destination is a color, x, y, z, w correspond to RGBA.


```
@O.x = 2.0
@O.y = 3.0
@O.z = 4.0
@O.w = 5.0
```

#### 四则运算

表达式可以使用算术运算。可以用()修改运算优先级。

```
@O.x = (2.0 + 3.0 * 2.0 / 3.0) - 2.0
```

#### 参数

Parameters input from the external can be specified from the numeric field on the panel and runtime.

|参数|说明|
|:----|:----|
|@P.x @P.y @P.z @P.w|Parameters before dynamic parameter is applied|
|@In0 @In1 @In2 @In3|Parameters input from the external|
|@GTime|当前时间（秒）|
|@PTime|父粒子生成至今的时间（s）|

#### 函数

可以使用以下函数。

|函数|说明|
|:----|:----|
|sin(x)|返回正弦值，x使用弧度制。|
|cos(x)|返回余弦值，x使用弧度制。|
|rand()|返回随机值|
|rand(x)|返回与x相关的随机值。如果x相同，则返回值也相同。|
|step(edge,x)|如果x大于edge，返回1.0。否则返回0。|

#### 目标

动态参数可应用于以下参数。

- 生成数量
- 生成速率
- 生成开始时间
- 生命周期
- 位置 - 固定，位置・速度・加速度，缓动
- 旋转 - 固定，角度・速度・加速度，缓动
- 缩放 - 固定，缩放・速度・加速度，缓动

## 示例

### LOD

The number of generations can be changed externally.

```
@O.x = @In0 * @P.x
```

### 激光

The length of the laser can be changed externally.
The size of Z is controlled externally.

```
@O.z = @In0 * @P.z
```

### 正弦波

像正弦波一样移动。

```
@O.x = sin(@GTime)
@O.y = @GTime
```
