# Fraud Detection and Prevention Repo
This repo serves as a research list for those trying to detect or prevent financial fraud in real-time or batch. 
I've collected links to papers, great learning resources, algorithms and more. 
Please submit a pull request if you see incorrect information or want to add some new resources.

## Sections:

*if you are looking for Covid-19 Trend information [click here](#covid-19-coronavirus-scams-2020-trend)!

----

1. [Trends and IOCs](#trends-and-iocs)
1. [Papers and Articles about Fraud Analysis](#papers-and-articles-about-fraud-analysis)
1. [Learning Tools](#base-understanding-and-learning-tools)
1. [Algorithms](#algorithms)  
1. [Data Sources](#data-sources)

----
## Trends and IOCs [^](#fraud-detection-and-prevention-repo)
This section details trends that have been observed on fraudulent electronic transactions. 
Also included are Indicators of Compromise (IOC) for an account or an electronic payment. 
A trend or IOC can be something tested multiple times like a [Benford's Law](#benfords-law), 
a country that is risky to send wires to, or a hunch based on a one or more real data sets.

### Benfords Law
Have you ever seen a fraudster or unwitting customer send a transaction just under some arbitrary threshold?  

*For example: $9,999 can feel like a really common bad amount.*  

But why? 
It's partially due to $10,000 being the reporting threshold for most banks, 
but also due to a phenomenon known as Benford's Law. 
In a real data set the number 9 is very unlikely to be the first digit. 
In fact, there is less than half a percent chance that the first digit is a 9.
Benford's Law holds up remarkably well across non faked data sets.  It has been used to catch accounting fraud and
can be extended to real time transaction monitoring.  The original algorithm looks at the first digit of a number
and can reliably predict the percent chance that digit is a 1-9. 
There is a 30% chance of a one being in the first digit, while odds go down for 2, 3, 4 and so on. 
If you are able to check the first digit of all amounts in your data set, and then check all known fraud you may see a 
pattern for your known fraud vs your known good data. 
There should be a slight variation between fraud and good data due to fraud data being more likely to be made up 
randomly than for a normal business payment. 
The difference between your normal and fraud transactions can then be applied to the reall time analysis of those transactions.  

Detailed Description: https://mathworld.wolfram.com/BenfordsLaw.html

#### Extensions of Benfords Law
Benford's law extends to second and third digits, but only marginally.  It is best used for first digit analysis. 
That said, I was able to look at digit frequencies to find some interesting trends!

##### Trend 1: Zero Cents
I found that it is 3 times more common to see a dollar amount with zero cents in a fraud data set, than a good data set.
Meaning that if I took 100 fraudulent transactions and 100 normal transactions, 
I would see 75 fraud transactions with zero cents and 25 normal transactions with zero cents.

Example: $1,234.**00**

##### Trend 2: Digit Frequencies
I found that fraud transactions tend to be more "round" than non fraud transactions. 
About 17% of my normal data set was round, while 35% of my fraud data was round.  Round came in many different forms. 
I counted digit frequency and found that zeros occurred (in any position) more often in fraud than non fraud. 
Also, if you modulus by 1,000 you can see "super round" values. 
These super round values occurred more often in fraud cases as well.

Example 1: $1,**0**3**000**4.**00**  
Example 2: $1,23**0,000.00**

### Covid-19 (Coronavirus) Scams (2020 Trend)
There are many covid-19 scams out there, and the landscape is changing daily. 
If a fraud system does not react to current events it will not catch as much fraud as it should. 
One thing that can be quick to implement are searches on keywords. 
Below is a list of keywords that may be found on anomalous transactions:
- virus
- corona
- corona virus
- coronavirus
- covid
- gloves
- nitril (type of glove used)
- clean (many companies are cleaning their offices, causing demand to go up and scammers to offer fake services, fair amount of FP)
- face
- mask
- medicine
- N95
- ppe (personal protective equipment)
- protect
- infect
- disinfect
- gown
- formula (baby formula is in demand)
- treatment
- tylenol
- S413 (type of protective equipment)
- medical
- vaccine
- crisis
- emergency
- cure
- donation (searched for "donat" so I could catch donate too)
- kit (testing kits are in high demand, kit produces lots of FP due to kitchen and similar words)
- ventilator (search on "ventilat" to get ventilation)
- respirat (to catch respirators and respiration)
- work%home (trying to find work from home)
- purif (to catch purification, purify)
- sanitation
- WHO (for world health organization)
- health (skimmed this, lots of hits)
- safe investment
- test (lots of FP)
- Italy
- ransom
- stimulus
- duct (air duct cleaning scams are a new trend)

Here are a list of great sources to find out more about current malicious covid-19 activity:
- Department of Homeland Security Alert: https://www.us-cert.gov/ncas/alerts/aa20-099a
- Github list of IOCs: https://github.com/parthdmaniar/coronavirus-covid-19-SARS-CoV-2-IoCs/blob/master/All%20IOCs
- Github list from Sophos Labs: https://github.com/sophoslabs/covid-iocs
- Reddit: https://www.reddit.com/r/blueteamsec/comments/fiy0i8/master_thread_covid19corona_threat_actor_campaigns/

## Papers and Articles about Fraud Analysis [^](#fraud-detection-and-prevention-repo)
### My Favorite Papers:
- TitAnt: Online Real-time Transaction Fraud Detection in Ant Financial
  - Has some great details and references on specific algorithms and their performance compared to each other.
  - [link to paper](https://arxiv.org/pdf/1906.07407.pdf)

### Repos with links to more papers
- Repo containing papers on fraud analysis: 
  - https://github.com/benedekrozemberczki/awesome-fraud-detection-papers
- Another fraud analysis paper repo on github:
  - https://github.com/YingtongDou/graph-fraud-detection-papers

## Base Understanding and Learning Tools

### Free
- Many resources and online classes here:
  - https://www.freecodecamp.org/news/free-courses-top-cs-universities/
- Learning financial data science: 
  - https://github.com/financial-data-science/CFDS-4
- Some ML models: 
  - https://github.com/georgymh/ml-fraud-detection
- High Level Explanation of some machine learning techniques: 
  - https://pkghosh.wordpress.com/2012/01/02/fraudsters-outliers-and-big-data-2/
- Data Science topics and tools:
  - https://www.kaggle.com/
- General Learning Resource with Online books and videos
  - https://www.packtpub.com/free-learning
- Credit Card Fraud Detection with Python Video:
  - https://youtu.be/PmssNOAeqdk
- Wikipedia: Data analysis techniques for fraud detection
  - https://en.wikipedia.org/wiki/Data_analysis_techniques_for_fraud_detection

### Paid Resources
- O'Reilly Online Learning ($500 a year)
  - https://www.oreilly.com/online-learning/individuals.html

### Books
Many of these books or ones like them may be available to you through your school/work library learning centers. 
If you don't have access to them there, you may have access to some of the web portals these books reside for free on 
(such as Wiley's [site](https://onlinelibrary.wiley.com/)). 
As a final resort, all of the titles link to amazon for purchase.


- [Forensic Analytics: Methods and Techniques for Forensic Accounting Investigations (Wiley Corporate F&A) 2nd Edition](https://smile.amazon.com/dp/1119585767/?coliid=I2LDWXN5OKT2YB&colid=1C4JD9ARYRA9V&psc=1&ref_=lv_ov_lig_dp_it)
  - Great book about some general accounting and financial fraud. 
  Discusses a deeper dive into Benford's law, Correlation, Time-Series Analysis, Risk Scoring and many other topics.

- [The Hundred-Page Machine Learning Book](https://smile.amazon.com/dp/199957950X/?coliid=INUFIW0CDO33T&colid=1C4JD9ARYRA9V&psc=1&ref_=lv_ov_lig_dp_it)
  - Shortest book to give a high level overview of many techniques.  This is a great introduction to machine learning

## Algorithms [^](#fraud-detection-and-prevention-repo)

### Machine Learning (ML) and Artificial Intelligence (AI)

#### Naive Bayes Classification:
- Brief description: 
  - https://towardsdatascience.com/introduction-to-naive-bayes-classification-4cffabb1ae54
- Python examples of different implementations with scikit-learn: 
  - https://scikit-learn.org/stable/modules/naive_bayes.html

#### Iterative Dichotomiser 3 (ID 3): 
- based on decision tree learning using rules.

#### See5/C5.0: 
- finds patterns and categories and uses that to make predictions
  - https://www.rulequest.com/see5-info.html

#### Isolation Forest:

#### Logistic Regression: 
- https://towardsdatascience.com/logistic-regression-detailed-overview-46c4da4303bc
- https://www.statisticssolutions.com/what-is-logistic-regression/

#### Factor Analysis:

#### Multiple linear regression:

## Data Sources
Below is a list of free data sources that can be used to practice some of the techniques described in this repo.

- Credit Card Fraud Detection: https://www.kaggle.com/mlg-ulb/creditcardfraud
- Synthetic Financial Transactions: https://www.kaggle.com/ntnu-testimon/paysim1
- German Credit Card data set: https://weka.8497.n7.nabble.com/file/n23121/credit_fruad.arff
- General Open data from many countries, here link to US open data: https://www.opendata500.com/us/list/