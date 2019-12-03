## 计算结果处理
### 信息提取
#### `POTCAR`中包含的元素
```bash
grep TITEL POTCAR
```
#### `POTCAR`中元素的截断能
```bash
grep ENMAX POTCAR
```
#### `OUTCAT`中计算完成后的体系能量
```bash
grep "  without" OUTCAR  # without前有两个空格
```
获得结果：
```
  energy  without entropy=       -0.00604471 energy(sigma->0) =       -0.01375782
```
> 第一个能量为在INCAR设定的SIGMA下的能量，第二个为推测SIGMA趋近于0时候的能量，应用的时候不能混用，整个计算中从始至终只能用其中一个。

#### `OUTCAR`中K点数目
```bash
grep irre OUTCAR
```

#### `OUTCAR`中收敛情况
```bash
grep 'reached required accuracy' OUTCAR
```
