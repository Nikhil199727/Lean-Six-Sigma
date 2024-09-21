# Lean-Six-Sigma
In a bustling factory, the management team faced an intriguing question: does training actually improve workers' productivity, or is it merely an unnecessary cost? To uncover the truth, they gathered data on how long it took workers to complete their tasks and noted whether each worker had undergone training. With this data in hand, the aim was to determine if training truly made a significant impact on efficiency.

This project revolves around analyzing this dataset to explore whether training leads to improved performance. The main goal was to perform various statistical tests to determine whether the average time taken to complete a task differs significantly between trained and untrained workers. By carefully checking the assumptions and running tests suited for different scenarios, the project strives to deliver evidence-backed conclusions on the impact of training.

### 2. Dataset Description

The dataset was sourced from internal factory records, containing the completion times of tasks performed by workers and whether each worker had received training. This dataset is small, consisting of just 56 entries.

#### Dataset Structure:
- **Source:** Hypothetical factory data (Excel format)
- **Type and Size:** 
  - Rows: 56 
  - Columns: 2 (`Time`, `Training`)

#### Variables:
1. **Time:**  
   - Meaning: The time it took for a worker to complete a task (in seconds).  
   - Type: Numeric (integer, measured on a ratio scale).  
2. **Training:**  
   - Meaning: Indicates whether the worker received training (Yes/No).  
   - Type: Categorical (nominal scale).

#### Data Quality:
- No missing values were found in the dataset.
- No duplicated entries.
- The `Time` variable is numeric and free from obvious measurement errors.
- The dataset is small, making it manageable but slightly limiting in terms of statistical power.

### 3. Objectives of the Project

The primary goal of this project was to assess whether training has a measurable impact on workers' productivity. To accomplish this, several key questions were posed:
- Does training reduce the time it takes for workers to complete tasks?
- Are the time differences between trained and untrained workers statistically significant?
- How do the data's distributional properties (normality, variance equality) affect the choice of statistical tests?

### 4. Tools

The project was implemented using Python with the following libraries:
- **Pandas:** For data manipulation and analysis.
- **NumPy:** For numerical operations.
- **Matplotlib & Seaborn:** For data visualization.
- **Scipy, Statsmodels, Bioinfokit:** For statistical analysis, including normality checks, residual plots, and ANOVA.
- **Pingouin:** For conducting Welch's ANOVA and Kruskal-Wallis tests.
- **Programming Language:** Python

### 5. Insights

#### Distribution of Time (Histogram)
A histogram of the `Time` variable showed a right-skewed distribution. This indicated that most workers completed tasks relatively quickly, but a few took significantly longer.

![download](https://github.com/user-attachments/assets/92150606-fc44-4cb9-b651-cb48b57175a8)



#### Training Distribution (Bar Chart)
The bar chart comparing the number of trained and untrained workers revealed a balanced distribution, ensuring fair representation in the subsequent analysis.

![download](https://github.com/user-attachments/assets/8197b74e-9088-421b-9479-760b718f29a4)



#### Variance Across Groups
When examining the variance of `Time` between the groups, the variance for trained workers was lower than that for untrained workers. This suggested that trained workers tended to complete tasks more consistently, while untrained workers had more variation in their completion times.



#### Assumptions Check (QQ Plot)
The QQ plot revealed that the data did not perfectly follow a normal distribution, with some deviations in the tails. This suggested that normality assumptions for ANOVA might not hold.

![download](https://github.com/user-attachments/assets/577c1bad-533a-42e9-b924-a98efc3bf27d)
![download](https://github.com/user-attachments/assets/5b4b80fc-aef1-4092-af5e-6fcc254bcaaa)
![download](https://github.com/user-attachments/assets/7cc78fa0-4e6c-47b6-a7f6-1d639f6e8d78)





#### Welch's ANOVA Results
Given the unequal variances between the groups, Welch's ANOVA was applied. The p-value from Welch’s ANOVA was 0.000151, which is less than 0.05, leading to the rejection of the null hypothesis. This result confirmed that training does have a statistically significant impact on task completion time.

#### Kruskal-Wallis Test Results
Since the normality assumption wasn't fully met, a non-parametric Kruskal-Wallis test was also performed. This test too showed a p-value below 0.05, providing additional evidence that trained workers performed significantly better than untrained workers.



### 6. Recommendations and Future Analysis

Based on the analysis, it is clear that training has a positive impact on worker productivity. For future analysis, it is recommended to:
- Collect a larger dataset to further validate these findings and improve statistical power.
- Analyze the impact of training duration or quality on performance, as the current dataset only distinguishes between trained and untrained.
- Explore other factors that may influence productivity, such as worker experience, task complexity, or equipment used.

Further refinement of the dataset and a broader investigation could lead to more actionable insights, helping optimize both the training programs and overall operational efficiency.
