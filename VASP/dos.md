## DOS计算
### K点数目
+ 计算DOS的时候需要更多的K点
+ 一般来说，K*a=45即可

### ISMEAR
+ 一般使用`ISMEAR = -5`即可
+ 在模型很大，只用了一个gamma点或者K点的数目小于3的时候，使用ISMEAR = -5容易出错
+ 对于金属体系，计算DOS时结构保持不动，可以使用ISMEAR = -5
+ 结构优化的时候不能使用ISMEAR = -5
+ 半导体和绝缘体系不能使用ISMEAR > 0
+ ISMEAR = -5不适合能带计算
+ 使用ISMEAR = 5的时候，SIGMA的取值没有影响
+ 只要算DOS，只要K点的数目不小于3就可以用ISMEAR = -5
+ 如果不能使用ISMEAR = 5就可以增加K点数目

### SIGMA
+ MP方法：ISMEAR = 1..N
  + SIGMA的取值太大，计算出来的能量可能不正确，SIGMA取值越小越精确，需要的时间越长
  + **保证OUTCAR中'entropy T*S'这项能量平均到每个原子上小于1 meV的前提下**，尽可能大
  + 对于金属体系，一般用MP方法，SIGMA = 0.1足够
+ GS方法：ISMEAR = 0
  + 对于大部分的体系都能得到较好的结果
  + SIGMA取值太大的时候会得到MP方法相近的误差
  + **保证OUTCAR中'entropy T*S'这项能量平均到每个原子上小于1 meV的前提下**，尽可能大
  + 金属体系使用GS方法一般取SIGMA = 0.05
  + 对于半导体和绝缘体，SIGMA的值要小，SIGMA = 0.1~0.5之间是安全的
+ 计算结束要检查'entropy T*S'这项能量平均到每个原子上是否小于1 meV
+ SIGMA小的时候，ISMEAR = 0和ISMEAR = 1效果基本一样
+ SIGAM大的时候，ISMEAR = 1效果更好
+ 选择一般在0.1~0.01之间

### 计算参数
+ 一步计算必须参数
  + ISMEAR = -5
  + LORBIT = 11
  + 高密度的K点
+ 两部计算必须参数
  + 第一步
    + ISMEAR = -5
    + LCHARG = .TRUE
    + 稍微低密度的K点
  + 第二步
    + ISMEAR = -5
    + ICHARG = 11
    + LORBIT = 11
    + 高密度的K点
