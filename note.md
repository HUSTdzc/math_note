# 什么是概率什么是统计
概率：使用现有的已知数据来预测未来事件的可能性。
统计：使用样本数据来得出有关更大群体的结论。
样本和总体的关系：总体研究对象的全体，总体的部分个体，独立同分布，实验前一般大写字母表示X~1~，试验后小写字母x~1~表示为样本观察值。（独立必定不相关，不相关不一定独立，独立判断通过定义概率相乘，相关性判断通过协方差）

# 由样本对总体的分布（特征）进行合理地推断。
通过样本发生频率估计概率分布
![频率估计概率](https://github.com/HUSTdzc/math_note/blob/main/IMAGE/465b515b0c434300c85baff57498879e.svg)
理论支撑：格列汶科定理，根据大数定律可知，事件发生的频率依概率收敛到这个事件发生的概率，因此可用事件{X≤x}发生的频率来估计P{X≤x}，即可用经验分布函数来估计总体的理论分布F(x) =P{X≤x}

# 统计量与统计量观察值
![统计量](https://github.com/HUSTdzc/math_note/blob/main/IMAGE/Screenshot%202024-05-16%20155708.png)
常用统计量：样本均值、样本方差、样本k阶原点矩、样本k阶中心距、顺序统计量、样本中位数、样本极差
> 样本方差分母为n-1，原点矩和中心矩分母为n
> 若样本期望、方差均存在，则：样本均值的期望与总体期望相同；样本均值的方差为总体方差除以n（证明需要利用方差的性质：分布和的方差等于方差的和加上二倍协方差，由于各个**样本独立同分布**所以协方差为0）；样本方差的期望与总体方差一致；
统计量的作用：压缩样本信息、提取有用信息（高级算法聚类、神经网络等本质也是提取有用信息的过程，利用统计数据得出更大群体更加普适性的结论）

# 抽样分布
## 卡方分布
![分布1](https://github.com/HUSTdzc/math_note/blob/main/IMAGE/Screenshot%202024-05-16%20170008.png)
性质：期望为n，方差为2n；**相互独立**的$`\chi^{2}`$分布具有可加性
## t分布
![分布2](https://github.com/HUSTdzc/math_note/blob/main/IMAGE/Screenshot%202024-05-16%20195442.png)

## F分布
![分布3](https://github.com/HUSTdzc/math_note/blob/main/IMAGE/Screenshot%202024-05-16%20200018.png)

## 上α分位点
![上α分位点](https://github.com/HUSTdzc/math_note/blob/main/IMAGE/Screenshot%202024-05-16%20200528.png)
![上α分位点性质](https://github.com/HUSTdzc/math_note/blob/main/IMAGE/Screenshot%202024-05-16%20202205.png)

> 此处遇到一道十分有意思的练习题：
> ![练习题](https://github.com/HUSTdzc/math_note/blob/main/IMAGE/image.png)
> ![解答](https://github.com/HUSTdzc/math_note/blob/main/IMAGE/D551044D58FF88E783056430FE7293E6.png)
> *其中关于S^2为什么服从n-1的卡方分布*可通过[这里](https://zhuanlan.zhihu.com/p/390043144)证明。

## 定理：
![定理1](https://github.com/HUSTdzc/math_note/blob/main/IMAGE/Screenshot%202024-05-17%20172855.png)
![定理2](https://github.com/HUSTdzc/math_note/blob/main/IMAGE/Screenshot%202024-05-17%20172908.png)
![定理3](https://github.com/HUSTdzc/math_note/blob/main/IMAGE/Screenshot%202024-05-17%20172918.png)
![定理4](https://github.com/HUSTdzc/math_note/blob/main/IMAGE/Screenshot%202024-05-17%20172932.png)


# 参数估计
总体中的未知参数，通过统计量对位置参数进行估计，采样获得估计值
## 矩估计
根据大数定理，样本矩在一定程度上逼近总体矩。总体的原点矩包含未知参数信息，通过样本原点矩求解方程组获得未知参数矩估计。
## 极大似然估计
在一次抽样中，若得到样本观测值(x1,…,xn)，则选择使得此组观测值出现的概率最大的参数进行估计。
对于似然函数一般为连乘形式，通常取对数求导求得最大值。
![性质](https://github.com/HUSTdzc/math_note/blob/main/IMAGE/Screenshot%202024-05-17%20210554.png)
该性质证明：极大似然函数对u求导时，可通过求导法则转换为对$`\theta`$求导，再乘以$`\theta`$对u求导，此处要求反函数存在导数。
> 反函数存在定理：严格单调函数必定有严格单调的反函数，并且二者单调性相同。函数的定义域与值域是一一映射

## 估计量的评选原则
### 无偏性
