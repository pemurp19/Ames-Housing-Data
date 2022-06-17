# Project 2 - Ames Housing Data and Kaggle Challenge

### Problem:
The Ames, IA housing market has a narrow range of home prices, which makes it difficult to run a profitable home flipping business in the city.

### Problem Statement:
As a data scientist for Iowa Development Company, I need to determine if a model can be developed from the Ames Tax Assessor’s data to identify homes that are currently undervalued and to prioritize renovations that will lead to the greatest profits at resale? 


---

### Datasets

* [`train.csv`](./data/train.csv): Ames, IA Housing Data 2006-2010
* [`test_ca.csv`](./data/test_ca.csv): Ames, IA Housing Data 2006-2010 

### Data Dictionary ([*source*](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt).)

---

**Analysis**

![alt text](https://git.generalassemb.ly/pemurp96/project_2/blob/main/images/home_price_distribution.png)

Narrow distribution of home prices in Ames makes it a tough market to flip homes in. Run linear regressoin models, starting with the most complex versions and simplifying. Iterating through interaction features and regularization methods, such as Ridge and Lasso regression. 

After data cleaning, set the benchmark model as the median home price ($157,000) which had a root mean squared error of $53,215. The most predictive model was not necessarily the most interpretable  so I had to balance those two factors and ended up selecting two different models. 

![alt text](https://git.generalassemb.ly/pemurp96/project_2/blob/main/images/inferential_model.png)

The more predictive model included 213 features and 89% of variability in home prices was explained by the features in this model. The predictive model used feature engineering which takes away from its interpretability. Hence, I selected a different production model to inform the renovation process and infer which home features would add the most value to a home's price. However, the predictive model will be used to identify undervalued homes based on listing price. 

---
![alt text](https://git.generalassemb.ly/pemurp96/project_2/blob/main/images/square_footage_corr.png)

### Findings and Recommendations


**Recommendations:**
Look to buy homes in Somerset and Northridge Heights as these neighborhoods have the highest positive correlation to Sale price. Hence, when we’re looking to resell we’ll be able to maximize that location value. 

Avoid homes that are located in Edwards, Iowa DOT and Rail Road, and Old Town(neighborhoods with the lowest negative correlation to Sale price). You can’t change the location of the home through renovation so want to make sure we’re well-positioned. 

Recommend expanding square footage as much as possible (specifically, we could focus on finishing a basement to maximize our renovation budget. For every Sq ft increase in living area (finished area) the home value increases by nearly $33 (seems small but even looking at the average unfinished basement size of   ~$590 sq feet, so if you multiply that by $33 per square foot, you’re seeing a $20,000 increase in home value.

Additionally, improving the Kitchen should provide some nice returns. Holding all other variables constant, the effect of having an excellent kitchen contributes to a more than $27,000 increase in a home’s value relative to a poor quality kitchen. That’s almost 20% of the median home value of $157,000. 

**Conclusion:** 
This data set provides a solid starting point for the purposes of Iowa Development Co.’s investment projects specifically in Ames. However to further enhance it’s predictive power and expand it’s application to other Iowa cities, it would be valuable to know the conditions behind each sale - were any of these sales between family members or foreclosures, for instance, that would be outliers and throw off the model’s predictive ability. Importantly, Ames is a college town - this could also make the model less applicable to other suburban towns or small cities which don’t have as much college student housing. 
