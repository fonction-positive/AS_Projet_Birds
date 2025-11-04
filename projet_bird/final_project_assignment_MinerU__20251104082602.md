# Final Project – Birds Biodiversity Temporal Trends

# Overview

As the concluding project for the applied statistics course, you will conduct an independent analysis of the long-term monitoring data collected in the Birds Biodiversity programme. Your goal is to quantify how biodiversity indicators have evolved over time, provide sound statistical uncertainty assessments, and highlight species-specific stories that emerge from the dataset.

To promote genuine data-driven thinking, this assignment specifies what questions must be addressed without prescribing how you should answer them. You are free to select the statistical techniques, models, and visual encodings you feel are most appropriate, provided that you justify your choices.

This project introduces a new dataset that you have not analysed previously in the course: the multi-year Birds Biodiversity monitoring records stored in projects/birds-biodiversity/data/raw/Observations 2012-2025.x1sx. You may reuse any helper modules in the repository (for example src/data_io.py) or build your own tooling if it better suits your workflow.

# Core Deliverables

Your final submission must include:

1. Technical report (Markdown or PDF) explaining your approach, the indicators you studied, and the conclusions you reached. The narrative should be self-contained and understandable to a statistically literate audience.  
2. Notebook(s) or scripts that implement your analysis reproducibly. Structure your code so that another analyst can re-run it from a clean checkout.  
3. Figures and tables that support your findings (export them to projects/birds-biodiversity/figures and projects/birds-biodiversity/results respectively). Label axes clearly and include units.

# Key Questions to Address

# 1. Dataset Familiarisation and Descriptive Analysis

- Provide an overview of the dataset structure: table dimensions, key columns, time coverage, and unique identifiers (transects, observers, species, etc.).  
- Produce descriptive statistics that quantify the distribution of relevant variables (counts, observer effort, and environmental descriptors such as weather conditions recorded during surveys). Pay special attention to how observation effort varies across time and space, since it influences the reliability and interpretation of downstream results. Use both tabular summaries and visualisations.  
- Discuss any notable data quality considerations (missing values, outliers, anomalous periods) that may influence subsequent analyses.

# 2. Multi-Year Indicator Trends

- Select at least three biodiversity or sampling indicators that you believe are informative (e.g., spatial coverage, species diversity, density, observer effort). Justify each choice.  
- For every indicator, compute annual estimates over the full 2014–2025 horizon and provide confidence intervals that reflect estimation uncertainty (you decide on the method and confidence level).  
- Quantify and interpret temporal trends. You may use linear models, generalized models, smoothing, or any other defensible approach, but explain why it suits the indicator's behaviour.

# 3. Species-Level Evolution

- Identify a subset of bird species that you consider interesting (e.g., high abundance, conservation concern, distinctive trends).  
- For each selected species, analyse how its recorded presence or counts have changed over time. Present confidence intervals and comment on the limitations of your estimation procedure.  
- Discuss potential ecological or operational reasons behind the patterns you observe (based on external knowledge or plausible hypotheses).

# 4. Synthesis and Recommendations

Summarise the main insights you discovered about the monitoring programme. Highlight converging evidence across indicators as well as any contradictions.

- Outline actionable recommendations for future data collection or biodiversity management. These can include methodological improvements, additional indicators to monitor, or follow-up questions that deserve investigation.

- Reflect on limitations: data quality, modelling assumptions, sensitivity to methodological choices, etc.

# Guidance (Non-Prescriptive)

# Expectations

- The goal is not to produce breakthrough ecological findings, but to demonstrate statistical creativity and rigour in how you analyse the data.  
- You are encouraged to propose novel indicators or visualisations, provided that you justify them and implement them correctly.  
- Actionable biodiversity management recommendations are welcome but not mandatory; you will not be penalised if no clear actions emerge.  
Incorrect conclusions caused by flawed assumptions, improper methodology, or coding mistakes will be penalised heavily, so validate every step carefully.  
You will only receive the raw dataset and this assignment brief. Feel free to rely on standard statistical libraries and to create your own helper code as needed. AI assistance is permitted, but you are responsible for every line of code you submit.  
- Visual outputs should be polished and professional. If warnings remain in the execution logs, explain why they could not or should not be suppressed.  
- Ensure that code is well commented and easy to follow so that reviewers can understand your reasoning without guesswork.  
- Confidence intervals can be obtained via analytical formulas, resampling, Bayesian intervals, or other defensible methods. Argue why your choice is appropriate for each indicator/species.  
- When modelling trends, check diagnostics to ensure your assumptions are reasonable (residual plots, robustness checks, alternative specifications, etc.).  
- Keep visualisations clear and focused. A small number of high-quality figures is preferable to a large set of redundant plots.

# Suggested Workflow

1. Familiarise yourself with the data: explore structure, missingness, notable events, and potential covariates (transects, observers, weather conditions).  
2. Define indicators and species scope: document why each metric or species was chosen before diving into coding.  
3. Implement the analysis: structure your notebooks/scripts into reusable sections (data loading, indicator computation, inference, visualisation).  
4. Validate results: sanity-check intermediate outputs and ensure reproducibility from a clean run.  
5. Prepare the report and artefacts: polish the narrative, export figures/tables, and verify that file paths point to the expected directories.

# Evaluation Criteria

- Statistical soundness (confidence intervals and trends are computed appropriately, methods are justified).  
Insight and interpretation (discussion goes beyond describing plots to making meaningful inferences).  
- Clarity and reproducibility (code runs from scratch, report is well structured, figures are informative).  
- Creativity and initiative (evidence of thoughtful indicator selection, methodological experimentation, or novel species/observers insights).

# Submission

- Package all materials (report, code, notebooks, figures, tables, README) into a single ZIP archive named FinalProject_Lastname1_Lastname2_Lastname3.zip.  
- Email the archive to stephane.rivaud@universite-paris-saclay.fr before 6 November, 23:59 (Paris time). Late submissions will not be accepted under any circumstances.  
- Include a README at the root of the archive describing the folder contents and reproduction instructions. Provide environment details, entry points, and any runtime considerations.  
- The report may be a standalone PDF that references generated outputs, or the entire study may be documented directly within notebook(s). Choose the format that best showcases your analysis.

Each group should list all members and student IDs in both the README and the report/notesbook.  
- An oral defence will be held between 7 and 14 November. Each group will present for 10 minutes followed by a 5-minute Q&A.

Good luck, and use this project to demonstrate the full breadth of statistical skills you've acquired throughout the course.







# 期末项目——鸟类生物多样性时间趋势

## 概述

作为应用统计学课程的结课项目，你将独立分析"鸟类生物多样性"计划中收集的长期监测数据。你的目标是量化生物多样性指标如何随时间演变，提供可靠的统计不确定性评估，并突出数据集中出现的特定物种的故事。

为促进真正的数据驱动思维，本任务指定了需要解决的问题，但未规定你应如何回答。你可以自由选择你认为最合适的统计技术、模型和可视化编码方式，前提是你要证明选择的合理性。

本项目引入了一个你在课程中未曾分析过的新数据集：存储在 `projects/birds-biodiversity/data/raw/Observations 2012-2025.x1sx` 中的多年鸟类生物多样性监测记录。你可以复用代码库中的任何辅助模块（例如 `src/data_io.py`），或者如果更适合你的工作流程，也可以构建自己的工具。

## 核心交付成果

你的最终提交必须包括：

1.  **技术报告**：解释你的方法、你研究的指标以及你得出的结论。叙述应自成一体，让具备统计知识的读者能够理解。
2.  **Notebook或脚本**：可重复地实现你的分析。结构化你的代码，以便其他分析师可以从干净的代码库重新运行它。
3.  **图表和表格**：支持你的发现。将它们分别导出到 `projects/birds-biodiversity/figures` 和 `projects/birds-biodiversity/results` 目录。清晰标注坐标轴并包含单位。

## 需要解决的关键问题

### 1. 数据集熟悉与描述性分析

*   提供数据集结构概览：表格维度、关键列、时间覆盖范围以及唯一标识符（样线、观察者、物种等）。
*   生成描述性统计量，量化相关变量的分布（计数、观察者努力量以及环境描述符，如调查期间记录的天气条件）。特别注意观察努力量如何随时间和空间变化，因为这会影响下游结果的可靠性和解释。同时使用表格摘要和可视化。
*   讨论任何可能影响后续分析的显著数据质量问题（缺失值、异常值、异常时期）。

### 2. 多年指标趋势

*   选择至少三个你认为具有信息量的生物多样性或采样指标（例如，空间覆盖度、物种多样性、密度、观察者努力量）。证明每个选择的合理性。
*   对于每个指标，计算2014-2025整个时间范围内的年度估计值，并提供反映估计不确定性的置信区间（方法和置信水平由你决定）。
*   量化和解释时间趋势。你可以使用线性模型、广义模型、平滑方法或任何其他可辩护的方法，但要解释为什么它适合该指标的行为。

### 3. 物种层面演变

*   确定一个你认为有趣的鸟类物种子集（例如，高丰度、受保护关注、独特趋势）。
*   对于每个选定的物种，分析其记录到的存在或计数如何随时间变化。呈现置信区间并评论你估计程序的局限性。
*   讨论你观察到的模式背后潜在的生态或操作原因（基于外部知识或合理的假设）。

### 4. 综合与建议

总结你关于该监测计划发现的主要见解。强调跨指标的确凿证据以及任何矛盾之处。

*   概述对未来数据收集或生物多样性管理的可行建议。这些可以包括方法改进、需要监测的额外指标或值得调查的后续问题。
*   反思局限性：数据质量、建模假设、对方法选择敏感性等。

## 指导（非规定性）

### 期望

*   目标不是产生突破性的生态发现，而是展示你在数据分析方面的统计创造力和严谨性。
*   鼓励你提出新颖的指标或可视化，前提是你能证明其合理性并正确实施。
*   欢迎提出可行的生物多样性管理建议，但不是强制性的；如果没有明确的行动出现，你不会受到惩罚。
*   由于有缺陷的假设、不当的方法或编码错误导致的错误结论将受到严重处罚，因此请仔细验证每一步。
*   你只会收到原始数据集和本任务简介。可以自由依赖标准统计库并根据需要创建自己的辅助代码。允许使用AI辅助，但你要对你提交的每一行代码负责。
*   可视化输出应精美且专业。如果执行日志中仍有警告，请解释为什么不能或不应该抑制它们。
*   确保代码注释良好且易于理解，以便审阅者无需猜测就能理解你的推理。
*   置信区间可以通过解析公式、重采样、贝叶斯区间或其他可辩护的方法获得。论证你的选择对每个指标/物种是合适的。
*   当建模趋势时，检查诊断以确保你的假设是合理的（残差图、稳健性检查、替代设定等）。
*   保持可视化清晰和聚焦。少量高质量的图表优于大量冗余的绘图。

### 建议工作流程

1.  熟悉数据：探索结构、缺失情况、显著事件和潜在协变量（样线、观察者、天气条件）。
2.  定义指标和物种范围：在深入编码之前，记录选择每个度量或物种的原因。
3.  实施分析：将你的notebook/脚本结构化为可重用的部分（数据加载、指标计算、推断、可视化）。
4.  验证结果：对中间输出进行合理性检查，并确保从干净运行开始具有可重复性。
5.  准备报告和成果物：完善叙述，导出图表/表格，并验证文件路径指向预期的目录。

### 评估标准

*   统计合理性（置信区间和趋势计算得当，方法论证充分）。
*   洞察力和解释力（讨论超越描述图表，进行有意义的推断）。
*   清晰度和可重复性（代码可从零开始运行，报告结构良好，图表信息丰富）。
*   创造性和主动性（在指标选择、方法实验或新颖的物种/观察者见解方面体现出深思熟虑的证据）。

## 提交

*   将所有材料（报告、代码、notebook、图表、表格、README）打包成一个名为 `FinalProject_LastName1_LastName2_LastName3.zip` 的ZIP压缩文件。
*   在**11月6日23:59（巴黎时间）之前**将压缩包通过电子邮件发送至 `stephane.rivaud@universite-paris-saclay.fr`。任何情况下均不接受逾期提交。
*   在压缩包的根目录包含一个README文件，描述文件夹内容并提供复现说明。提供环境详情、入口点和任何运行时注意事项。
*   报告可以是一个独立的PDF，引用生成的输出，或者整个研究可以直接记录在notebook中。选择最能展示你分析的格式。
*   每个小组应在README和报告/notebook中列出所有成员和学生ID。
*   **口头答辩将于11月7日至14日期间举行**。每个小组将进行10分钟的演示，然后是5分钟的问答。

祝你好运，并利用这个项目来展示你在整个课程中学到的全面统计技能。







# 鸟类生物多样性数据集概览

本文档帮助您快速了解期末项目的主要数据集 `data/raw/Observations 2012-2025.xlsx` 的内容。

## 数据来源与范围
- **项目**：马提尼克岛繁殖鸟类监测计划（应用统计学期末项目）。
- **覆盖年份**：2012–2025（含），"observation" 工作表中的每行代表一条观测记录。
- **地理范围**：全岛范围的样线；每条观测记录都关联一个监测点。

## 工作簿结构
此Excel工作簿包含三个您需要结合使用的工作表：

| 工作表名称     | 用途                                                         |
| -------------- | ------------------------------------------------------------ |
| `ESPECES`      | 鸟类分类辅助信息（学名/法语名、迁徙状态、特有 vs. 引入）。   |
| `GPS-MILIEU`   | 站点目录，每行一个观测点（包含样线ID、点位ID、栖息地类型、GPS标签）。 |
| `NOM FRANÇAIS` | 观测日志 – 核心事实表，每行代表一次点位访问，包含数量统计和探测元数据。 |

在分析过程中，请始终将映射表（`ESPECES`, `GPS-MILIEU`）与观测数据结合使用，以便用物种和栖息地信息来丰富事实表。



## 观测数据表列名解释：(NOM FRANCAIS)

**基本信息列：**

1. `Nom observateur` - 观察者姓名
2. `code département` - 部门代码 (972 = 马提尼克)
3. `Nom transect` - 样线名称
4. `date` - 观测日期
5. `1er, 2e ou 3e passage` - 第几次访问 (1/2/3)
6. `nuages` - 云量等级
7. `pluie` - 降雨等级
8. `vent` - 风力等级
9. `visibilité` - 能见度等级
10. `N° point` - 观测点编号 (1-10)
11. `heure début` - 开始时间
12. `ESPECE` - 物种名称

**距离带计数列 (按探测方式分类)：**

- **< 25m**: `Auditif`, `Visuel` (听觉、视觉探测)
- **<50m**: `Auditif`, `Visuel`
- **<100m**: `Auditif`, `Visuel`
- **> 100m**: `Auditif`, `Visuel`
- **vol**: `Auditif`, `Visuel` (飞行中的鸟类)

**汇总列：**

- `totaux` - 总计数
- 其他汇总列 (听觉总计、视觉总计、组合计数等)



## 观测数据收集方式
1.  **样线即站点** – 每条样线对应一个监测站点。每个站点包含沿样线布置的 **10个固定观测点**。
2.  **访问协议** – 进行调查时，观察者前往站点，从点1开始，记录鸟类 **5分钟**，然后步行至下一个点重复此过程，直到完成全部10个点。
3.  **观察者频率** – 一位观察者对给定站点的访问 **最多两次**（协议未明确此限制是针对每个季节、每年还是整个项目期间）。
4.  **探测类型** – 每条记录都将探测分类为 **视觉**、**听觉** 或 **两者兼有**，这使得分析特定模式的探测率成为可能。

## 每行数据代表什么
- 在特定日期对某个观测点的一次访问。
- 汇总了在该次点位访问中探测到的物种、个体数量、探测方式和努力量元数据。

## 关键列（高层次）
- **`observation_id`** – 记录的唯一标识符。
- **`transect_id` / `point_id`** – 位置元数据；`point_id` 在每个样线内从1到10。
- **`date` / `year`** – 访问时间戳；`year` 便于进行趋势分析。
- **`observer_id`** – 执行样线访问人员的匿名标识符。
- **`species_code` / `species_name`** – 观测到的物种。
- **`individual_count`** – 在5分钟观测窗口内探测到的个体数量。
- **`detection_type`** – 分类字段，指示视觉、听觉或两者。
- **努力量指标**（例如，`visit_duration_minutes`, `points_completed`）– 在标准化计数或估算经努力量调整的指数时非常重要。

> 可能存在其他列（例如，天气、备注）。加载后请检查标题行以确认可用性。

## 推荐的初步步骤
1.  使用pandas加载数据：
    ```python
    import pandas as pd
    df = pd.read_excel("projects/birds-biodiversity/data/raw/Observations 2012-2025.xlsx")
    ```
2.  使用 `df.info()` 和 `df.head()` **检查模式一致性**。
3.  **验证努力量假设** – 确认每条样线有10个点，查找完成访问点数少于10的站点，并注意探测模式的分布。
4.  **创建概览性摘要** – 按站点划分的物种丰富度、观察者工作量、年度总数、探测模式份额。

## 使用期望
- 将工作簿视为只读；在其他地方派生出新的表格/笔记本。
- 在报告中引用为 "Martinique Breeding Bird Monitoring, 2012–2025"。
- 共享数据子集时，请导出副本，而不是修改原始提取文件。

祝你好运，并记得将你的探索性数据分析与项目任务要求联系起来！⚡️