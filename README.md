# Monday-Effect

The Monday effect is a theory which states that returns on the stock market on Mondays will follow the prevailing trend from the previous Friday. Therefore, if the market was up on Friday, it should continue through the weekend and, come Monday, resume its rise and vice versa. The Monday effect is also known as the "weekend effect."

## Theroy

Two-way ANOVA is to understand if there is an interaction between the two independent variables on the dependent variable. 

ANOVA tests for significance using the F-test for statistical significance. The F-test is a groupwise comparison test, which means it compares the variance in each group mean to the overall variance in the dependent variable.

P score : The P-value approach involves determining "likely" or "unlikely" by determining the probability — assuming the null hypothesis were true — of observing a more extreme test statistic in the direction of the alternative hypothesis than the one observed.

Z score: (also called a standard score) gives you an idea of how far from the mean a data point is. But more technically it’s a measure of how many standard deviations below or above the population mean a raw score

## Data
Apple stock data from Jan 2020 --- Dec 2020 
...
. Date
. Open	
. High	
. Low	
. Close	
. Adj 
. Close	
. Volume
...

## Data Modification

Weekly Price change is calculated by computing the rolling difference between Closing and Opening price for a week. 

Split the weekly change on its deviation from mean using standard deviation 
```
df['Weekly_change'] =  df['Close'] - df['Open'].rolling(window=5,min_periods=0).mean() 

df['Weekly_significance_change'] =  abs(df['Weekly_change'] - df['Weekly_change'].mean())/df['Weekly_change'].std()

```

'Average' standard deviation indicates that the values tend to be close to the mean (also called the expected value) of the set, while a 'High' standard deviation indicates that the values are spread out over a wider range.

```

Weekly_Change = ['Average',  'High'  ]

bins= [0,1,2]

df['Weekly_significance_change_Range'] = pd.cut(df['Weekly_significance_change'], bins, labels=Weekly_Change)

```
![image](Average_high.png)
![image](Average_high1.png)



## Anova


