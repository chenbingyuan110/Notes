# 不同类型计算对应的`INCAR`文件
## 单点计算
+ NSW = 0 / IBRION = -1

## 结构优化
+ ISIF = 3  # 结构优化必须设置
+ ENCUT = 600  # 1.3*max(ENMAX)，一般600或700便可
+ NSW = 100
+ EDIFFG = -0.015

## 频率计算
+ IBRION = 5
+ NFREE = 2
+ POTIM = 0.02 / 0.015
+ PREC = Normal
+ EDIFF = 1E-5 / 1E-6

## 参数分类
### 自旋和磁矩
+ ISPIN
+ MAGMOM

### 体系相关
+ ISMEAR
+ SIGMA

### 初始结构好坏
+ IBRION
+ POTIM
+ NSW

### 决定收敛
+ EDIFF
+ EDIFFG
