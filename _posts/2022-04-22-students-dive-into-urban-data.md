---
layout: post
lang: en
title: "Urban Analytics students dive into urban data"
date: 2022-04-22
description: "Four of our MSc in Urban Analytics students took part in the Centre for Urban Science and Progress London (CUSP London) Data Dive on 4-7 April with the theme of Working Towards Healthier Cities. As you can imagine, it..."
tags: ubdc teaching data-dive
related_posts: false
---

> Originally published on the Urban Big Data Centre blog on 22 April 2022 (by Jorge Michel, Samuel Hönle and Qunshan Zhao). The original page is no longer online — an [archived copy](https://web.archive.org/web/20220422111543/https://www.ubdc.ac.uk/news-media/2022/april/urban-analytics-students-dive-into-urban-data/) is available on the Wayback Machine, including the figures omitted here.

*Four of our MSc in Urban Analytics students took part in the Centre for Urban Science and Progress London (CUSP London) Data Dive on 4-7 April with the theme of Working Towards Healthier Cities. As you can imagine, it was right up their street.*

Fifty students from five universities were split into groups and tasked with tackling one of three challenges: Making sense of simulations of an infectious disease outbreak in Manchester; finding patterns in Stop and Search police data; combining COVID-19 data with other data sets to gain insights and to find correlations. They only had a few days to explore the data available and produce analyses to develop understanding and help deliver practical solutions to the challenges facing city-dwellers everyday lives.

UBDC MSc students Jorge Michel Gutierrez and Samuel Hönle explain the challenges they took part in and share their experiences below.

### Jorge’s experience

 

### The stop and search challenge

I was fortunate to collaborate with a very smart and passionate group of people from UCL and King’s College London, who had different bachelor's backgrounds, including music, data science, computer science and communication. However, we all shared similar master’s programmes, such as urban informatics, urban analytics, or spatial analysis. We chose to work on the crime challenge, where the main objective was to analyse stop and search data and understand its efficiency in crime reduction and prevention. Stop and search is a procedure conducted by the police if they have ‘reasonable grounds’ to suspect a person is carrying illegal drugs, a weapon, stolen property, or something which could be used to commit a crime. The data used was from UK data police, specifically crime and stop and search data, the English Index of Multiple Deprivation (IMD) and ONS census data.

 

### Our approach

We approached the problem from two perspectives. The first looked at possible demographics and socioeconomic biases that could be impacting the accuracy of stop and search and, therefore, the actual crime reduction. The second was to understand if the accuracy of stop and search had an impact on reducing crime. Lower Layer Super Output Areas (LSOAs) were taken as areas of analysis for both. For the first approach, a racial discrepancy metric was developed, which was the difference between the proportion of the non-white population in an area and the proportion of non-white people stopped and searched by the police in the same area. This was mapped to find if there was any pattern and if there was a relation to the crime reduction.

As shown in the maps above, we found that the non-white population is overrepresented in stop and searches in many LSOAs, with only very few areas where the opposite happens. We found a discrepancy ring around central London. However, there was no significant negative impact of the discrepancy on crime prevention, as many of the LSOAs presenting this overrepresentation still had a reduction in average crime from 2019 to 2021.

On the other hand, when looking at accuracy - the rate in which the outcome of a stop and search procedure was detention because those searched were carrying something illegal - we found that they have a measurable impact on crime reduction. However, the volume of stop and searches by itself had four times more impact on crime reduction than accuracy. This was concluded after a regression model where the IMD and the non-white population was included to control for sociodemographic factors that could have influenced the crime trends. When linking both findings - the racial discrepancy and accuracy - there was a very low correlation between them, as seen in the figure above.

 

### Conclusions

Based on the findings, we concluded that increasing the number of stop and searches can benefit crime prevention to a limited extent but after a certain point it becomes inefficient, and the reinforcement of racial discrepancies could override the benefits. To improve accuracy in procedures, police should look at factors such as deprivation of an area to determine the number of stop and searches that should be conducted.

### Samuel’s experience

 

### The COVID-19 challenge

The challenge brief was formulated very broadly, leaving the team with a lot of freedom in defining what we wanted to study. We decided to focus on the impact of policy decisions on COVID-19 infection numbers. Specifically, we wanted to know whether lifting the containment policy during the decline in infections in early 2022 measurably led to an increase in cases in London.

 

### Our approach

We combined COVID-19 infection data for London with a policy index for different pandemic response measures in England compiled by the University of Oxford. We then used interrupted time-series regression analysis to see which policy changes in early 2022 had a measurable effect on new infections. With that information, we went back to the last time measures were eased in mid-2021 and compared the results. By limiting the study both spatially and temporally, we tried to fix as many other effects as possible but emphasised that wider contextual knowledge of the pandemic was necessary to further interpret our results. We then compiled our findings to advise a policy maker on which policies to lift first after a hypothetical future COVID-19 wave.

 

### Conclusions

We found that:

- Lifting mask requirements completely, together with other measures, with a more transmissible variant in winter, significantly increased spread.

- Lifting the same restrictions in summer with a less transmissible variant and some mask requirements remaining, did not significantly increase the spread of the virus.

- School openings and allowing international travel had no direct measurable impact (early 2022).

One interesting feature of the process was the format of the presentations. The teams were challenged to limit their presentations to four slides:

- Slide one: a description of the problem, the data, and the limitations of the analysis

- Slide two: the findings, containing clear key insights or recommendations for policy makers

- Slide three: a visual representation of the results

- Slide four: any additional necessary insights into the data or the methods

Nick Holliman, Professor of Computer Science and Director of CUSP, explained that this was the most effective way to communicate research to decision-makers when tested with the British Army.

I am proud to say that my team received the Best Technical Contribution Award for our analysis and [presentation (PDF 0.98MB)](https://web.archive.org/web/2022/https://www.ubdc.ac.uk/media/2381/the-effects-of-policy-interventions-on-covid19-220422.pdf). You can view the code behind our analysis on [GitHub](https://github.com/samuelhoenle/cusp-dd-2022-group2).

Image: Winners of the Best Technical Contribution Award. From left to right: Elika Sinha, Yuning Jiang, Tongqing Zhu (also an MSc in Urban Analytics student), and Samuel Hönle.

The CUSP London Data Dive 2022 gave students the chance to apply the skills we gained in our studies to real-world data while focussing on producing useful results and presenting them in an innovative format. Participating in the event gave me confidence in the skills and education we receive at the University of Glasgow. And finally, participating in person meant that we could connect with fellow students in our field from other universities and our potential future colleagues, and enjoy four days in London together with them.

### A word from the MSc in Urban Analytics programme convener - Dr Qunshan Zhao

This year is the first time our MSc in Urban Analytics students have taken part in the CUSP Data Dive in London. The event provides a perfect opportunity for students to apply what they have learnt from our programme while under pressure in a fast-paced environment. As a result, our students improve their understanding of how data science is applied in real-world situations and develop practical skills in formulating questions, analysing data, and presenting results. We plan to continue participating in these events, which will provide a unique learning and networking experience for our future students.

**If you like what you've read and you're interested in studying with us, please visit our [MSc in Urban Analytics programme page](https://www.ubdc.ac.uk/education-and-events/education/msc-programmes/urban-analytics/) where you can find out more and apply.**
