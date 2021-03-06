# NYCrestaurantsAnalysis

Have you ever wondered about how safe eating at a given restarant was? How about a given neighborhood or kind of cuisine? We'll be exploring health inspection data from the NYC Department of Health and Mental Hygiene across the state's five boroughs to answer our question: does it really matter where you eat in the city? For the purpose of this investigation our null hypothesis will be that it does matter in which of the boroughs you eat your food at. I will explore health inspection grades, scores, and their boroughs for my analysis.

# Data Source
The source of my data is New York's Open data platform. Data can be accessed via a Socrata SQL query.

# Analysis

## Count of Restaurants across all boroughs
Manhattan has the most restaurants, with Brooklyn and Queens following closely behind as expected.

## Cuisines across all boroughs
The most common cuisine of all restaurant types in the boroughs is American, followed by Chinese. Queens majorly favors Chinese above all others.

<img src = https://github.com/CBanalyst10/NYCrestaurantsAnalysis/blob/main/img/ctypesallboros.png>
<img src = https://github.com/CBanalyst10/NYCrestaurantsAnalysis/blob/main/img/ctypesbk.png>
<img src = https://github.com/CBanalyst10/NYCrestaurantsAnalysis/blob/main/img/ctypesqn.png>
<img src = https://github.com/CBanalyst10/NYCrestaurantsAnalysis/blob/main/img/ctypesmh.png>
<img src = https://github.com/CBanalyst10/NYCrestaurantsAnalysis/blob/main/img/ctypesbx.png>
<img src = https://github.com/CBanalyst10/NYCrestaurantsAnalysis/blob/main/img/ctypessi.png>


## Most frequently seen words in violation reports
<img src = https://github.com/CBanalyst10/NYCrestaurantsAnalysis/blob/main/img/wcabv.png>

## Most common score of violations across all restaurants, versus Grade A

Owners would want their scores to be lower as scores are a sum of violation count, but not their severity. Thus it is possible to have a low score and still have a serious enough violation to get a closure. Likewise it is possible to have a fair amount of violations and get a Grade A so long as they're minor.

<img src = https://github.com/CBanalyst10/NYCrestaurantsAnalysis/blob/main/img/hsallg.png>

<img src = https://github.com/CBanalyst10/NYCrestaurantsAnalysis/blob/main/img/hsa.png>

## Hypothesis testing against p-values
I proposed that eating anywhere in New York should not differ significantly. Although this seemed mostly true there were exceptions.

Using the module Scipy to produce a variety of test results across a variety of cohorts, I was able to perform measures across multiple group pairs.

### Mann Whitney U tests
#### Grade Aggregates
Grades given after inspections are A, B, C, P, N, G, and Z. A, B, and C are direct health ratings while P, N, G, and Z generally mean a future reassessment visit is pending. Restaurants who fail an inspection and don't compete well in a court of law to revise their score can have an inspection scheduled in the future to re-open their business. For simplicity and lack of time I have aggregated the letter grades into distict numerical scores. A is worth 3 points, B is worth 2 points, C is worth 1 point, and all others are rated for 0 points in this brief analysis.

Although most p-values were low and thus the comparison between these boroughs resulted in us keeping the null hypothesis that these grade scores are not significantly different, the comparison of Bronx to Staten Island revealed a significant difference of grade aggregate score.

Brooklyn v Queens

MannwhitneyuResult(statistic=4483083938.0, pvalue=2.340965345856826e-06)


Brooklyn v Manhattan

MannwhitneyuResult(statistic=7798981557.0, pvalue=0.002894214267661095)


Brooklyn v Bronx

MannwhitneyuResult(statistic=1801184452.5, pvalue=0.0005274865246170486)


Brooklyn v Staten Island

MannwhitneyuResult(statistic=653929991.0, pvalue=2.186457974405724e-07)


Queens v Manhattan

MannwhitneyuResult(statistic=6966581755.0, pvalue=0.009563484151986884)


Queens v Bronx

MannwhitneyuResult(statistic=1623721612.5, pvalue=0.4237846029112684)


Queens v Staten Island

MannwhitneyuResult(statistic=590206408.5, pvalue=0.002910983365737641)


Bronx v Staten Island

MannwhitneyuResult(statistic=2799153181.0, pvalue=0.06594103012805569)


#### Scores
Scores are a numerical count of health violations, though not necessarily their severity. Comparing violation scores within a Mann-Whitney U-test shows statistically significant differences between the Brooklyn-Manhattan, Queens-Bronx, Queens-Staten-Island, and Bronx-Staten Island

Brooklyn v Queens

MannwhitneyuResult(statistic=4027761290.0, pvalue=6.279700273260612e-10)


Brooklyn v Manhattan

MannwhitneyuResult(statistic=7063251831.5, pvalue=0.07291172955343204)


Brooklyn v Bronx

MannwhitneyuResult(statistic=1633356266.0, pvalue=0.00022866041586911854)


Brooklyn v Staten Island

MannwhitneyuResult(statistic=593789637.0, pvalue=0.00021761478432325465)


Queens v Manhattan

MannwhitneyuResult(statistic=6247632696.5, pvalue=5.41108915663237e-16)


Queens v Bronx

MannwhitneyuResult(statistic=1482260416.5, pvalue=0.1603084485152904)


Queens v Staten Island

MannwhitneyuResult(statistic=543026556.0, pvalue=0.32130699230651416)


Bronx v Staten Island

MannwhitneyuResult(statistic=2532442622.0, pvalue=8.385718703075684e-07)



