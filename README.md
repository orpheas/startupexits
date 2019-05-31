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

## Data Analysis

Following an established theoretical framework when analysing and interpreting data is of paramount importance. Such a framework guides and ensures the quality of the analytical process (Saunders, Lewis, & Thornhill, 2015). One of the most popular analytical methodologies is the Cross-industry standard process for data mining — CRISP-DM (KD Nuggets, 2014). CRISP-DM was initially conceived in 1996 and was eventually developed into a full-fledged methodology by an industrial consortium funded by the European Commission. It was formally presented in 2000 (Chapman, et al., 2000).

The CRISP-DM model is comprised of six phases, as seen in Figure 1 below.

[CRISP-DM](https://upload.wikimedia.org/wikipedia/commons/thumb/b/b9/CRISP-DM_Process_Diagram.png/479px-CRISP-DM_Process_Diagram.png)

In more detail, these phases are:

Business understanding: At this stage, focus is placed on understanding the business background of the project and the data, how these can be translated to objectives and requirements, and, finally, how these objectives can add value to the business.

Data understanding: The data understanding phase includes the collection of data to be analysed, as well as data familiarization activities. These consist of running summary statistics, data visualisations, uncovering initial insights, as well subsets of the data that may be of interest.

Data preparation: This stage encompasses all activities required in order to produce the final dataset for analysis. These activities are data transformation (transforming the data types), data cleaning (removing missing value entries or substituting them), as well as feature engineering (selecting the features/variables to be used for the analytical model).

Modelling: In the modelling phase, various analytical & modelling techniques are selected and applied on the finalized dataset. Several techniques may be used.

Models used also re-inform the data preparation phase, with the analyst often able to edit and re-establish the final dataset.
Evaluation: At this stage of the analysis, the models built are subject to evaluation, based on relevant metrics (e.g. accuracy, true positives and false negatives, etc.)

The analyst is also responsible for evaluating whether the target objectives have been met and whether it is appropriate to alter current models or develop models anew.

Deployment: At the Deployment phase – the final phase – the final model is ready to be deployed. The deployment phase may range from helping guide the client on how to embed the model to his organizational needs, to simply producing a final report. In our case, deployment refers to the presentation of the final model.

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
