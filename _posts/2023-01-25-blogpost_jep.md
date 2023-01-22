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

 

