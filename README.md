# Predicting Startup Exits Using Crunchbase Data - A Venture Capitalist Perspective

## Abstract

Startups are cornerstones of advanced economies, but they fail at a high rate. Venture
Capitalists are responsible for sourcing promising startups, investing capital and value-added
services to help them grow, with the end-goal of achieving a return on
their investment. When investing in startups, VCs declare that some of the most significant
factors that play a role in their decision-making are the founding team, the business
model, the industry, and more. Utilizing data from Crunchbase, one of the largest
platforms in the world for startup, funding, acquisition, and IPO data, we attempt to
employ the decision-making factors of VCs in the production of machine learning models
that will predict which startups will reach acquisition or IPO stages, thus generating a
return for their venture investors. Our analysis formally adopts the CRISP-DM methodology
and employs Logistic Regression and Support Vector Machine algorithms in producing the
predictive models. Logistic Regression turned out to be our better performing model with
an F1 score of 61.69%, a Precision score of 63.07%, and TPR/FPR rates of 70.10%/57.55%.
With the model carrying promise for identifying investment-worthy startups, further
iterations have been recommended in order to produce a better and more robust model.

## Data Collection

The analysis dataset was acquired via https://data.crunchbase.com/docs.

## Analysis Framework

Following an established theoretical framework when analysing and interpreting data is of paramount importance. Such a framework guides and ensures the quality of the analytical process (Saunders, Lewis, & Thornhill, 2015). One of the most popular analytical methodologies is the Cross-industry standard process for data mining — CRISP-DM (KD Nuggets, 2014). CRISP-DM was initially conceived in 1996 and was eventually developed into a full-fledged methodology by an industrial consortium funded by the European Commission. It was formally presented in 2000 (Chapman, et al., 2000).

The CRISP-DM model is comprised of six phases, as seen in Figure 1 below.

![CRISP-DM](https://upload.wikimedia.org/wikipedia/commons/thumb/b/b9/CRISP-DM_Process_Diagram.png/240px-CRISP-DM_Process_Diagram.png)

In more detail, these phases are:

__Business understanding__: At this stage, focus is placed on understanding the business background of the project and the data, how these can be translated to objectives and requirements, and, finally, how these objectives can add value to the business.

__Data understanding__: The data understanding phase includes the collection of data to be analysed, as well as data familiarization activities. These consist of running summary statistics, data visualisations, uncovering initial insights, as well subsets of the data that may be of interest.

__Data preparation__: This stage encompasses all activities required in order to produce the final dataset for analysis. These activities are data transformation (transforming the data types), data cleaning (removing missing value entries or substituting them), as well as feature engineering (selecting the features/variables to be used for the analytical model).

__Modelling__: In the modelling phase, various analytical & modelling techniques are selected and applied on the finalized dataset. Several techniques may be used. Models used also re-inform the data preparation phase, with the analyst often able to edit and re-establish the final dataset.

__Evaluation__: At this stage of the analysis, the models built are subject to evaluation, based on relevant metrics (e.g. accuracy, true positives and false negatives, etc.). The analyst is also responsible for evaluating whether the target objectives have been met and whether it is appropriate to alter current models or develop models anew.

__Deployment__: At the Deployment phase – the final phase – the final model is ready to be deployed. The deployment phase may range from helping guide the client on how to embed the model to his organizational needs, to simply producing a final report. In our case, deployment refers to the presentation of the final model.

## Business Understanding

On their seminal report on Venture Capital, Gompers, Gornall, Kaplan, & Strebulaev (2016), conducted surveys on 889 venture capitalists from 681 different firms, in order to better understand how they function and what they believe are the most important aspects of successful startups. Among core VC functions, the report lists deal sourcing, investment selection, valuation, deal structure, post investment value-added, exits, internal firm organization, and relationships with limited partners. A majority of VCs see the startup team as a more valuable characteristic than the type of product or the startup domain (considered by 95% of VCs as an important factor and by 47% as the most important factor). The startup business model was rated as important by 83% of VCs, the product of the startup by 74%, the market maturity by 68%, and the industry/domain by 31% of VCs.

In predictive modeling, the literature seems to feature prominent works particularly in M&A prediction, with IPO prediction focusing mostly on share pricing.

Ragothaman, Naik, & Ramakrishnan (2002) utilized rule-induction methods to create an expert system for acquisition prediction; with the features built out of, primarily, financial metrics. The classification accuracy on the holdout sample were 81.3% for the acquisition and 65.6% for the non-acquisition cases.

Wei, Jiang, & Yang (2008) engineered features out of patent data; namely number of patents a company holds, patent impact, etc. They also formulated M&A prediction as a classification problem. Using an ensemble method, with Naïve Bayes classifiers and by assigning different weights to their features, they achieved a weighted average accuracy of 87.94%, with a Recall of 45.37% and Precision of 41.97% on the acquired companies, and a Recall of 92.8% and Precision of 93.67% on non-acquired companies.

Ali-Yrkkö, Hyytinen, & Pajarinen (2005) followed a similar approach, attempting to predict company acquisitions based on patenting and other company data of Finnish firms (firm size, free cash flow, etc.). Utilizing patent registration data from the European Patent Office (EPO), they employed a logistic regression algorithm to conduct a hypothesis test on whether these features affect acquisitions.

Meador, Church, & Rayburn (1996) focused on primarily financial (Long-term debt/Total Assets, Long-term Debt/Market Value) and other company data (firm size) and produced, once again, a logistic regression model for M&A prediction. The accuracy for correctly predicted M&A was 77.27% level, while for the non-M&A it was 50%. The dataset, however, was once again rather small (<200 observations).
Investigating predictive uses of Crunchbase data, we mainly come across Xiang, et al. (2012), as well as two more obscure works (0-1 citations).

Xiang, et al. (2012) uses both Crunchbase, as well as Techcrunch (startup news website) data (e.g. number of articles on the startup, as well as topical features extracted from said articles), attempting to predict company acquisitions. The problem is again formulated as a binary classification problem, with the first, “successful” group defined as the group of acquired startups, and the second, “unsuccesful” group defined as the group of non-acquired startups or startups that IPO’d.
The paper split companies in sub-samples according to industry domains. Using Bayesian Networks, they achieved True Positive percentages ranging up to 79.8%, with False Positive rates ranging between 0-8.3%. Support Vector Machine and Logistic Regression algorithms were also employed; they, however, greatly underperformed compared to the Bayesian networks. In a given example, they state that “the TP (True Positive) and FP (False Positive) on companies in the aggregate “computer” category for SVM (Support Vector Machine) and LR (Logistic Regression) without topic features are 39.6%/0.1% and 2.8%/0.3% respectively, while BN achieved 59.9%/2.2%.”

Looking at the two more obscure papers, we firstly see Bento (2017) utilizing exclusively the Crunchbase dataset and formulating the problem as a binary classification problem (Group 1 being startups that either got funded or were acquired, Group 2 being non-funded and non-acquired startups). By using a Random Forest model, the paper achieves a True Positive Rate of 94.1% and a False Positive Rate of 7.8%, with a Precision rate of 92.2% and the AUC (Area Under Curve) at 93.2%.

Finally, Pan, Gao, & Luo (2018) utilized another instance of the Crunchbase dataset on a binary classification formulation (Group 1 being startups that reached IPO or were acquired, Group 2 being startups that neither reached IPO, neither were acquired), and employing a K-nearest Neighbors algorithm, achieved an F1 score of 44.45% and an accuracy of 73.70%.

## Data Understanding

_Data is confidential_

## Data Preparation

We have tested for __missing values__, __outliers__, and __categorized__ and __binned__ features, since we are dealing with a binary classification problem.

## Modelling 

Tested for __imbalance__ in the dataset and treated the imbalance with __oversampling__ the minority class.

In terms of algorithms, we utilized a Logistic Regression algorithm, as well as a Support Vector Machine algorithm. We have first trained the models on a training split (70%), and subsequently tested on the testing split (30%).

Logistic Regression turned out to be our better performing model with an F1 score of 61.69%, a Precision score of 63.07%, and TPR/FPR rates of 70.10%/57.55%.

## Evaluation

The main metrics used to build upon further evaluation models, are the numbers of True Positives (TP), True Negatives (TN), False Positives (FP), and False Negatives (FN). Most evaluation metrics are built upon these main measures.

- TP rate is the rate of classifying a company as acquired/IPO, while it is indeed acquired/IPO
- FP rate is the rate of classifying a company as acquired/IPO, while it is not acquired/IPO
- FN rate is the rate of classifying a company as not acquired/IPO, while it is acquired/IPO
- TN rate is the rate of classifying a company as not acquired/IPO, while it is indeed not acquired/IPO

Overall classification accuracy is defined as:
Accuracy = (TP + TN) / (TP + FP + FN + TN)

Other metrics are defined as:
Precision (ability to find all relevant instances that are actually relevant) = TP / (TP+FP)
True Positive Rate (ability to find all relevant instances) = TP / (TP+FN)
False Positive Rate (the rate of falsely identifying negatives as positives)= FP / (FP + TN)
F1 Score = 2 * ((Precision*Recall) / (Precision+Recall))

## References

Ali-Yrkkö, J., Hyytinen, A., & Pajarinen, M. (2005). Does patenting increase the probability of being acquired? Evidence from cross-border and domestic acquisitions. Applied Financial Economics, 15(14), 1007-1017.

Alpaydin, E., & Bach, F. (2014). Introduction to Machine Learning. MIT Press.

Baesens, B. (2014). Analytics in a Big Data World: The Essential Guide to Data Science and Its Applications. John Wiley & Sons, Incorporated.

Bento, F. (2018). Predicting start-up success with machine learning. Doctoral Dissertation.

Blank , S., & Dorf, B. (2012). The Startup Owner's Manual.

Burkov, A. (2019). The Hundred-Page Machine Learning Book. Self-published.

Chapman, P., Clinton, J., Kerber, R., Khabaza, T., Reinartz, T., Shearer, C., & Wirth, R. (2000). CRISP-DM 1.0 Step-by-step data mining guide. SPSS.

Coghlan, D., & Brannick, T. (2005). Doing Action Research in Your Own Organization. SAGE Publications.

Crunchbase Inc. (2019). About Us: Crunchbase. Retrieved 2019, from Crunchbase: https://about.crunchbase.com/about-us/

Exploiting Technological Indicators for Effective Technology Merger and Acquisition (M&A) Predictions. (2014). Decision Sciences, 45, 147-174.

Fanning, K., & Drogt, E. (2014). Big Data: New Opportunities for M&A. The Journal of Corporate Accounting & Finance(January/February), 27-34.

Feinleib, D. (2012). Why Startups Fail. New York: Springer.

Ghosh, S., & Gage, D. (2012, September 20). The Venture Capital Secret: 3 Out of 4 Start-Ups Fail. Wall Street Journal.

Gompers, P., Gornall, W., Kaplan, S. N., & Strebulaev, I. A. (2016). How Do Venture Capitalists Make Decisions? European Corporate Governance Institute.

Haislip, A. (2011). Essentials of Venture Capital. Wiley.

Hastie, T., Tibshirani, R., & Friedman, J. (2008). The Elements of Statistical Learning. Springer.

Hosmer, D. W., Lemeshow, S., & Sturdivant, R. X. (2013). Applied Logistic Regression. Wiley.

KD Nuggets. (2014, 10). CRISP-DM, still the top methodology for analytics, data mining, or data science projects. Retrieved from KD Nuggets: https://www.kdnuggets.com/2014/10/crisp-dm-top-methodology-analytics-data-mining-data-science-projects.html

Lewis, K. (2015, July-December). Three fallacies of digital footprints. Big Data & Society, 1-4.

McAbee, S. T., Landis, R. S., & Burke, M. I. (2017). Inductive reasoning: The promise of big data. Human Resource Management Review, 27, 277-290.

Meador, A. L., Church, P. H., & Rayburn, L. G. (1996). Development of prediction models for horizontal and vertical mergers. Journal of financial and strategic decisions, 9(1), 11-23.

Mesnard, A., & Ravallion, M. (2006). The wealth effect on new business startups in a developing economy. Economica, 73.291, 367-392.

NASDAQ & Business Wire. (2019, May 09). NASDAQ News. Retrieved from NASDAQ: https://www.nasdaq.com/press-release/uber-announces-pricing-of-initial-public-offering-20190509-01539

Pan, C., Gao, Y., & Luo, Y. (2018). Machine Learning Prediction of Companies’ Business Success. CS229 Stanford University.

Provost, F., & Fawcett, T. (2013). Data Science for Business. O'Reilly Media.

Ragothaman, S., Naik, B., & Ramakrishnan, K. (2002). Predicting corporate acquisitions: An application of uncertain reasoning using rule induction. Information Systems Frontiers, 5(4), 401-412.

Ries, E. (2011). The Lean Startup: How Today's Entrepreneurs Use Continuous Innovation to Create Radically Successful Businesses. Crown Publishing Group.

Robehmed, N. (2015, March 2). The World's Youngest Billionaires 2015: 46 Under 40. Forbes.

Saunders, M., Lewis, P., & Thornhill, A. (2015). Research Methods for Business Students.

Towards Data Science, & Koehrsen, W. (2018, Mar 3). Beyond Accuracy: Precision and Recall: Towards Data Science. Retrieved from Towards Data Science: https://towardsdatascience.com/beyond-accuracy-precision-and-recall-3da06bea9f6c

Towards Data Science, & Narkhede, S. (2018, May 9). Understanding Confusion Matrix: Towards Data Science. Retrieved from Towards Data Science: https://towardsdatascience.com/understanding-confusion-matrix-a9ad42dcfd62

Vance, A. (2017, August 1). How Two Brothers Turned Seven Lines of Code Into a $9.2 Billion Startup. Bloomsberg Businessweek.

Wei, C. P., Jiang, Y. S., & Yang, C. S. (2008). Patent analysis for supporting merger and acquisition (m&a) prediction: A data mining approach. Workshop on E-Business, 187-200.

Wu, J. C. (1997). Statistics = Data Science?

Xiang, G., Zheng, Z., Wen, M., Hong, J., Rose, C., & Liu, C. (2012, May). A supervised approach to predict company acquisition with factual and topic features using profiles and news articles on techcrunch. Sixth International AAAI Conference on Weblogs and Social Media.
