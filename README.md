# Central_Limit_Theorem

Take multiple samples from a population and calculate a certain statistic: mean 𝑥 ̅ , median. 𝑥 ̅ values calculated individually from all the samples are normally distributed.

### 1. Introduction
In this assignment, we are going to conduct an experiment on central limit theory using the dataset from San Francisco library usage. The library system is composed of records including patron type, total checkouts and renewals, age range, etc. The dataset includes 423,448 records, from 2003 year to 2016 year. For more information on specific columns refer to the official data dictionary and the information in the Column Metadata on the /Data tab.

We will take column "total checkouts", which showed how many times the patron has been used on books in the library system since first registering. By taking numbers of the column, we'll perform random sampling and compute the mean, meadian and standard deviation to experiment central limit theorem.

#### Dataset: https://www.kaggle.com/datasf/sf-library-usage-data/kernels
Distribution: Exponential distribution (TBD)
Parameters: mean, median, standard deviation
We will do experiment with different numbers of samples count (10,30,100) and different sample sizes (30,100,1000).

#### Sample Count: 10, 30, 100
#### Sample Size: 30,100, 1000


### 2. Experiment on Central Limit Theory
##### 2.1 Data Loading
Take a look at library data first. Import pandas library to help us understand type of library data. we will only choose number(integer, float) column to do this exercise. In this experiment, we pick the column - Total Checkouts to analyse the frequency of people to checking out books from library. As info() showed, most of the column are objects, which we are not interested in this time. So we can remove those cloumn in the next step.

##### 2.2 Data Tidying
we are going to clean the data to make it easy to oberseve and calculate.
Check if there is any null row in Total Checkouts column. If yes, we need to add a defalt value, such as 0 in it. If no, we can just keep going.

It seems like there are too many columns we don't want use and reference, we can remove them by using drop() function. After the column- Age range, those information are personal data, recording about preference of individual (home library, active time, contact way...etc). Those are not related to the value of borrowing books.

Also, we change column name to avoid any blank space inside the column. It will be a problem when we create a function with blank space in it. By using bottom line between each words, we can rename each column

Import seaborn library to do a simple graph. X axis is the value of each person who checking out books. Y axis is quantity of people.
As the graph showed, outliers occured when approaching to maxinum. On the other hand, there are many spots in the minium area, 
so we can assume there are no outliers when approaching to minium. 

#### 2.3 Functions
Draw samplings from the data. Create a barplot using searborn chart. generate the statistics of sampling distribution.
Calaulate the statistics Mean, Median, Standard Deviation of sampling distribution.

#### 2.4 Mean
Using two statement, Same sample count 100, sample size change 30, 100, 1000

#### 2.5 Median
Using two statement, Same sample count 100, sample size change 30, 100, 1000

#### 2.6 Standard Deviation
Using two statement, Same sample count 100, sample size change 30, 100, 1000

### 3. Summary
#### Summary1: 
Sample size is more related to sample count.
Accroding to the table above, fixed the size to larger, no matter how many simple count, the mean is almost the same and st dev are approaching to zero, whcih means more accurate.

#### Summary 2.
From our research, we found that no matter we make sample count or sample size fixed, the estimated mean, median and standard deviation of sample distribution are close to the actual mean, median and standard deviation of population distribution.. Hence the central limit theorem can efficiently estimate the statistics of a larger data.

### 4. Additional Topic Discussions
###### 1. What is a good compromise between the number of samples and the sample size? In the real world, it is expensive to do sampling. But you still want the most accurate estimates.
To make more accuacy in our estimation, we require a larger sample size and sample count. A sample size of 30 is usually recommanded and sometimes 40 is a least. Yet for some other distributions that are distinctly not normal(such as multiple peaks, badly skewed, etc), we probably need even larger sample size. From our result, we can infer that the sample count and sample size do matter in estimating the statistics of population distribution. With Sample count on 100 and sample size on 100, the estimated statistics will be nearly the same with the population statistics.

###### 2. Which population probability distributions are more challenging to estimate their parameters with random sampling? Given what the Central Limit Theorem says about the distributions of the sample statistics, would a normally distributed population be easiest? Would other distributions be harder to make good parameter estimates? If so, why?
According to above mentioned, if the original distribution are closer to normal distribution, the estimation will be easier, as the sample size can be smaller and will reduce the cost. On the other hand, it is harder to make good estimates with distributions that are skewed, multiple peaked or having many outliers since it will cause a problem when drawing samples from the orginal dataset.

###### 3. From the charts in the February 27th set of lecture notes, it appears that estimating the standard deviation parameter is more challenging than estimating the population mean and median. Is that generally true for all population distributions? If so, why?
Gernerally, it is more challenging to choose standard deviation parameter because of outlier. But in out dataset, we remove outliers before we processed the data. Hence our result turns out to be accurate in all parameters(mean, median, std)

###### 4. For a fixed sample count, what sample sizes are required for the sample distributions to approach normal for each parameter estimation? Is it possible to rank the parameters by the required sample sizes when estimating using random sampling?
From our dataset, we fixed count = 100. Then, we found that when sample size is greater than 100, there are 68% of data between mean +- 1 std. We believe the sample size should greater than 100. From our data result, we can't rank the parameter between mean, mediem, standard deviation.
