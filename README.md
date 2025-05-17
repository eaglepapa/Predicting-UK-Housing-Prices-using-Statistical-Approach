# Predicting UK Housing Prices using Statistical Approach

## Table of Contents
- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Cleaning/Preparation](#data-cleaningpreparation)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Results/Findings](#resultsfindings)
- [Recommendations](#recommendations)
- [Limitations](#limitations)
- [References](#references)
- [Contact](#contact)
  
### Project Overview
---
The main aim of the project was to design a model to predict house prices for Real Estate Agency in UK. The following equation;

**Ŷ = -2,639,000 + 21.56X₁ + 165,900X₂ + 121,800X₃ + 15.24X₅**  

was generated for the model. It was discovered that, for every square foot increase in house size, sale price increases on average by about £15.24, holding other variables constant. Also for every increase in average area income, sale price increases on average by about £21.56, holding other variables constant. Average area income, house age, number of rooms, and size of the house, had statistical significant relationship with the house price.


![model  summary](https://github.com/user-attachments/assets/dda882c3-1727-42be-a9f3-f0adbc233d0c)


### Data Sources
UK Housing Data: The dataset was downloaded from Kaggle

### Tools
- RStudio – Data cleaning and analysis  
  [Download here](https://posit.co/products/open-source/rstudio/)

- Power BI – Report creation and data visualization  
  [Download here](https://www.microsoft.com/en-us/download/details.aspx?id=58494)

- Excel – Data cleaning, transformation, and visualization  
  [Download here](https://www.microsoft.com/en-us/microsoft-365/excel)

#### Data Cleaning/Preparation
In the initial data preparation please, I performed the following tasks:
1.	Data loading and inspection.
2.	Handling missing values.
3.	Data cleaning and formatting.
4. 	Building the model
5.	Predicting values

   
### Exploratory Data Analysis
EDA involved exploring the UK housing data to answer key business questions, such as: 
-	Does the size of a house affect the price of the house?
-	Does the average area income of the city affect the house price?
-	Does average area income, house age, number of rooms, number of bedrooms, and size of the house, affect the house price?
-	What will be the predicted house price after inputting the values; Avg..Area.Income = £540,000, House.Age = 2 years, Number.of.Rooms = 5 , and SquareFeet = 800000 sq ft, into the adopted linear regression model?
  
  
![corr](https://github.com/user-attachments/assets/4798a14a-53e3-4884-9270-1badcaa094d6)

  
### Data Analysis 
```r
# Making predictions on the testing set (testing the model)
lm_predictions <- predict(lm_model, newdata=test_data)


# Save the trained model object to a file
saveRDS(lm_model, "lm_model.rds")

# Load the multiple linear Regression model
lm_model <- readRDS("lm_model.rds")

# Prepare the input data
input_data <- data.frame(
  Avg..Area.Income = 540000,
  House.Age = 2,
  Number.of.Rooms = 5,
  SquareFeet = 800000
)

# Make predictions
predictions <- predict(lm_model, input_data)

# Print the predictions
print(predictions) 
```

### Results/Findings
The analysis results are summarized as follows:
|NO.|BUSINESS QUESTION|ANSWER|
|------|---------------------------|------------|
|1|Does the size of a house affect the price of the house?|15.24SquareFeet means for every square foot increase in house size, sale price increases on average by about GBP 15.24, holding other variables constant.|
|2|Does the average area income of the city affect the house price?|21.56Avg..Area.Income means for every increase in average area income, sale price increases on average by about £21.56, holding other variables constant.|
|3|Does average area income, house age, number of rooms, number of bedrooms, and size of the house, affect the house price?|Y ̂= -2639000 + 21.56X_1+ 165900X_2+ 121800X_3+ 15.24X_5 Means average area income, house age, number of rooms, and size of the house, has statistically significant relationship with the house price.|
|4| What will be the predicted house price after inputting the values; Avg..Area.Income = £540,000, House.Age = 2 years, Number.of.Rooms = 5 , and SquareFeet = 800000 sq ft, into the adopted linear regression model?| After inputting the values; Avg..Area.Income = 540000, House.Age = 2, Number.of.Rooms = 5, and SquareFeet = 800000, into the multiple linear regression model, the predicted house price was **$22,135,164**.|

### Recommendations
After excluding variables that were not statistically significant, I recommend adopting the following linear equation for the model:

**Ŷ = -2,639,000 + 21.56X₁ + 165,900X₂ + 121,800X₃ + 15.24X₅**

Where; X₁ = Avg..Area.Income, X₂ = House.Age, X₃ = Number.of.Rooms, and X₅ = SquareFeet


### Limitations
The dataset was sourced from Kaggle, and as such, the authenticity and reliability of the data cannot be fully guaranteed.

### References

1.	BEERS, B. (2024) What Is Regression? Definition, Calculation, and Example. [Online] Available from: https://www.investopedia.com/terms/r/regression.asp. [Accessed 12 April 2024].
2.	Bhandari, P. (2023) Inferential Statistics | An Easy Introduction & Examples. [Online] Available from: https://www.scribbr.co.uk/stats/inferential-statistics-meaning/. [Accessed 12 April 2024].
3.	Biswal, A. (2023) What is Exploratory Data Analysis? Steps and Market Analysis | Simplilearn. [Online] Available from: https://www.simplilearn.com/tutorials/data-analytics-tutorial/exploratory-data-analysis. [Accessed 12 April 2024].
4.	Blumenfeld, Z. (2023) Predictive Modeling Techniques: Types, Benefits & Algorithms. [Online] Available from: https://neo4j.com/blog/predictive-modeling-techniques/. [Accessed 13 April 2024].
5.	Bose, P. (2023) Exploratory Data Analysis in Python: A Comprehensive Guide. Blogs & Updates on Data Science, Business Analytics, AI Machine Learning [Online]. Available from: https://www.analytixlabs.co.in/blog/exploratory-data-analysis-in-python/. [Accessed 13 April 2024].
6.	Cydni. (2015) Informed Consent - Definition, Examples, Cases, Processes. Legal Dictionary. [Online] Available from: https://legaldictionary.net/informed-consent/. [Accessed 13 April 2024].
7.	D, V. (2021) Multivariate analysis: an overview. Students 4 Best Evidence. [Online] Available from: https://s4be.cochrane.org/blog/2021/09/09/. [Accessed 13 April 2024].
8.	Denis, D. J. (2020) Univariate, Bivariate, and Multivariate Statistics Using R. [Online] Available from: https://ebookcentral.proquest.com/lib/bolton/reader.action?docID=6146792. [Accessed 5 April 2024].


## Contact
Feel free to reach out!  
📧 Email: [oduroprince08@gmail.com](mailto:oduroprince08@gmail.com) &nbsp;|&nbsp; 🔗 LinkedIn: [linkedin.com/in/oduroprince24](https://linkedin.com/in/oduroprince24)


🚀
📊
📈
🧠

Thanks for visiting! 😄
