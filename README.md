
## Patterns of Firearm-Related Crimes in the United States
#### Machine Learning Foundations with Python (90-803)
#### Spring 2023



Program Description

Gun violence has been a major issue in the United States. Statistics show that there were 64,590 incidents of gun violence in the US in 2021, resulting in 33,687 deaths and 31,903 injuries. This program is developed to provide insights that can be used by policymakers and stakeholders to prevent gun violence and make communities safer.

Getting Started

- Language: Python
- Modules:
  - Install the following modules (numpy, pandas, seaborn, statsmodels, sklearn, imblearn, matplotlib) by entering the following example command to the command line if needed:
    - pip install numpy

Executing program

Run the notebook file ML\_Project\_Final\_Group4.ipynb

Datasets

All the raw datasets used are saved in the folder named “Datasets\_Team4”. The link to the folder is here: <https://drive.google.com/drive/folders/14amew47wmJQOcJweSEQihImxNTBNIgMC?usp=sharing>

- Gun Law Dataset contains the amounts of firearms legislation across all US states from 1990 to 2016.
- CDC Dataset contains the number of firearm-related death across the population in all US states from 2001 - 2020.
- School Shooting Incidence Dataset contains information about school shootings in the US from 1999 to the present.
- School Shooting Weapon Dataset contains weapon information on school shooting incidents in the US from 1999 to the present. 
- Gun Dealer Violations Dataset contains inspection reports documenting violations of procedure across the US over a recent time period. 






Branching strategy

Truck-based was used as a branching strategy. The “main” branch contains the production-ready code and only contains stable and tested code. Each team member has their own “develop” branch named after their initials (i.e., ysdevelop, nr\_develop, AS\_develop). Those branches served as staging areas for each teammate for code that was in progress but not yet ready for release. And each teammate works on new features and continuously integrates code changes into the “main” branch. 

With this branching strategy, we have a “main” branch that always contains stable and production-ready code and “develop” branches for ongoing development. 

Project Outline

We are targeting three areas to explore the gun violence situation: policy solutions, understanding contributing factors, and prevention strategies. We aim to answer three questions from our dataset: 1) which state-level firearm-restrictive laws have the highest impact on preventing homicide, 2) can we predict the type of gun most likely to be used in a school shooting based on the severity of the attack, and 3) can we predict gun dealer types based on violations, inspection letter content, and license recommendation? We answered the first question with Regression and the second and third questions with Classification. 

The Jupyter Notebook contains data exploration (visualization), analysis (data processing) for the datasets, and feature engineering, model training/selection, model tuning/validation, and model performance metrics for each question in order.

Conclusions and Discussions - Addressing Questions

**Question 1: What state-level firearm-restrictive laws have the highest effect on preventing homicide?** 

![](Aspose.Words.f430d02a-5392-4534-9f72-7ed6d6245122.001.png)

The top 5 laws that contribute to the gun-related deaths are: 

- defactoregh - De facto registration of handguns is in place because of a recordkeeping requirement for all handgun sales
- registrationh - Gun owners must register their handguns with the state
- assaultregister - Grandfathered weapons must be registered
- magazine - Ban on sale large capacity magazines beyond just ammunition for pistols
- reportall - All private sellers and licensced dealers are required to report all fireamrs sales record to the states

The top 5 laws that decrease the gun-related deaths are:

- violenth - Handgun possession is prohibited for people who have committed a violent misdemeanor
- registration - gunowners must register their firearms with the state
- universalpermit - background checks conducted through permit requirement for all firearm sells
- reportallh - All private sellers and licensed dealers are required to report handguns sales record to the state
- preemptionnarrow - Any state law that preempts local regulation of firearms is narrow in its scope (i.e., in one area of regulation)

In general, the analysis suggests that certain types of state-level firearm-restrictive laws may have a greater impact on reducing gun-related deaths compared to others. For instance, laws related to de facto registration and large-capacity magazine restrictions may have unintended consequences and increase homicides. On the other hand, laws related to violent misdemeanors, firearm registration, and universal background checks are likely to have a positive impact on preventing gun violence. Policymakers and stakeholders can use this information to inform their decisions on which types of firearm laws to implement in order to make communities safer. The findings also highlight the importance of continued research and evaluation to better understand the impact of firearm laws on reducing gun violence.

**Question 2: Based on the severity of the attack, can we predict which type of gun is most likely to be used in a school shooting?**


Our goal is to predict which type of gun is most likely to be used in a school shooting based on the severity of the attack. To accomplish this, we trained multiple classification models on our dataset. The AdaBoost model provided the best precision across classes and recall for the minority class. In this case, we prioritized **precision** over recall since we are trying to capture the dangers of big guns, and having a higher class precision is key for that. However, the recall was low due to a high false negative rate for that class. This suggests that the boundary between the data distribution for both classes is not distinct in the dataset.

![](Aspose.Words.f430d02a-5392-4534-9f72-7ed6d6245122.003.png)

Using feature importance analysis, we were able to identify the most important factors that led to the classification of a weapon as a "Big Gun". Our analysis revealed that the number of victims was the most important feature in classifying the weapon as a "Big Gun". This implies that the more victims a school shooting has, the more likely it is that the gun used was a big gun. 

Overall, this information can be useful for policymakers and law enforcement in developing strategies to prevent and respond to school shootings. By understanding which types of weapons are most likely to be used in these incidents, they can focus their efforts on limiting access to those weapons and improving response protocols to minimize harm in the event of an attack.

**Question 3: Can we predict gun dealer types based on violations, inspection letter content, and license recommendation?**

The primary insights we intend to gain from this question are two-fold. First, we want to better understand how predictive this is based on the data. If it were not predictive at all, this suggests that the inspection reports are vague and the inspections in particular do not reveal information that could lead us toward reasonable policy solutions. Second, we want to understand which type of distributor is committing the most violations.

![](Aspose.Words.f430d02a-5392-4534-9f72-7ed6d6245122.004.png)

This feature importance graph illustrates our second goal, we can see that the total number of violations is highly important to classifying our class 1 ‘manufacturer’, suggesting that manufacturers of firearms are committing the greatest number of legal violations. Future policy recommendations should focus on minimizing the sheer number of violations committed by manufacturers in the US. In relation to policy goals, if we were not able to accurately classify our positive values, it suggests that the inspection reports are so vague that they do not capture the differences between distributors. This could mean a problem with the protocol involved in inspection reports that needs to be addressed. If there is going to be policy action, we want to be sure we know where we are directing it. Below is our strongest classification report in terms of precision which we are prioritizing for the prior reasons. 

![](https://drive.google.com/file/d/14IlwiIMCOVD11MrpYUm0-t9P95v7HWCh/view?usp=sharing)

Conclusions and Discussions - Overall 

In summary, the three questions addressed the relationship between gun violence and firearm laws, the prediction of the type of gun used in school shootings, and the identification of the most common violators of firearm regulations. The analysis revealed that certain types of firearm laws, such as those related to violent misdemeanors, firearm registration, and universal background checks, are likely to have a positive impact on reducing gun violence. The prediction model indicated that the number of victims is the most important factor in classifying a weapon as a "Big Gun" in school shootings, suggesting that policymakers and law enforcement should focus on limiting access to these weapons. Finally, the analysis identified firearm manufacturers as the most common violators of regulations, highlighting the need for policy recommendations to minimize the number of violations committed by manufacturers. Overall, these findings can inform policymakers and stakeholders in their efforts to reduce gun violence and improve public safety.

Future Work

Future work could involve expanding the scope of analysis to include other variables or factors that may impact gun violence or firearm laws. For example, the impact of mental health resources or economic factors on gun violence could be explored. Additionally, further research could investigate the effectiveness of specific policy interventions, such as those related to background checks or firearm registration. It may also be beneficial to conduct analyses at a more local level, such as examining the impact of firearm laws in specific cities or regions. Finally, ongoing evaluation and monitoring of firearm laws and their impact on gun violence is critical for identifying trends and informing evidence-based policy decisions.

References of the datasets

- <https://www.statefirearmlaws.org/resources>
- <https://projects.thetrace.org/inspections/methodology/>
- <https://github.com/washingtonpost/data-school-shootings>
- <https://wisqars.cdc.gov/data/explore-data/explore/selected-years>



