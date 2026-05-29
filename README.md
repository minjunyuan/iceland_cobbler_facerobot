# Iceland Cobbler Face Robot

这是一个基于 Blender 开源角色模型进行二次设计的人脸机器人项目。项目内容包括机器人内部表情机构、脸部外壳、硅胶皮肤模具，以及用于展示的 STL 文件。

除明确注明来源的 Blender Studio Einar 参考模型外，本文展示的机器人机械结构、外壳、硅胶皮肤模具和实物制作均为自制。机构驱动舵机使用 MG90D。

## 项目状态

本文主要记录设计思路、关键流程和阶段性成果，没有对内部结构设计的全部细节逐一展开。若对某个结构、制作步骤或文件内容有疑问，可以通过 GitHub Issues 交流。

实际制作人脸机器人时会遇到大量与材料、装配公差、驱动行程、硅胶成型和外壳避让相关的具体问题，需要读者结合自己的加工条件和设计目标自行调整。本项目目前处于搁置状态，现有结构仍存在一些需要继续优化的问题，但整体设计方向接近常见人脸机器人和仿生表情机构的主流思路，可作为外观机构、面壳设计和硅胶模具设计的参考案例。

## 项目结构

```text
.
├─ full_assembly_stl/   # 所有设计元素的 STL 文件
├─ images/              # 项目图片、渲染图、过程图
└─ README.md
```

## 1. 设计对象

本项目的设计对象来源于 Blender Studio 的开源角色模型：[Einar](https://studio.blender.org/characters/einar/v1/)。

这个模型本身有完整的头部建模，并且包含独立的眼睛、牙齿和舌头模型。由于这些部分之间的相对位置已经确定，因此非常适合作为人脸机器人外观设计、机构空间规划和硅胶皮肤制作的参考对象。

<p>
  <img src="images/readme/001_1.jpg" width="32%" alt="Einar 参考图 1">
  <img src="images/readme/002_2.jpg" width="32%" alt="Einar 参考图 2">
  <img src="images/readme/003_3.jpg" width="32%" alt="Einar 参考图 3">
</p>

<p>
  <img src="images/readme/004_blender5.jpg" width="32%" alt="Blender 参考模型 1">
  <img src="images/readme/005_blender8.jpg" width="32%" alt="Blender 参考模型 2">
  <img src="images/readme/006_blender9.jpg" width="32%" alt="Blender 参考模型 3">
</p>

## 2. 结构设计

结构部分采用模块化设计，目的是方便拆装、调试和后续修改。主体可以分为眉部、眼部和嘴部，其中嘴部又分为上颚部分和下颚部分。

眉部机构会预留一部分脸颊和鼻子拉线的空间；眼部机构用于支撑和控制眼睛区域；嘴部机构则承担上下颚和口腔区域的表情运动。

本项目中使用的舵机型号为 MG90D。模块化设计可以让舵机、连杆、壳体和硅胶皮肤的设计相互独立，便于单独修改和迭代。

### 整体设计展示

<p>
  <img src="images/readme/007_整体机构前.jpg" width="32%" alt="整体机构前视图">
  <img src="images/readme/008_整体机构斜.jpg" width="32%" alt="整体机构斜视图">
  <img src="images/readme/009_整体机构侧.jpg" width="32%" alt="整体机构侧视图">
</p>

<p>
  <img src="images/readme/010_整体机构前带壳.jpg" width="32%" alt="整体机构前视图带壳">
  <img src="images/readme/011_整体机构斜带壳.jpg" width="32%" alt="整体机构斜视图带壳">
  <img src="images/readme/012_整体机构侧带壳.jpg" width="32%" alt="整体机构侧视图带壳">
</p>

<p>
  <img src="images/readme/013_整体机构前带壳带皮.jpg" width="32%" alt="整体机构前视图带壳带皮">
  <img src="images/readme/014_整体机构斜带壳带皮.jpg" width="32%" alt="整体机构斜视图带壳带皮">
  <img src="images/readme/015_整体机构侧带壳带皮.jpg" width="32%" alt="整体机构侧视图带壳带皮">
</p>

### 眉部机构

<p>
  <img src="images/readme/016_眉毛机构前.jpg" width="48%" alt="眉毛机构前视图">
  <img src="images/readme/017_眉毛机构斜.jpg" width="48%" alt="眉毛机构斜视图">
</p>

### 眼部机构

<p>
  <img src="images/readme/018_眼睛机构前.jpg" width="48%" alt="眼睛机构前视图">
  <img src="images/readme/019_眼睛机构斜.jpg" width="48%" alt="眼睛机构斜视图">
</p>

### 嘴部机构

<p>
  <img src="images/readme/020_嘴巴机构前.jpg" width="32%" alt="嘴巴机构前视图">
  <img src="images/readme/021_嘴巴机构斜.jpg" width="32%" alt="嘴巴机构斜视图">
  <img src="images/readme/022_嘴巴机构侧.jpg" width="32%" alt="嘴巴机构侧视图">
</p>

### 实物图

<p>
  <img src="images/readme/023_A正.jpg" width="32%" alt="实物图 A 正面">
  <img src="images/readme/024_A侧.jpg" width="32%" alt="实物图 A 侧面">
  <img src="images/readme/025_B.jpg" width="32%" alt="实物图 B">
</p>

### STL 文件说明

`full_assembly_stl/` 中放置了所有设计元素的 STL 文件。将这些 STL 导入任何可以观察 STL 的软件中，例如 Blender，可以显示正确的相对位置。

在本项目中，Blender 不只是展示工具，后续也用于设计机器人脸部外壳，以及设计硅胶皮肤制作所需要的模具。

<p>
  <img src="images/readme/026_blender1.jpg" width="24%" alt="STL 导入 Blender 1">
  <img src="images/readme/027_blender2.jpg" width="24%" alt="STL 导入 Blender 2">
  <img src="images/readme/028_blender3.jpg" width="24%" alt="STL 导入 Blender 3">
  <img src="images/readme/029_blender4.jpg" width="24%" alt="STL 导入 Blender 4">
</p>

## 3. 机器人脸部外壳设计（Blender）

### 3.1 参考人物模型处理

Blender 开源模型中可以获得无厚度的参考人物模型。机器人脸部外壳不需要明显的皱纹，同时对称、平整的表面更适合后续设计和加工，所以这里对原始模型进行了平滑处理。

<p>
  <img src="images/readme/030_1.jpg" width="32%" alt="参考模型处理 1">
  <img src="images/readme/031_3.jpg" width="32%" alt="参考模型处理 2">
  <img src="images/readme/032_2.jpg" width="32%" alt="参考模型处理 3">
</p>

### 3.2 外壳厚度

外壳需要一定厚度。在 Blender 中，固定厚度通常可以通过修改器中的“实体化”完成，厚度选项可以修改壳体厚度，偏移量可以决定实体化方向。

需要注意两点：

- Blender 中的单位 `m` 在当前显示中对应 `mm`。
- 有些区域，例如眼睛附近，曲率比较大，实体化后可能出现局部穿模。但在制作外壳时不一定需要担心，因为这些区域后续通常会被挖掉，用来给运动构件留空间。

<p>
  <img src="images/readme/033_4.jpg" width="32%" alt="实体化厚度 1">
  <img src="images/readme/034_5.jpg" width="32%" alt="实体化厚度 2">
  <img src="images/readme/035_10.jpg" width="32%" alt="实体化厚度 3">
</p>

### 3.3 外壳制作

#### 布尔修改器演示

在机器人驱动位置的外壳处，需要给内部运动机构让出空间。本项目主要依靠 Blender 的布尔修改器完成切割。

基本思路是：在对应角度画出想切割的切面，封闭网格后，按 `E` 将切割体延伸至与模型相交，然后添加布尔修改器，即可删去对应区域。

<p>
  <img src="images/readme/036_6.jpg" width="32%" alt="布尔修改器演示 1">
  <img src="images/readme/037_7.jpg" width="32%" alt="布尔修改器演示 2">
  <img src="images/readme/038_8.jpg" width="32%" alt="布尔修改器演示 3">
</p>

<p>
  <img src="images/readme/039_9.jpg" width="48%" alt="布尔修改器演示 4">
  <img src="images/readme/040_11.jpg" width="48%" alt="布尔修改器演示 5">
</p>

#### 外壳的实际设计

实际设计中通常需要两部分面壳：上脸部分和下巴部分。因为下巴有两个旋转自由度，所以需要独立出来。

当布尔切割完成后，可以按 `Tab` 进入编辑模式，选中上脸壳的一个点后按 `A` 全选关联点，再右键选择“分离选中项”，即可将两部分独立开来。

<p>
  <img src="images/readme/041_12.jpg" width="24%" alt="外壳实际设计 1">
  <img src="images/readme/042_13.jpg" width="24%" alt="外壳实际设计 2">
  <img src="images/readme/043_14.jpg" width="24%" alt="外壳实际设计 3">
  <img src="images/readme/044_15.jpg" width="24%" alt="外壳实际设计 4">
</p>

#### 外壳连接部分

外壳需要和 Blender 中导入的原机械结构进行物理连接。本项目采用的是简单的螺栓连接，并直接在 Blender 中完成连接结构的设计。

<p>
  <img src="images/readme/045_16.jpg" width="48%" alt="外壳连接结构 1">
  <img src="images/readme/046_17.jpg" width="48%" alt="外壳连接结构 2">
</p>

#### 外壳磁吸部分

为了方便面具摘取和复用，外壳上均匀分布了一些磁吸孔位。

<p>
  <img src="images/readme/047_19.jpg" width="48%" alt="外壳磁吸孔位 1">
  <img src="images/readme/048_20.jpg" width="48%" alt="外壳磁吸孔位 2">
</p>

图 18 中的四个槽位预留给眉部上方的拉线自由度，设计成凹槽形式，为拉线提供导向。这个设计参考了清华大学表情机器人 Morphene。

<p>
  <img src="images/readme/049_18.jpg" width="60%" alt="眉部拉线导向槽">
</p>

设计外壳时，需要将整体 STL 放入 Blender 中进行位置比对，防止出现干涉。需要挖去的位置和挖去多少都比较依赖具体结构，个性化较强，需要根据自己的机构自行设计。

## 4. 硅胶皮肤模具设计

硅胶皮肤的制作通常需要依靠模具，一般使用内外模具。这里将最终用于呈现硅胶外表面的模具称为外模具，也就是最终示人面的那一侧。

整体思路是：制作外壳时使用的无厚度模型，既是外壳的参考，也是内模具的参考；在此基础上整体放大，即可得到外模具。

具体操作方式可以很多样。这里主要记录本项目中的基本思路和关键步骤，不对中间所有建模细节展开。

### 4.1 预处理

为了防止穿模，需要对初始模型进行一定处理，并加上底座。预处理尽量只针对内模具，因为需要确保最终外形一致，所以外模具不建议随意改变。

<p>
  <img src="images/readme/050_21.jpg" width="60%" alt="硅胶模具预处理">
</p>

### 4.2 磁铁

磁铁分为固定部分和运动部分。固定部分在外壳设计时已经确定位置，因此同样需要用到内模具上；运动部分则通过和模型进行比对，确定几个运动位置的磁铁。

本机器人的面部驱动使用的是磁吸方式。

<p>
  <img src="images/readme/051_22.jpg" width="32%" alt="磁铁设计 1">
  <img src="images/readme/052_23.jpg" width="32%" alt="磁铁设计 2">
  <img src="images/readme/053_24.jpg" width="32%" alt="磁铁设计 3">
</p>

### 4.3 整体处理

模具上添加了用于开模的把手和用于定位的球槽。

<p>
  <img src="images/readme/054_25.jpg" width="60%" alt="模具整体处理">
</p>

### 4.4 外模具设计

外模具设计不在这里展开细说，主要展示最终设计效果。

<p>
  <img src="images/readme/055_27.jpg" width="60%" alt="外模具设计">
</p>

### 4.5 整体效果

<p>
  <img src="images/readme/056_34.jpg" width="60%" alt="硅胶模具整体效果">
</p>

## 5. 其他说明

Blender 开源模型本身提供了眼睛、牙齿和舌头模型，并且这些模型可以用于比对设计是否精准。这对不会曲面建模的设计者非常有利。

本文提供的开源模型仍然需要一定处理，不能简单理解为“直接套用即可完成机器人脸部设计”。它更适合作为可靠的外形参考、空间参考和后续建模基础。

<p>
  <img src="images/readme/057_28.jpg" width="32%" alt="眼睛牙齿舌头模型 1">
  <img src="images/readme/058_29.jpg" width="32%" alt="眼睛牙齿舌头模型 2">
  <img src="images/readme/059_30.jpg" width="32%" alt="眼睛牙齿舌头模型 3">
</p>

<p>
  <img src="images/readme/060_31.jpg" width="32%" alt="眼睛牙齿舌头模型 4">
  <img src="images/readme/061_32.jpg" width="32%" alt="眼睛牙齿舌头模型 5">
  <img src="images/readme/062_33.jpg" width="32%" alt="眼睛牙齿舌头模型 6">
</p>
