# NYCrestaurantsAnalysis

Have you ever wondered about how safe eating at a given restarant was? How about a given neighborhood or kind of cuisine? We'll be exploring health inspection data from the NYC Department of Health and Mental Hygiene across the state's five boroughs to answer our question: does it really matter where you eat in the city? For the purpose of this investigation our null hypothesis will be that it does matter in which of the boroughs you eat your food at. I will explore health inspection grades, scores, and their boroughs for my analysis.

# Data Source
The source of my data is New York's Open data platform. Data can be accessed via a Socrata SQL query.

# Analysis

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

