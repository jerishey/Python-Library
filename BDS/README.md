# Data Science
Data science is the study of data used to extract meaningful insights for business decisions. It combines mathematics, computing and domain knowledge to solve real-world problems and uncover hidden patterns.
<br>
It processes raw data to address business challenges and predict future trends. For example, from large company datasets, data science can help answer questions like:

- What do customer want?
- How can we improve our services?
- What will the upcoming trend in sales?
- How much stock they need for upcoming festival.


### `Steps in Data Science`
```bash
1. Data Collection: Gathering raw data from various sources, such as databases, sensors or user interactions.

2. Data Cleaning: Ensuring the data is accurate, complete and ready for analysis.

3. Data Analysis: Applying statistical and computational methods to identify patterns, trends or relationships.

4. Data Visualization: Creating charts, graphs and dashboards to present findings clearly.

5. Decision-Making: Using insights to inform strategies, create solutions or predict outcomes.
```

### `Advantages`
```bash
1. Decision-Making & Forecasting: Businesses analyze data to identify trends, reduce risks and predict future demand.

2. Efficiency & Optimization: Helps in saving time and resources by improving processes like supply chain and operations.

3. Personalization: Enables customized recommendations in platforms like e-commerce and marketing.

4. Fraud Detection & Security: Identifies unusual patterns in financial transactions to prevent fraud.

5. Healthcare Improvements: Supports early diagnosis using medical data and predictive models.

6. Marketing & Sentiment Analysis: Helps businesses understand customer behavior and public opinion through data insights.
```

## `Data Science with Python`
Data Science with Python focuses on extracting insights from data using libraries and analytical techniques. Python provides a rich ecosystem for data manipulation, visualization, statistical analysis and machine learning, making it one of the most popular tools for data science.

`Features`
```bash
1. Simple and Easy Syntax : Python has a simple and readable syntax that makes programming easy for beginners and developers.

2. Large Library Support : Python provides many powerful libraries like NumPy, Pandas, and Scikit-learn for data analysis and machine learning.

3. Data Visualization : Python supports graphs, charts, and dashboards to represent data visually and improve understanding.

4. Machine Learning Support : Python is widely used for machine learning and artificial intelligence applications because of its advanced frameworks and tools.

5. Open Source : Python is free to use and has a large open-source community that continuously improves its tools and libraries.

6. Cross-Platform Compatibility : Python programs can run on different operating systems like Windows, Linux, and macOS without major modifications.
```

`Advantages`
```bash
1. Easy to Learn : Python is beginner-friendly due to its clean and simple syntax.

2. Faster Development : Pre-built libraries and tools reduce coding time and speed up development.

3. Powerful Data Handling : Python efficiently processes, cleans, and analyzes large datasets.

4. Strong Machine Learning Ecosystem : Python provides excellent support for AI and machine learning development.

5. Better Visualization : Python helps create attractive visual reports and graphs for decision-making.

6. High Industry Demand : Python data science skills are highly demanded in industries such as healthcare, finance, and e-commerce.
```

`Disadvantages`
```bash
1. Slower Execution Speed : Python executes slower compared to compiled languages like C++ and Java.

2. High Memory Consumption : Python programs may use more memory during execution.

3. Runtime Errors : Errors may appear during program execution because Python is dynamically typed.

4. Multithreading Limitations : Python has limitations in handling heavy multithreading tasks efficiently.

5. Dependency Issues : Managing different library versions can sometimes create compatibility problems.

6. Less Suitable for Mobile Development : Python is not commonly preferred for mobile application development.
```

## `Descriptive Statistic`
Statistics is the foundation of data science. Descriptive statistics are simple tools that help us understand and summarize data. They show the basic features of a dataset, like the average, highest and lowest values and how spread out the numbers are.

### `Types of Descriptive Statistics`
There are three categories for standard classification of descriptive statistics methods, each serving different purposes in summarizing and describing data. They help us understand:

1. Where the data centers (Measures of Central Tendency)
2. How spread out the data is (Measure of Variability)
3. How the data is distributed (Measures of Frequency Distribution)

#### `1. Measures of Central Tendency`
Statistical values that describe the central position within a dataset. There are three main measures of central tendency:

`1. Mean :` is the sum of observations divided by the total number of observations. It is also defined as average which is the sum divided by count.

$\text{Mean} = \frac{\sum x}{n}$

where :

- x = Observations
- n = number of terms
```bash
import numpy as np

# Sample Data
arr = [5, 6, 11]

# Mean
mean = np.mean(arr)

print("Mean = ", mean)

Output:
Mean =  7.333333333333333
```

`2. Mode :` The most frequently occurring value in the dataset. It’s useful for categorical data and in cases where knowing the most common choice is crucial.
```bash
import scipy.stats as stats

# sample Data
arr = [1, 2, 2, 3]

# Mode
mode = stats.mode(arr)
print("Mode = ", mode)

Output:
Mode =  ModeResult(mode=array([2]), count=array([2]))
```

`3. Median :` The median is the middle value in a sorted dataset. If the number of values is odd, it's the center value, if even, it's the average of the two middle values. It's often better than the mean for skewed data.
```bash
import numpy as np

# sample Data
arr = [1, 2, 3, 4]

# Median
median = np.median(arr)

print("Median = ", median)

Output:
Median =  2.5
```

#### `2. Measure of Variability`
Measure of variability is a statistical concept used to show how spread out or dispersed the data values are from each other or from the average value.

`1. Range :` describes the difference between the largest and smallest data point in our data set. The bigger the range, the more the spread of data and vice versa. While easy to compute range is sensitive to outliers. This measure can provide a quick sense of the data spread but should be complemented with other statistics.
```bash
Range = Largest data value - smallest data value 

Example:
import numpy as np

# Sample Data
arr = [1, 2, 3, 4, 5]

# Finding Max
Maximum = max(arr)
# Finding Min
Minimum = min(arr)

# Difference Of Max and Min
Range = Maximum-Minimum
print("Maximum = {}, Minimum = {} and Range = {}".format(
    Maximum, Minimum, Range))

Output:
Maximum = 5, Minimum = 1 and Range = 4
```

`2. Variance :` is defined as an average squared deviation from the mean. It is calculated by finding the difference between every data point and the average which is also known as the mean, squaring them, adding all of them and then dividing by the number of data points present in our data set.

$\sigma^2 = \frac{\sum (x - \mu)^2}{N}$

where :

- x -> Observation under consideration
- N -> number of terms 
- μ -> Mean 

```bash
import numpy as np

data = [10, 20, 30, 40, 50]

variance = np.var(data)

print("Variance:", variance)
```

`3. Standard deviation :` Standard deviation measures how much the data values differ from the mean. It is widely used in statistics and machine learning to understand data spread and model performance.

- It is defined as the square root of variance.
- A low standard deviation means values are close to the mean.
- A high standard deviation indicates greater variation in the dataset

$\sigma = \sqrt{\frac{\sum (x - \mu)^2}{N}}$

where :
- x = Observation under consideration
- N = number of terms 
- μ = Mean
```bash
import numpy as np

data = [10, 20, 30, 40, 50]

std_deviation = np.std(data)

print("Standard Deviation:", std_deviation)

- Variability measures are important in residual analysis to check how well a model fits the data.
```

#### `3. Measures of Frequency Distribution`
Measures of frequency distribution are statistical methods used to show how often data values occur in a dataset. They help organize and understand the distribution of data.

<b>Frequency Distribution Table Includes measure like :</b>

- Data intervals or categories
- Frequency counts
- Relative frequencies (percentages)
- Cumulative frequencies when needed