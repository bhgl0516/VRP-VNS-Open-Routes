# VRP VNS 开放路径优化方案
VRP-VNS-开放路径优化方案 是针对车辆路径问题（VRP）特别设计的解决方案，专门用于优化开放路径问题中与吨公里相关的物流运输。本项目融合了强大的VRP算法、变邻域搜索（VNS）以及局部搜索算子（如Two-Opt优化、节点交换和位置重排）。通过结合启发式与元启发式算法，我们的解决方案以高效为核心进行物流规划，最小化产品运输过程中的总体能耗（通过基于站点间距离、货物载重及车辆自重计算每公里的吨公里数），从而降低运输成本。

需要特别说明的是，由于穷举法需要不切实际的计算时间，生成的解决方案并非最优解。然而，通过运用启发式与元启发式算法，我们的程序能够在合理时间内高效找到一个极具效能的解决方案。这种算法策略组合确保了在求解质量与计算效率之间取得平衡，实现快速实用的问题解决。

## 运行场景概述如下:

### 配送设置:
将产品从中心仓库运输至分布于不同位置的250个客户（编号集合N = {1,2, … ,250}）。
每个客户i ∈ N订购的产品数量记为𝑑ᵢ。***所有数据可在程序读取的Instance.txt文件中获取***。

### 车队与车辆规格:
使用同构车队，车辆空载重量𝛚 = 6吨，最大载重𝑄 = 8吨。
每辆卡车从中心仓库𝑑 = {0}出发，按顺序访问客户节点。

### 路径约束:
每个客户i ∈ N由单一车辆单次访问完成配送，且必须交付所需数量𝑑ᵢ的商品。

### 路径终止规则:
路径在最后一个服务客户处终止，即采用开放路径模式。

### 成本计算:
运输总成本基于所有路径累计的吨公里数（吨 × 公里）进行计算。

### 优化目标:
路径设计需最小化综合吨公里数，同时考虑卡车自重和货物运输重量。

### 算法实现:
* 集成专为开放路径和吨公里优化设计的VRP算法
* 通过变邻域搜索（VNS）在初始解生成后进行动态解空间探索
  * 融合多种局部搜索算子，包括Two-Opt优化、节点交换和位置重排

## 程序执行说明
运行程序请使用命令 `python main.py`。执行后将生成***output.txt***文件，其中包含***问题解决方案（总吨公里数及生成的配送路径）***。本仓库中已提供基于Instance.txt规格生成的output.txt示例文件。通过命令 `python sol_checker.py` 可验证output.txt中的解决方案是否正确。

## 开发团队
| Full Name | Github Account |
| --- | --- |
| Kapetanaki Elina | [ElinaKapetanaki](https://github.com/ElinaKapetanaki) |
| Kirikos Aggelos | [aggekirikos](https://github.com/aggekirikos) | 
| Siamantouras Vaggelis | [evansiam](https://github.com/evansiam) | 
| Tsagkaraki Aggeliki | [Angeliki03](https://github.com/Angeliki03) | 
| Tsetsila Despoina | [DespoinaTsetsila](https://github.com/DespoinaTsetsila) |
| Chlouveraki Nikol | [nikochlouveraki](https://github.com/nikochlouveraki) |
