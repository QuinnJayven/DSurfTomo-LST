# DSurfTomo-LST

**Adaptive-Dictionary-Regularized 3-D Direct Inversion of Surface-Wave Dispersion Data**

[中文](#中文说明) | [English](#english)

---

# 中文说明

## 简介

DSurfTomo-LST 是在 DSurfTomo 三维面波频散直接反演程序基础上发展的一套自适应字典正则化层析成像程序。

程序直接利用台站对之间的面波频散数据反演三维横波速度结构，不需要预先构建不同周期的二维相速度或群速度图。DSurfTomo-LST 保留了 DSurfTomo 的快速行进法（Fast Marching Method, FMM）正演、射线路径更新和三维灵敏度矩阵计算，并在反演中加入局部稀疏建模和自适应字典学习。

反演初期采用 Laplacian 正则化建立大尺度速度背景，随后切换到基于局部 patch 的字典正则化。局部模型采用 OMP（Orthogonal Matching Pursuit）进行稀疏编码，并采用 ITKM（Iterative Thresholding and signed K-Means）更新字典。不同反演深度层使用独立字典，同时通过深度方向耦合约束相邻层之间的连续性。

本仓库提供 Windows 64 位可执行程序、示例输入文件和用户手册。由于相关研究项目仍在进行，源代码计划于 2027 年公开。

## 主要文件

```text
DSurfTomo-LST/
├── README.md
├── DSurfTomo_lst.exe
├── DSurfTomo_lst.in
├── MOD
├── MOD.true
├── surfdataTB.dat
├── Run.bat
└── Manual/
    └── DSurfTomo-LST_用户手册_CN.html
```

## 运行

Windows 下双击：

```text
Run.bat
```

也可在 CMD 或 PowerShell 中进入程序目录后运行：

```text
DSurfTomo_lst.exe DSurfTomo_lst.in
```

输入参数、数据格式和输出文件的详细说明见：

[DSurfTomo-LST 中文用户手册](DSurfTomo-LST_用户手册.html)

## 引用

如果本代码对您的研究有帮助，欢迎引用以下文献：

**Z. Li, J. Ding, X. Cheng, R. He, X. Zhou and Z. Chen**,  
“Adaptive-Dictionary-Regularized 3-D Direct Inversion of Surface-Wave Dispersion Data,”  
*IEEE Transactions on Geoscience and Remote Sensing*, vol. 64,  
pp. 5919117-5919117, 2026, Art. no. 5919117.  
doi: [10.1109/TGRS.2026.3736453](https://doi.org/10.1109/TGRS.2026.3736453)

### 相关文献

**H. Fang, H. Yao, H. Zhang, Y.-C. Huang, and R. D. van der Hilst**,  
“Direct inversion of surface wave dispersion for three-dimensional shallow crustal structure based on ray tracing: methodology and application,”  
*Geophysical Journal International*, vol. 201, no. 3, pp. 1251–1263, June 2015.  
doi: [10.1093/gji/ggv080](https://doi.org/10.1093/gji/ggv080)

**M. J. Bianco and P. Gerstoft**,  
“Travel Time Tomography With Adaptive Dictionaries,”  
*IEEE Transactions on Computational Imaging*, vol. 4, no. 4, pp. 499–511, 2018.  
doi: [10.1109/TCI.2018.2862644](https://doi.org/10.1109/TCI.2018.2862644)

## 致谢

DSurfTomo-LST 由 DSurfTomo 程序发展而来。衷心感谢方洪健教授和姚华建教授开发并公开共享 DSurfTomo 源代码。DSurfTomo 为本程序的实现和后续方法扩展提供了重要基础。

本程序包中用于测试和演示的面波频散数据取自 DSurfTomo 程序包。感谢原作者提供相关程序、示例数据和使用资料。

DSurfTomo-LST 中的局部稀疏建模和自适应字典学习采用了 Michael J. Bianco 和 Peter Gerstoft 提出的 LST 方法，并使用了两位作者公开的相关代码，对其进行了适配和改写，使其能够用于 DSurfTomo 的三维面波频散直接反演框架。衷心感谢两位作者在相关方法研究和代码公开共享方面所作的贡献。

---

# English

## Overview

DSurfTomo-LST is an adaptive-dictionary-regularized tomography program developed from the DSurfTomo framework for direct inversion of surface-wave dispersion data.

The program directly inverts interstation surface-wave dispersion measurements for a three-dimensional shear-wave velocity model, without requiring intermediate two-dimensional phase- or group-velocity maps. DSurfTomo-LST retains the Fast Marching Method (FMM), ray-path updating, and three-dimensional sensitivity-matrix calculation of DSurfTomo, while introducing local sparse modeling and adaptive dictionary learning into the inversion.

The inversion starts with Laplacian regularization to establish the large-scale velocity structure and then switches to dictionary-based regularization. Local patches are sparsely represented using Orthogonal Matching Pursuit (OMP), and the dictionaries are updated using Iterative Thresholding and signed K-Means (ITKM). An independent dictionary is used for each inverted depth layer, with an additional depth-coupling term to maintain continuity between neighboring layers.

This repository provides a Windows 64-bit executable, example input files, and a user manual. The source code is planned for public release in 2027, following the completion of the related ongoing research project.

## Main Files

```text
DSurfTomo-LST/
├── README.md
├── DSurfTomo_lst.exe
├── DSurfTomo_lst.in
├── MOD
├── MOD.true
├── surfdataTB.dat
├── Run.bat
└── Manual/
    └── DSurfTomo-LST_用户手册_CN.html
```

## Running the Program

On Windows, double-click:

```text
Run.bat
```

or run the following command from CMD or PowerShell in the program directory:

```text
DSurfTomo_lst.exe DSurfTomo_lst.in
```

For details on the input parameters, data format, and output files, see:

[DSurfTomo-LST Chinese User Manual](DSurfTomo-LST_用户手册.html)

## Citation

If this code is useful for your research, please consider citing:

**Z. Li, J. Ding, X. Cheng, R. He, X. Zhou and Z. Chen**,  
“Adaptive-Dictionary-Regularized 3-D Direct Inversion of Surface-Wave Dispersion Data,”  
*IEEE Transactions on Geoscience and Remote Sensing*, vol. 64,  
pp. 5919117-5919117, 2026, Art. no. 5919117.  
doi: [10.1109/TGRS.2026.3736453](https://doi.org/10.1109/TGRS.2026.3736453)

### Related References

**H. Fang, H. Yao, H. Zhang, Y.-C. Huang, and R. D. van der Hilst**,  
“Direct inversion of surface wave dispersion for three-dimensional shallow crustal structure based on ray tracing: methodology and application,”  
*Geophysical Journal International*, vol. 201, no. 3, pp. 1251–1263, June 2015.  
doi: [10.1093/gji/ggv080](https://doi.org/10.1093/gji/ggv080)

**M. J. Bianco and P. Gerstoft**,  
“Travel Time Tomography With Adaptive Dictionaries,”  
*IEEE Transactions on Computational Imaging*, vol. 4, no. 4, pp. 499–511, 2018.  
doi: [10.1109/TCI.2018.2862644](https://doi.org/10.1109/TCI.2018.2862644)

## Acknowledgements

DSurfTomo-LST was developed from the DSurfTomo program. We sincerely thank Prof. Hongjian Fang and Prof. Huajian Yao for developing DSurfTomo and making its source code publicly available. DSurfTomo provided an important foundation for the implementation and further development of this work.

The surface-wave dispersion data included in this package for testing and demonstration are taken from the DSurfTomo package. We gratefully acknowledge the original authors for providing the program, example data, and accompanying documentation.

The local sparse modeling and adaptive dictionary-learning components of DSurfTomo-LST adopt the LST method proposed by Michael J. Bianco and Peter Gerstoft and also make use of their publicly available related code. The code was adapted and modified for integration with the three-dimensional direct surface-wave dispersion inversion framework of DSurfTomo. We sincerely appreciate their contributions to the methodology and their sharing of the associated code.
