# 局部组装 `src/localasm/RunLocalAssembly.cpp`
> Local assembly is a new module introduced in MEGAHIT v1.0. The approach was ﬁrst used in IDBA-UD.

L = mean + 3 * sd, mean、sd为文库插入尺寸的平均值和标准差

- 载入并构建hashmap
- 读入文库
- 映射到contigs上
- 组装并输出
