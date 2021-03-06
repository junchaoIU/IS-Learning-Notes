# K近邻

- K近邻假设给定一个训练数据集，其中实例类别已定。分类时，对于新的实例，根据其k个最近的输入模型的训练实例，进行多数投票表决来决定其类别。
- k=1是特殊情况，称为最近邻算法
- 特征空间中，对于每个实例点，距离该点比其他点更近的所有点组成的一个区域，叫做单元（cell）
- k近邻中计算的点间距离一般为欧氏距离，也可以是其他距离如Minkowski距离

设特征空间是$X$是$n$维向量空间$R^n  $，$x_{i}, x_{j}/in{X}$，$x_{i}, x_{j}  $的$L_{p}$距离定义为：

$$
L p\left(x_{i}, x_{j}\right)=\left(\sum_{l=1}^{n}\left|x_{i}^{(l)}-x_{j}^{(l)}\right|^{p}\right)^{\frac{1}{p}}
$$


$p=2$时，称为欧氏距离（直线）；$p=1$时，称为曼哈顿距离（弧形）；$p=无穷大$时，取最大值（直角线）

- 不同距离度量所确定的最近邻点不同
- K值减少意味着模型整体变得复杂，容易发生过拟合
- K值过大，模型过于简单，完全忽略了训练实例中大量的有用信息
- K值一般取一个比较小的数值，通常采用交叉验证法来选取最优K值
- kd树构建：选取特征坐标轴，不断地用超平面垂直于该坐标轴进行切分，kd树是一个二叉树
- 平衡kd树：选取的切分点为坐标轴中位数，平衡kd树搜索时效率未必是最优的
- 搜索kd树：首先找到包含目标点的叶节点，从该叶节点出发，依次回退到父节点，不断找寻与目标点最邻近的节点，当确定不可能存在更近的点时停止。
