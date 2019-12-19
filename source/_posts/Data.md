---
title: The Mining and Analysis of Web Recruitment Information
tags:
  - Data Mining
photos:
  - 'http://wenchao4quant.oss-ap-southeast-1.aliyuncs.com/research/datamining/cluster_s.png'
  - 'http://wenchao4quant.oss-ap-southeast-1.aliyuncs.com/research/datamining/net_s.png'
date: 2017-12-10 18:08:44
categories: Research & Projects
---

"*The Mining and Analysis of Web Recruitment Information Based on Document mining, Occupation Network and Time Series Model*", **4th TipDM Cup National Data Mining Race Project**

**Author**：W. C. Zhang, Y. Wu, Y. R. Han

**Abstract**: With the development of network applications, more and more recruitments information is listed on the webs, and these information reflects the certain assignments of the firms on their future crews, these properties including the occupation need, competences and skills. Meanwhile, these information also provides universities and colleges for knowing the update demand of the talents from the society in time, and then arraneging the majors and courses, which also promotes the academic performance of students.

<!-- more -->

However, is there any relationship among occupations and degrees and working experiences? Which property is helpful for applicants to be assigned? To answer these questions, the anaylsis for web recruitment information bears huge practical value, and according to the specific property of these information, the application of data mining techniques to explore being the fundamental method. This paper researches the correlations among the recruitments information basing on the techniques of text mining, and analyses the internal correlations behind information in the way of descriptive analysis and modelings, which can really serve to provide useful information and suggestions for education development of universities and colleges.

In data mining process, we first use R toprocess unstructured data, segment Chinese words and filter disable word with package `tm`, meanwhile constructing Volatile Corpus with `Rwordseg`, which realizes clearing up unstructured data in recruitment information. Secondly, we construct a complex network model transform from TF-IDF term matrix to find the correlation between the talent recruitment information, which is the basis for the subsequent hierarchical description. As a result, we extract the structured data in the work experience, education level, salary level, geographical distribution and release time to give a multi-dimension description for talent demand. Moreover, time series model predicts jobs quantity showing the urge demand in data mining industry. Finally, based on CIER, we deeply analyse supply and demand of IT industry and its trend in future development by the methods combined statistics and economics.

**Key words**: Data Preprocess; Text Mining Complex; Time-Series Modeling