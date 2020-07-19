# Predicting_Employee_Churn
 
## 1. Context

The data comes from myhappyforce.com where employees report daily happiness levels at work. This platform (app) is used by companies to track happiness of the workforce, which helps us better understand the phenomenon of employee turnover. The cost of employee turnover has been pointed out extensively in the literature. A high turnover rate not only increases human resource costs, which can reach up to 150% of the annual salary per replaced employee, but it also has social costs, as it is correlated with lower wages, lower productivity per employee, and not surprisingly, a less loyal workforce.

The anonymized data is opensourced on Kaggle.com. The data source is real and reliable.

## 2. Goal

The goal is to clarify the characteristics of employees that will churn (or that are at risk of churning), to help companies understand the causes so they can reduce the turnover rate. We assume that the top feautures of employees that churn are:

- low relative happiness
- high happiness level fluctuation
- low ratio of likes

## 3. Content

The data consists of three tables: votes, interactions and churn.

A vote was obtained when an employee opened the app and answered the question: How happy are you at work today? To vote the employee indicates their feeling by touching one of four icons that appeared on the screen.
After the employee indicates their happiness level, a second screen appears where they can see their peers’ comments and like or dislike them, this data is stored in the interactions table.
The churn table contains when an employee churned (quit or was fired).

## 4. Conclusions:

### Regarding to distributions of features:

- The overall distributions of employees' happiness level are different. The number of votes for level 3 is larger than the others. Employees are tend to have relatively high hapiness level, since the numbers of votes for level 3 and level 4 are higher then the votes for level 1 and level 2.
- There are some outliers in the dataset. Some employess are not a big fan of voting for happiness level everyday, but some are actively engaged with this.
- Overall, there are 15.7% of employees churn, and 84.3% of employees stay at the company during the time period of our analysis time.

### Regarding to relationship between variables:

- There are negative relationships among"votes_1", "votes_2", "votes_3", and "votes_4", because the overall happiness level of an individual is relatively stable. If a person vote for level 1 many times, it is less likely for him or her to vote for level 4 after that. So if votes for level 1 increase, the votes for level 2, 3, and 4 are probobaly decrease.
- There is a positive relationship between votes_num and likes_num. These two variables are both good indicators of engagement of employees. If one person votes a lot, he or she may be more active to comment on others' updates and share thoughts with the community.
- There is a positive relationship among "votes_3", "votes_4", "votes_num", and "likes_num". That means the person who votes for 3 level and 4 level are more likely to vote and interact with others. We find this is interesting because it indicates that the happier people are more likely to express themselves and engage with others.
- There are no significant relationship between "stillExists" and other variables.

### Regarding to prediction models:

- Linear regression model are not suitable for predicting churn behavior since the prediction score is low.
- Logistic regression model, SGD model, and Ridge classification model perform better than the linear regression model. Especially, the logistic regression model perform well with a 85% precision rate for predicting employee retention, but it is not suitable for predicting churn.
- The impact of "votes_mean" and "votes_std" on churn are higher than the impact of "votes_num" and "likes_num". However, we could not determine that they are siginificant predictors for employee churn.
- To sum up, surprisingly, a prior expected explanatory features such as mean happiness level and the ratio of likes (positivity), were not significant.
