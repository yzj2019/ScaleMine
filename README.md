# ScaleMine频繁子图挖掘

## 试图跑起来示例

情况说明：
- 服务器上运行，不是sudoers，提前部署了 Open MPI 4.0.0
- 缺少其它依赖

下面实操：
1. 源代码用的 Open MPI 的版本应该小于2.0.0，所以有些API需要更改，主要在main.cpp中；
2. 源代码有一处地方，c++11后不再支持`static const double`直接初始化，改为`static constexpr double`；
3. 运行环境依赖，需要安装boost库：
    ```
    sudo apt-get update
    sudo apt-get install libboost-all-dev
    ```
4. 编译：
    
    在ScaleMine文件夹下，执行
    ```
    bash ./compile.sh
    ```
5. 运行示例：
    ```
    mpirun -n 2 pfsm -file ./Datasets/patent_citations.lg -freq 28000 -threads 4
    ```
    运行详见[官方文档](./doc.md)。

## 将ScaleMine应用到赛题数据上

