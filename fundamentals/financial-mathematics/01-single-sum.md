# 单笔现金流现值与终值 (Single Sum PV & FV)

> 在时间价值基础上，学习如何处理单笔金额在不同时间点的转换。

## 学习目标

- 掌握单笔现金流的终值 (FV) 与现值 (PV) 计算公式。
- 理解复利频率（年、半年、季度、月、日）的影响。
- 学会使用有效年利率 (EAR) 做利率换算，比较不同复利结构。
- 能够利用 Excel 或计算器验证结果。

## 基本公式回顾

```math
FV = PV \,(1 + r)^n \qquad \text{和} \qquad PV = \frac{FV}{(1 + r)^n}
```

其中：

- PV (Present Value)：现值
- FV (Future Value)：终值
- r：每期利率
- n：期数（复利次数）

## 复利频率的影响

若名义年利率为 `r_{nom}`，一年复利 `m` 次，则每期利率为 `r_{nom} / m`，期数 `n = m × 年数`。

终值计算：

```math
FV = PV \left(1 + \frac{r_{nom}}{m}\right)^{m \times t}
```

例：存入 10,000 元，名义年利率 6%，每年复利四次（季度）。1 年后终值：

```
FV = 10,000 × (1 + 0.06 / 4)^(4 × 1) ≈ 10,618
```

## 有效年利率 (Effective Annual Rate, EAR)

比较不同复利频率的利率时，需要换算为同一基准，常用 EAR：

```math
EAR = \left(1 + \frac{r_{nom}}{m}\right)^m - 1
```

例：名义利率 12%，分月复利，则 `EAR = (1 + 0.12/12)^12 - 1 ≈ 12.68%`。

若是半年复利，`EAR = (1 + 0.12/2)^2 - 1 = 12.36%`。

## 连续复利

连续复利公式：

```math
FV = PV \times e^{r \times t} \qquad \text{或} \qquad PV = FV \times e^{-r \times t}
```

其中 `e` 是自然常数，`r` 为连续复利的年利率。

例：`PV = 10,000`，连续复利年利率 5%，一年后：`FV = 10,000 × e^{0.05} ≈ 10,512`。

## Excel / 计算器提示

- Excel：`FV(rate, nper, pmt, pv)`；单笔金额时 `pmt = 0`。
- 现值：`PV(rate, nper, pmt, fv)`。
- RATE、NPER 函数可求未知利率或期数。
- 财务计算器（如 HP-12C）可直接输入 PV、FV、I/Y、N 计算。

## 快速自测

1. 你希望 5 年后得到 50,000 元，银行提供名义年利率 4%，按月复利。现在需要存入多少？
2. 两个银行产品：A 提供年利率 5%，半年复利；B 提供年利率 4.8%，按月复利。哪个实际收益更高？
3. 如果资金按连续复利 6% 增长，多久可以翻倍？（Hint: 使用对数）

### 参考答案与解析

1. `r = 0.04/12`，`n = 12×5 = 60`。`PV = 50,000 / (1 + 0.04/12)^60 ≈ 41,093`。
2. A 的 EAR = `(1 + 0.05/2)^2 - 1 ≈ 5.0625%`；B 的 EAR = `(1 + 0.048/12)^12 - 1 ≈ 4.918%`，因此 A 更高。
3. 解 `2 = e^{0.06 t}`，即 `t = ln(2)/0.06 ≈ 11.55` 年。

## 延伸阅读

- CFA 一级 Quantitative Methods：Compounding and Discounting
- Excel 帮助文档：`FV`, `PV`, `RATE`
- Investopedia：Effective Annual Rate
- Quantitative finance 教材中的利率换算章节

---

下一步学习 `02-annuity.md`，处理多期等额现金流（普通年金、预付年金、永续年金）。
