---
title: 'Missing data in the SHARE Job Episodes Panel: A potential cause and solution

<img src="/files/2023-01-25-blogpost_jep/3_1_distribution_imputation-situation_gender.png" style="display: block; margin: auto;" />
'
date: 2023-01-25
permalink: /posts/2023/01/blogpost_jep/
tags:
  - SHARE
  - JobEpisodesPanel
  - goodtoknow
  - replication
---

<br />


## Missingness in the Job Episodes Panel


The Survey of Health, Ageing and Retirement in Europe (SHARE) is a cross-national panel study for individuals aged 50 and older covering 28 countries in the most recent waves (Bergmann u. a. 2019). SHARELIFE contains valuable and detailed retrospective data about individual life courses. Instead of the raw survey data, many researchers use the Job Episodes Panel (JEP), a generated dataset containing information on working life courses based on the retrospective SHARELIFE data (Brugiavini u. a. 2013, 2019). One of the particularly rich variables is the situation indicator containing the self-reported situation or activity individuals were in for each year, covering multiple categories out of labour force. Constructing such variables and making them publicly available is an important service for the academic community and improves the comparability of research since the data preparation is less heterogenous compared to when data preparation is based on individual decisions. However, the situation variable contains missing information for sizeable shares of person-year spells. This is problematic because missingness seems to be not random when looking at the two dimensions countries and gender.
Using the person-year-spells for ages above 15 of whole JEP sample, the average share of missing observations of all person-year spells per person on the situation variable ranges from 1.5% in Denmark to 7.5% in Poland for men and from 3.5% in Estonia/Slovakia to 33.4% in Malta for women (figure 1). In many countries there is a considerable gender differences in relative missingness, while the level varies across countries. Due to this sizeable missingness, individual studies have to make decisions on how to proceed with such missing data (e.g. listwise deletion or imputations) if they are aware of them in the first place. These different approaches are likely to produce biased results since specific countries as well as specific groups of men and particularly women (see below) will have been more affected by large shares of missing information on their working lives.
When focussing on all person-year-spells the gender gaps become narrower (figure A1). However, in most empirical applications, the situation variable might be applied for employment biographies which is why I focus on the ages above 15 in the main figures here.  


### Figure 1: Missingness before adjustment.

<img src="/files/2023-01-25-blogpost_jep/1missing-before-impu_genderXcountry_2r_rel_age16.png" style="display: block; margin: auto;" />

 <font size="1"> Own calculations based on whole sample of JEP release 7.1.0.6</font>



## The Source of Missingness and a Potential Solution

The Job Episodes Panel (up until release 8.0.0) does not consider variables of the raw data containing information on the situations people were in after their last job (variables re035_*, re039_*, re039a_*). They are then asked whether the situation changed again and to report the second situation they were in after the change etc. until their situation does not change anymore. Most of the spells with missing information can be filled using this information of the raw data.
I impute only person-year-spells that are missing on the situation variable and that occur in the years after the last reported job (re035). Spells with missing information are filled for each year until the first year with non-missing information on the situation variable or until the situation changed again (re039a). If the situation changed, the same procedure is done for the nth situation after the last job nth times. The year in which the situation after the last job changed is filled with the new situation. 
The code for filling the missing information is available here:

## Reduction in Missingness & country- and gender-specific patterns

Figure 2 shows the share of missingness by country and gender after filling the missing information as described above. The level of relative missingness drops down to on average below 2% of all person-year spells for most countries. The improvement differs across countries and gender, but overall, the gender gaps in missingness are reduced to a minor level. 
When considering all person-year spells and not only those for ages 16 onwards the share of missing data drops down to an average of 7-9% for most countries (figure A2). This is because most respondents have missing information in their first 4 years of life which cannot be filled by the applied procedure – 81% of the remaining missing information on the situation variable occur during the first 15 years of age. And a large share of the remaining missing information is due to gaps between education and the first situation after the end of the education phase.


### Figure 2. Missingness after adjustment.

<img src="/files/2023-01-25-blogpost_jep/2missing-after-impu_genderXcountry_2r_rel_age16.png" style="display: block; margin: auto;" />

 <font size="1"> Own calculations based on whole sample of JEP release 7.1.0.6</font>

 Figures 3 shows the categories of the situation variable that have been filled in relative and absolute terms by gender and pooled over all countries. 77.8% of the missing data (a total of 194,383 person-year spells) for women is due to unpaid care work (Looking after home and family) they engaged in after their last job. Thus, not considering the situation respondents were in after their last job produces particularly large shares of missing spells for women engaged in care work. This is most likely due to the traditionally gendered division of labour in most of the observed countries, in which women are more likely to drop-out of the labour market and retire earlier due to care duties (e.g. Carr u. a. 2016; Zagel und Van Winkle 2020). Thus, a large share of unpaid care work is obscured in the original situation variable. For women, small shares of the previously missing data represent being sick or disabled as well as unemployment periods – spells that were underestimated in the JEP data so far too.

 ### Figures 3. Distribution of working states that have been filled for all countries by gender.

 <img src="/files/2023-01-25-blogpost_jep/3_1_distribution_imputation-situation_gender.png" style="display: block; margin: auto;" />
 <img src="/files/2023-01-25-blogpost_jep/3_2_distribution_imputation-situation_gender_freq.png" style="display: block; margin: auto;" />
  <font size="1"> Own calculations based on whole sample of JEP release 7.1.0.6</font>