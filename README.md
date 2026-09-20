# 积分理论

## 主要内容

Bourbaki《数学原本》(Éléments de mathématique) 中《积分理论》一卷的自学笔记。

## 说明

本笔记按 Bourbaki 原书的章节层级组织，对应关系如下：

| Bourbaki 原书 | 本笔记 | 本仓库中的示例 |
|---|---|---|
| 章（Chapitre） | `Content/` 下的**章目录** | `1_Inequalities_of_Convexity/` |
| 节（§） | 章目录下的**节目录** | `1_The_fundamental_inequality_of_convexity/` |
| 小节（1、2、…） | 节目录下的 **`.tex` 文件** | `1_Subsection_Name.tex` |

- 目录与文件名取该层级标题的**英译**，并加编号前缀（`1_`、`2_`…，不加前导零）。
- 中文标题写在 `\chapter{...}` 与 `\section{...}` 中：`\chapter{}` 用该**节目录**名的中译，`\section{}` 用该**文件**名的中译。
- 每层目录各有一个 `index.tex`，按顺序汇总对下一层的 `\input`。

定理环境用法、交叉引用（`\cref`）、符号库维护等 **tex 层面的规定**，另见模板《笔记写作》的 README。

## 内容结构

```
Content/
├─ 1_Inequalities_of_Convexity/
│  ├─ 1_The_fundamental_inequality_of_convexity/
│  ├─ 2_The_inequalities_of_Hölder_and_Minkowski/
│  └─ 3_The_semi-norms_Np/
├─ 2_Riesz_Spaces/
│  ├─ 1_Riesz_spaces_and_fully_lattice-ordered_spaces/
│  └─ 2_Linear_forms_on_a_Riesz_space/
├─ 3_Measures_on_Locally_Compact_Spaces/
│  ├─ 1_Measures_on_a_locally_compact_space/
│  ├─ 2_Support_of_a_measure/
│  ├─ 3_Integrals_of_continuous_vector-valued_functions/
│  └─ 4_Products_of_measures/
├─ 4_Extension_of_a_Measure_Lp_Spaces/
│  ├─ 1_Upper_integral_of_a_positive_function/
│  ├─ 2_Negligible_functions_and_sets/
│  ├─ 3_Lp_spaces/
│  ├─ 4_Integrable_functions_and_sets/
│  ├─ 5_Measurable_functions_and_sets/
│  ├─ 6_Convexity_inequalities/
│  └─ 7_Barycenters/
├─ 5_Integration_of_Measures/
│  ├─ 1_Essential_upper_integral/
│  ├─ 2_Summable_families_of_positive_measures/
│  ├─ 3_Integration_of_positive_measures/
│  ├─ 4_Integration_of_positive_point_measures/
│  ├─ 5_Measures_defined_by_numerical_densities/
│  ├─ 6_Images_of_a_measure/
│  ├─ 7_Integration_with_respect_to_an_induced_measure/
│  └─ 8_Products_of_measures/
├─ 6_Vectorial_Integration/
│  ├─ 1_Integration_of_vector-valued_functions/
│  ├─ 2_Vectorial_measures/
│  ├─ 3_Disintegration_of_measures/
│  └─ Appendix_Complements_on_topological_vector_spaces/
├─ 7_Haar_Measure/
│  ├─ 1_Construction_of_a_Haar_measure/
│  ├─ 2_Quotient_of_a_space_by_a_group_homogeneous_spaces/
│  ├─ 3_Applications_and_examples/
│  ├─ Appendix_I/
│  └─ Appendix_II/
├─ 8_Convolution_and_Representations/
│  ├─ 1_Convolution/
│  ├─ 2_Linear_representations_of_groups/
│  ├─ 3_Convolution_of_measures_on_groups/
│  ├─ 4_Convolution_of_measures_and_functions/
│  └─ 5_The_space_of_closed_subgroups/
├─ 9_Measures_on_Hausdorff_Topological_Spaces/
│  ├─ 1_Premeasures_and_measures_on_a_topological_space/
│  ├─ 2_Operations_on_measures/
│  ├─ 3_Measures_and_additive_set_functions/
│  ├─ 4_Inverse_limits_of_measures/
│  ├─ 5_Measures_on_completely_regular_spaces/
│  └─ 6_Promeasures_and_measures_on_a_locally_convex_space/
└─ 10_Annex_Complements_on_Hilbert_spaces/
   ├─ 1_Trace_of_a_quadratic_form_with_respect_to_another/
   └─ 2_Hilbert-Schmidt_mappings/
```

## 文件结构

```
main.tex          编译入口
structure.sty     样式包：页面设置、定理环境、引用、数学符号库
quiver.sty        交换图支持
Content/          分章正文，每章一个目录，由 index.tex 汇总 \input
commit.py         一键提交并推送（说明见 commit.md）
setup_mode.py     习题编排模式切换（说明见 setup_mode.md）
README.md         本文件：项目说明
CHANGELOG.md      更新日志：tex 配置调整与正文内容调整
```

各脚本的选项与功能分别见 [commit.md](commit.md) 与 [setup_mode.md](setup_mode.md)；符号库由上层目录的 `symbols.py` 统一管理。

## 编译

本笔记使用自建的【笔记写作】模板（样式包 `structure.sty`），须用 **XeLaTeX** 编译：

```bash
xelatex main.tex
```

- **编译环境**：XeLaTeX。模板依赖 ctexbook 与 XeLaTeX 特性，**不支持 pdfLaTeX**。
- **TeXStudio**：建议 4.0 或更高版本。
- `main.pdf` 未纳入版本控制，需本地编译生成。
