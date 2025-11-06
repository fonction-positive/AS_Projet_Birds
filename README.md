# Bird Observation Data Analysis Project
# 鸟类观测数据分析项目

**Course**: Applied Statistics / 应用统计学  
**Institution**: Université Paris-Saclay  
**Academic Year**: 2024-2025  
**Submission Date**: November 2025 / 2025年11月

---

## 📋 Project Overview / 项目概述

This project analyzes bird observation data from 2014-2025 to assess biodiversity trends, species population dynamics, and environmental influences. Using statistical methods including GLM, bootstrap resampling, and diversity indices, the analysis provides insights into temporal patterns and ecological changes.

本项目分析 2014-2025 年的鸟类观测数据，以评估生物多样性趋势、物种种群动态和环境影响。使用 GLM、自举重采样和多样性指数等统计方法，分析揭示了时间模式和生态变化。

### Project Objectives / 项目目标

1. **Data Quality Assessment** / 数据质量评估
   - Clean and validate observational records
   - Handle missing values and outliers systematically
   
2. **Biodiversity Analysis** / 生物多样性分析
   - Calculate species richness, Shannon index, Hill numbers, and evenness
   - Assess temporal trends with statistical confidence intervals
   
3. **Temporal Patterns** / 时间模式
   - Analyze annual and monthly trends (2014-2025)
   - Identify seasonal variations in bird populations
   
4. **Environmental Effects** / 环境影响
   - Model weather influences using GLM
   - Evaluate extreme weather impacts on observations
   
5. **Effort Adjustment** / 努力量校正
   - Account for variable observation effort across years
   - Use Poisson/Negative Binomial models for robust estimates

## 📊 Dataset / 数据集

The dataset consists of three main components:

数据集包含三个主要部分:

1. **Observation Data** (`NOM FRANÇAIS` sheet)
   - Observer information / 观察者信息
   - Temporal data (date, time, visit number) / 时间数据(日期、时间、访问次数)
   - Environmental conditions (clouds, rain, wind, visibility) / 环境条件(云量、降雨、风力、能见度)
   - Bird counts by distance bands (25m, 50m, 100m, >100m) / 按距离带的鸟类计数
   - Detection methods (auditory, visual, in-flight) / 检测方法(听觉、视觉、飞行)

2. **Species Reference** (`ESPECES` sheet)
   - French common names / 法语俗名
   - Scientific names / 学名
   - Migration status / 迁徙状态

3. **Site Information** (`GPS-MILIEU` sheet)
   - GPS coordinates (UTM) / GPS 坐标
   - Habitat types / 栖息地类型
   - Transect and point identifiers / 样线和点位标识符

### Data File / 数据文件

- **Filename**: `Observations 2012-2025.xlsx`
- **Format**: Microsoft Excel with multiple sheets
- **Size**: ~25,000 observation records / 约 25,000 条观测记录
- **Temporal Coverage**: 2014-2025 (12 years) / 时间跨度: 2014-2025 年(12 年)
- **Spatial Coverage**: Multiple transects across different habitat types / 多条样线覆盖不同栖息地类型

## 🔧 Installation / 安装

### Prerequisites / 前提条件

```bash
Python 3.8 or higher
Jupyter Notebook or JupyterLab
```

### Required Libraries / 所需库

```bash
pip install pandas numpy matplotlib seaborn scipy statsmodels missingno pygam openpyxl
```

### Detailed Dependencies / 详细依赖项

```python
pandas>=1.3.0          # Data manipulation
numpy>=1.21.0          # Numerical computing
matplotlib>=3.4.0      # Plotting
seaborn>=0.11.0        # Statistical visualization
scipy>=1.7.0           # Scientific computing
statsmodels>=0.13.0    # Statistical models (GLM, OLS)
missingno>=0.5.0       # Missing data visualization
pygam>=0.8.0           # Generalized Additive Models
openpyxl>=3.0.0        # Excel file handling
```

## 🚀 Usage / 使用方法

### Quick Start / 快速开始

1. **Clone or download the repository** / 克隆或下载仓库
   ```bash
   cd /path/to/project
   ```

2. **Place your data file** / 放置数据文件
   - Ensure `Observations 2012-2025.xlsx` is in the project directory
   - 确保 `Observations 2012-2025.xlsx` 在项目目录中

3. **Open the Jupyter Notebook** / 打开 Jupyter Notebook
   ```bash
   jupyter notebook bird.ipynb
   ```

4. **Run cells sequentially** / 按顺序运行单元格
   - Execute cells from top to bottom
   - 从上到下执行单元格

### Analysis Workflow / 分析流程

The notebook is organized into the following sections:

笔记本按以下部分组织:

#### 1. Data Loading / 数据加载
- Import Excel data with appropriate column names
- 使用适当的列名导入 Excel 数据

#### 2. Load Observation Data / 加载观测数据
- Parse observation records from main sheet
- 从主工作表解析观测记录

#### 3. Load Species Reference Data / 加载物种参考数据
- Import species metadata
- 导入物种元数据

#### 4. Load Site and Habitat Data / 加载站点和栖息地数据
- Import GPS and habitat information
- 导入 GPS 和栖息地信息

#### 5. Exploratory Data Analysis / 探索性数据分析
- Dataset overview
- Annual observation trends
- Spatial coverage over time
- Observation effort analysis

#### 6. Data Preprocessing / 数据预处理
- Handle duplicate records / 处理重复记录
- Handle missing values / 处理缺失值
- Data cleaning strategy / 数据清理策略
- Handle weather outliers / 处理天气异常值
- Count outliers / 计数异常值

#### 7. Biodiversity Indicators / 生物多样性指标
- Multi-year diversity indicators with bootstrap confidence intervals
- Trend significance analysis
- Effort-adjusted encounter rates

#### 8. Species-Specific Analysis / 物种特定分析
- Annual trends for target species
- Monthly trends for target species
- Focus on high-abundance species like *Elénie siffleuse*

#### 9. Environmental Influences / 环境影响分析
- Weather trends over time
- Extreme weather events
- GLM analysis of weather effects

#### 10. Summary and Conclusions / 总结与结论
- Key findings synthesis
- Data quality assessment
- Recommendations for future monitoring

## 📈 Key Analyses / 核心分析

### 1. Diversity Indicators / 多样性指标

**Metrics Calculated** / 计算的指标:
- **Species Richness**: Number of unique species per year / 每年唯一物种数
- **Shannon Index**: Community diversity measure / 群落多样性测度
- **Evenness (Pielou's J')**: Distribution uniformity / 分布均匀性
- **Hill Numbers (D1, D2)**: Effective species counts / 有效物种计数
- **Spatial Coverage**: Proportion of transects surveyed / 调查样线比例

**Methods** / 方法:
- Cluster bootstrap resampling (B=1000)
- 95% confidence intervals via Wilson method
- Linear trend testing with p-values

### 2. Effort-Adjusted Encounter Rate / 努力校正后的遇见率

**Model Framework** / 模型框架:
```
count ~ year + covariates + offset(log(effort))
```

**Family Selection** / 家族选择:
- Poisson GLM (if dispersion ≤ 1.5)
- Negative Binomial (if overdispersion detected)

**Outputs** / 输出:
- Annual predicted encounter rates
- 95% confidence intervals
- Trend significance tests

### 3. Species-Specific Trends / 物种特定趋势

**Focus Species** / 重点物种:
- Top 10 most abundant species
- Detailed analysis for *Elénie siffleuse*

**Temporal Scales** / 时间尺度:
- Annual trends (2014-2025)
- Monthly patterns (averaged and year-specific)

**Statistical Approach** / 统计方法:
- Bootstrap confidence intervals
- Poisson GLM with weather covariates
- GAM smoothing for non-linear patterns

## 📊 Visualization Examples / 可视化示例

The notebook generates various plots including:

笔记本生成多种图表,包括:

- **Line plots** with confidence bands / 带置信区间的折线图
- **Boxplots** and density plots for distributions / 分布的箱线图和密度图
- **Heatmaps** for effort across transects and years / 跨样线和年份的努力量热图
- **Bar charts** for species richness and counts / 物种丰富度和计数的柱状图
- **Scatter plots** for environmental relationships / 环境关系的散点图

## � Main Results / 主要结果

### 1. Data Quality / 数据质量

**Dataset Characteristics** / 数据集特征:
- **Total Records**: ~25,000 observations / 约 25,000 条观测记录
- **Temporal Range**: 2014-2025 (12 years) / 时间跨度: 2014-2025 年
- **Unique Species**: ~150 bird species / 约 150 种鸟类
- **Transects**: Multiple sampling lines / 多条样线
- **Missing Data**: <5% after cleaning / 清理后缺失率 <5%

**Data Processing Results** / 数据处理结果:
- ✅ Removed duplicate records
- ✅ Filled missing distance band counts with 0
- ✅ Imputed weather variables using mean values
- ✅ Marked extreme weather conditions (vent=3, pluie≥2, visibilite=4)
- ✅ Filtered invalid weather values (negative wind, non-integer values)

### 2. Temporal Trends / 时间趋势

**Observation Effort** / 观测努力量:
- Significant **increase** in annual records (p < 0.01)
- Expanded spatial coverage from ~10 to ~30 transects
- More consistent monitoring in recent years

**Biodiversity Indicators** / 生物多样性指标:
- **Species Richness**: Stable (no significant trend, p > 0.05)
- **Shannon Diversity**: Stable around H' ≈ 3.5-4.0
- **Evenness (J')**: Consistent at ~0.70-0.75
- **Hill Numbers**: D1 ≈ 30-40 effective species
- **Spatial Coverage**: Increased from 40% to 90% (p < 0.001)

**Key Finding**: Despite increased monitoring effort, diversity metrics remained stable, indicating **ecological stability** rather than biodiversity loss.

**关键发现**: 尽管监测力度增加，多样性指标保持稳定，表明**生态稳定**而非生物多样性丧失。

### 3. Species-Specific Patterns / 物种特定模式

**Top 10 Most Abundant Species** / 前 10 种最丰富的物种:
1. Sucrier à ventre jaune
2. Quiscale merle
3. Sporophile rougegorge
4. Elénie siffleuse ⭐ (focal species)
5. Tourterelle à queue carrée
6. Sporophile cici
7. Tyran gris
8. Saltator gros-bec
9. Viréo à moustaches
10. Merle à lunettes

**Elénie siffleuse Analysis** / Elénie siffleuse 分析:
- **Annual Trend**: Stable with inter-annual variability
- **Seasonal Pattern**: Peak abundance in months 3-5 (March-May)
- **Weather Effects**: Negative association with strong wind (vent=3)
- **GLM Results**: Significant year and month effects (p < 0.05)

### 4. Environmental Influences / 环境影响

**Weather Patterns** / 天气模式:
- **Wind (vent)**: Mean = 1.2, predominantly calm conditions
- **Rain (pluie)**: Mean = 0.8, infrequent precipitation
- **Clouds (nuages)**: Mean = 1.5, variable cloud cover
- **Visibility (visibilite)**: Mean = 1.3, generally good visibility

**Extreme Weather Impact** / 极端天气影响:
- Extreme weather events: ~5-10% of total observations
- **Reduced counts** during strong wind and heavy rain
- Annual frequency: 2-5 extreme weather days per year
- No increasing trend in extreme weather frequency (p > 0.05)

**GLM Model Performance** / GLM 模型性能:
- Poisson model adequate for most species (dispersion ≈ 1.2)
- Weather covariates explain ~15% of variance
- Month effect stronger than weather effect (ANOVA p < 0.001)

## 📁 Project Structure / 项目结构

```
.
├── bird.ipynb                          # Main analysis notebook / 主分析笔记本
├── Observations 2012-2025.xlsx         # Raw data file / 原始数据文件
├── README.md                           # Project documentation / 项目文档
└── requirements.txt                    # Python dependencies / Python 依赖项
```

## 🔬 Methodology / 方法论

### Statistical Methods / 统计方法

1. **Descriptive Statistics** / 描述性统计
   - Summary statistics for all variables
   - Distribution analysis (histograms, boxplots, KDE)

2. **Data Cleaning** / 数据清理
   - Duplicate removal
   - Missing value imputation (mean for weather, 0 for counts)
   - Outlier detection using IQR method

3. **Diversity Indices** / 多样性指数
   - Species Richness: S (number of species)
   - Shannon Index: H' = -Σ(pi × ln(pi))
   - Evenness: J' = H' / ln(S)
   - Hill Numbers: D1 = exp(H'), D2 = 1/Σ(pi²)

4. **Bootstrap Resampling** / 自举重采样
   - Cluster bootstrap (B=1000 iterations)
   - 95% confidence intervals via percentile method
   - Wilson confidence intervals for proportions

5. **Generalized Linear Models** / 广义线性模型
   - Poisson GLM for count data
   - Negative Binomial for overdispersed data
   - Offset term: log(effort) for exposure adjustment
   - Covariates: year, month, weather variables

6. **Trend Analysis** / 趋势分析
   - Ordinary Least Squares (OLS) regression
   - P-value testing for significance (α = 0.05)
   - Generalized Additive Models (GAM) for non-linear patterns

## 💡 Discussion and Interpretation / 讨论与解释

### Ecological Significance / 生态学意义

1. **Stable Biodiversity** / 生物多样性稳定
   - No evidence of biodiversity loss over 12-year period
   - Consistent species composition suggests habitat stability
   - Supports conservation effectiveness in study area

2. **Monitoring Quality** / 监测质量
   - Increased spatial coverage enhances representativeness
   - Consistent methodology enables reliable trend detection
   - Expanded effort allows better population estimates

3. **Seasonal Ecology** / 季节生态学
   - Strong seasonal patterns indicate migratory behavior
   - Peak abundance in spring (March-May) aligns with breeding season
   - Monthly variation more important than weather for most species

4. **Weather Sensitivity** / 天气敏感性
   - Birds respond negatively to extreme weather (strong wind, heavy rain)
   - Reduced detectability rather than true population changes
   - Important to account for weather when interpreting trends

### Limitations / 局限性

- **Observer Bias**: Different observers may have varying detection abilities
- **Temporal Coverage**: Some months underrepresented in early years
- **Habitat Changes**: No explicit habitat quality data available
- **Species Identification**: Potential misidentification for similar species
- **Spatial Autocorrelation**: Transects may not be fully independent

### Recommendations / 建议

1. **Continue Long-term Monitoring** / 继续长期监测
   - Maintain consistent methodology
   - Ensure adequate spatial and temporal coverage
   - Train observers to standardize detection protocols

2. **Expand Covariates** / 扩展协变量
   - Include habitat quality metrics
   - Record observer experience level
   - Measure additional weather variables (temperature, humidity)

3. **Advanced Methods** / 高级方法
   - Occupancy modeling to account for imperfect detection
   - Mixed-effects models for hierarchical data structure
   - Spatial models to handle autocorrelation

4. **Conservation Focus** / 保护重点
   - Monitor rare or declining species more intensively
   - Assess habitat-specific trends
   - Evaluate climate change impacts on phenology

## 📚 References / 参考文献

### Statistical Methods / 统计方法
- Chao, A., et al. (2014). Rarefaction and extrapolation with Hill numbers. *Methods in Ecology and Evolution*.
- Zuur, A. F., et al. (2009). *Mixed Effects Models and Extensions in Ecology with R*. Springer.
- Wood, S. N. (2017). *Generalized Additive Models: An Introduction with R*. CRC Press.

### Ecological Context / 生态学背景
- MacKenzie, D. I., et al. (2017). *Occupancy Estimation and Modeling*. Academic Press.
- Magurran, A. E. (2004). *Measuring Biological Diversity*. Blackwell Publishing.

### Software Documentation / 软件文档
- McKinney, W. (2010). Data structures for statistical computing in Python. *Proceedings of the 9th Python in Science Conference*.
- Seabold, S., & Perktold, J. (2010). Statsmodels: Econometric and statistical modeling with Python. *Proceedings of the 9th Python in Science Conference*.

## 🎯 Conclusion / 结论

This project successfully demonstrates the application of advanced statistical methods to ecological monitoring data. Key achievements include:

本项目成功展示了高级统计方法在生态监测数据中的应用。主要成果包括:

1. **Comprehensive Data Processing** / 全面的数据处理
   - Systematic handling of ~25,000 observation records
   - Robust cleaning protocols for missing values and outliers
   - Quality-controlled dataset ready for ecological inference

2. **Multi-faceted Biodiversity Assessment** / 多方面的生物多样性评估
   - Five diversity metrics calculated with confidence intervals
   - Temporal trends quantified with statistical significance testing
   - Stable biodiversity confirmed over 12-year monitoring period

3. **Rigorous Statistical Modeling** / 严格的统计建模
   - GLM framework accounting for observation effort
   - Bootstrap methods for uncertainty quantification
   - Appropriate model selection (Poisson vs. Negative Binomial)

4. **Ecologically Meaningful Results** / 具有生态学意义的结果
   - Identified seasonal patterns in bird populations
   - Quantified weather effects on detection probability
   - Demonstrated monitoring design improvements over time

**Overall Assessment** / 总体评价:  
The analysis reveals a **stable and diverse bird community** with no evidence of biodiversity loss. The **increasing observation effort** and **expanding spatial coverage** indicate improving monitoring quality, which enhances our ability to detect future ecological changes.

分析揭示了一个**稳定且多样的鸟类群落**，没有生物多样性丧失的证据。**不断增加的观测努力量**和**扩大的空间覆盖**表明监测质量不断提高，这增强了我们检测未来生态变化的能力。

---

## � Technical Notes / 技术说明

### Reproducibility / 可重复性
- All analyses are contained in `bird.ipynb`
- Random seeds set for bootstrap procedures (seed = year × 19 + 7)
- Software versions documented in `requirements.txt`

### Computational Requirements / 计算要求
- **RAM**: 4 GB minimum (8 GB recommended)
- **Processing Time**: ~5-10 minutes for complete analysis
- **Python Version**: 3.8 or higher

### Code Quality / 代码质量
- Well-commented bilingual code (English/French)
- Modular functions for reusability
- Clear visualization with publication-quality figures

---

**Author**: [Your Name]  
**Student ID**: [Your Student Number]  
**Email**: [your.email@universite-paris-saclay.fr]

**Supervisor**: [Supervisor Name]  
**Course Code**: [Course Code]

**Declaration** / 声明:  
This project represents my original work. All sources and references are properly cited. The analysis was conducted independently, with guidance from course materials and statistical literature.

本项目代表我的原创工作。所有来源和参考文献均已正确引用。分析是独立进行的，并参考了课程材料和统计文献的指导。

---

**Last Updated**: November 6, 2025  
**Version**: 1.0 - Final Submission
