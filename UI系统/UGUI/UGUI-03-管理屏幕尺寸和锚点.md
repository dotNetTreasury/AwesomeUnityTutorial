# 管理屏幕尺寸和锚点

## 1. 管理屏幕尺寸

### 1.1 屏幕横纵比

横纵比（宽高比）描述了屏幕的宽度和高度之间的关系

例如，老式电视和最早的电影使用 4:3 的纵横比。这意味着屏幕有 4 个单位宽和 3 个单位高。然而，现代宽屏电视和大多数新电影使用更宽的 16:9 纵横比，而手机的默认通常为 9：16 或 10：16

![](../../imgs/屏幕横纵比.png)

### 锁定项目的纵横比

Unity 允许您选择要用于 Canvas 的纵横比。

Free Aspect: 启用Free Aspect后，Canvas 的形状和大小会随着您调整 Game View 窗口的大小而改变。

## 2. Anchors 锚点

锚点在场景视图中显示为四个小三角形手柄（四叶花）。

每个叶子位置对应矩形的四个顶点（四个实心蓝色圆点 ）。当描点随父对象变换时，矩形的顶点与对应的锚点绝对距离必须保持不变。

例如，子项可以锚定到父项的中心，或锚定到一个角。

注意：

* 锚点可操作范围是父对象的矩形，而非当前对象的矩形。因为锚点就是用于子对象相对于父对象定位用的
* 锚点在一起，就不会在该方向上随着父对象缩放而缩放；反之则会。

### 2.1 锚点示例

下图中，UI 元素锚定到父项的中心。元素与中心保持固定偏移。

![](https://docs.unity3d.com/cn/2021.2/uploads/Main/UI_Anchored1.gif)

下图中，UI 元素锚定到父项的右下角。元素与右下角保持固定偏移。

![](https://docs.unity3d.com/cn/2021.2/uploads/Main/UI_Anchored2.gif)

通过锚定还可以让子项随父项的宽度或高度一起拉伸。矩形的每个角与其对应的锚点都有一个固定的偏移，即矩形的左上角与左上角锚点有一个固定的偏移，以此类推。因此，矩形的不同角可以锚定到父矩形中的不同点。

下图中，UI 元素的左角锚定到父项的左下角并且右角锚定到右下角。元素的角与其各自的锚点保持固定的偏移。

![](https://docs.unity3d.com/cn/2021.2/uploads/Main/UI_Anchored3.gif)

下图中，UI 元素的左角锚定到距离父矩形左边一定百分比的点，而右角锚点到距离父矩形右边一定百分比的点。

![](https://docs.unity3d.com/cn/2021.2/uploads/Main/UI_Anchored4.gif)

### 2.2 锚点预设

在 Inspector 面板中，可以在 Rect Transform 组件的左上角找到 Anchor Preset 按钮。点击该按钮会弹出 Anchor Presets 下拉菜单。

![](../imgs/UI_AnchorPreset.png)

如果水平轴或垂直轴上的锚点设置为与任何预设不同的位置，则会显示自定义选项。

![](../imgs/UI_RectTransform1.png)

Anchor Min 对应于 Scene View 中左下角的锚点手柄，Anchor Max 对应于右上角的手柄。

当所有锚点手柄都在一起时，显示的字段为 Pos X、Pos Y、宽度和高度。 Pos X 和 Pos Y 值表示枢轴相对于锚点的位置。

当锚点分开时，字段可以部分或完全更改为“左”、“右”、“上”和“下”。这些字段定义了由锚定义的矩形内的填充。如果锚点水平分离，则使用 Left 和 Right 字段，如果它们垂直分离，则使用 Top 和 Bottom 字段。

请注意，更改锚点或枢轴字段中的值通常会反向调整定位值，以使矩形保持原位。在不需要的情况下，通过单击检查器中的 R 按钮启用原始编辑模式。这会导致锚点和枢轴值能够更改，而不会因此而更改任何其他值。这可能会导致矩形在视觉上移动或调整大小，因为它的位置和大小取决于锚点和枢轴值。


<br>
<hr>
<br>

>参考资料
>
> - [创建用户界面 UI（官方手册）](https://docs.unity3d.com/cn/2021.2/Manual/UIToolkits.html)
> - [UGUI 包文档](https://docs.unity3d.com/Packages/com.unity.ugui@1.0/manual/index.html)
> - [其他 UI 资料- UI 系统学习](https://pmlpml.github.io/unity3d-learning/09-ui.html)



配套视频教程：
[https://space.bilibili.com/43644141/channel/seriesdetail?sid=299912](https://space.bilibili.com/43644141/channel/seriesdetail?sid=299912)

文章也同时同步微信公众号，喜欢使用手机观看文章的可以关注

![](../../imgs/微信公众号二维码.jpg)