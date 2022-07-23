# GAMES104-现代游戏引擎：从入门到实践

## 08 游戏引擎的动画技术基础(上)

### 遇到的挑战

1、需要根据**交互**来改变

2、和**玩法系统**协同合作

3、需要在**复杂环境**中调整

4、**实时**计算

5、动画**数据庞大**

6、真实感：脸部表情等

### 2D动画技术

原理：一组连续的frames

应用：2d游戏背景，3d游戏的粒子系统（sheet texture）,live2D（套皮人儿）

### 3D动画技术

rigid hierarchy animation （基于层次结构的刚体动画）：角色的每个**关节做成一个可动**的东西， 类似皮影戏，关节处的骨骼容易穿插

per-vertex animation（顶点动画）：需要设置很多顶点，每一个顶点的**位置随着时间的变化存下来**

Morph Target animation（ 变形目标动画）：用**k帧+lerp**实现，适合脸部动画

3D skinned animation（蒙皮）：每个顶点受不止一个骨骼影响，由**多根骨骼在一起同时作用**，皮肤不会穿插。2D也有用

physics-based animation ：ragdoll、布料、水体、IK。



动画制作：**k帧、动捕**

### 蒙皮动画实现

**skeleton = bone + joints**

Root->Pelvis

1、做mesh

2、做skeleton

3、刷蒙皮（每个顶点会受那根骨骼的影响，影响的权重）

4、做pose

5、动起来

### 3D旋转数学原理

欧拉角：符合直觉，但不好插值

**四元数**：

## 09.高级动画技术

### 动画混合

做 lerp

### 混合空间

方向+速度

**覆盖masked混合**：上半身动画、下半身动画

**叠加additive混合**：在原有的基础上，加上一个动画。（受击动画）

### 动画状态机

### 动画混合树

可以用多个变量控制动画的混合

### 反向动力学IK

双骨骼IK：

Foot IK 、 Look At IK、Hand IK 、Full Body IK

长链IK怎么算？

**CCD、FABRIK、Jacobian matrix**