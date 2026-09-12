# 积分理论

Bourbaki《数学原本》(Éléments de mathématique) 中《积分理论》一卷的自学笔记。

## 内容

测度的积分、局部紧空间上的测度、Hausdorff 拓扑空间上的测度、Haar 测度、测度的扩张与 L^p 空间、向量值积分、卷积与表示、凸性不等式、Riesz 空间，以及 Hilbert 空间补注（附录）。

## 编译

须使用 XeLaTeX（`structure.sty` 依赖 ctexbook 与 XeLaTeX 特性）：

```bash
xelatex main.tex
```

`main.pdf` 未纳入版本控制，需本地编译生成。

## 目录结构

```
main.tex          编译入口
structure.sty     样式包：页面设置、定理环境（tcolorbox）、引用（hyperref + cleveref）、数学符号库
quiver.sty        交换图支持
Content/          分章正文，每章一个目录，由 index.tex 汇总 \input
commit.py         一键提交并推送到 GitHub
setup_mode.py     习题编排模式切换（独立习题集 / 章末习题）
update_cwl.py     从 structure.sty 提取符号，更新 TeXStudio 补全文件
merge_symbols.py  把各笔记新增的符号回填到模板
```

## 脚本

```bash
python commit.py "提交说明"    # 提交并推送，说明可省略（默认「更新笔记」）
python setup_mode.py 1|2      # 切换习题编排模式
python update_cwl.py          # 同步 TeXStudio 符号补全
python merge_symbols.py       # 预览待回填符号（加 --write 执行）
```

## 说明

正文使用英文标点；定理与证明环境由 `structure.sty` 提供。编译产物（aux / log / out / toc / synctex.gz / pdf）与备份文件已在 `.gitignore` 中排除。
