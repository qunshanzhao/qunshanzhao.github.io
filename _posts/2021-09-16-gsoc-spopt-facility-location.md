---
layout: post
title: "A summer of Python coding — open-source facility location modelling (spopt) development"
date: 2021-09-16
description: "Since its launch in 2005, the Google Summer of Code programme has introduced over 16,000 students to open-source software development."
tags: ubdc spopt open-source gsoc
related_posts: false
---

> Originally published on the Urban Big Data Centre blog on 16 September 2021 (by Germano Barcelos, James Gaboardi, Levi Wolf and Qunshan Zhao). The original page is no longer online — an [archived copy](https://web.archive.org/web/20210917123554/https://www.ubdc.ac.uk/news-media/2021/september/open-source-facility-location-modelling-spopt-development/) is available on the Wayback Machine, including the figures omitted here.

*Since its launch in 2005, the Google Summer of Code programme has introduced over 16,000 students to open-source software development.*

This global initiative has partnered participants with 13,000 mentors from over 118 countries worldwide to work on a ten-week programming project. In 2021, Germano Barcelos worked with three mentors from [PySAL](https://github.com/pysal/pysal) and [NumFOCUS](https://numfocus.org/) to develop a facility location modelling module to optimally solve facility location problems under various distance metrics.

In this blog, the [project team](#Team) explain the four facility location models developed by Germano and share the future plans for this project.

### Background to the project

Facility Location Modelling first appeared more than 100 years ago during the industrial revolution. Businesses needed to find the optimal locations to place factories to reduce logistical costs or build retail centres to generate more revenue from customers. Since then, researchers have developed coverage models to answer questions such as where to locate fire stations to fully cover the residential neighbourhoods within a given distance/time threshold or build a defined number of wireless towers to cover a certain percentage of the wireless communication network. Most facility location modelling problems have been formulated as mixed-integer programming problems. Given these problems are computationally difficult (NP-hard), they require the most powerful solvers from availing in Operations Research to find a solution in a tolerable period of time. Facility location modelling is also a geographical problem, so we need to work with spatial datasets such as road networks and polygon areas and use GIS to facilitate the data preparation, processing, storage, and visualisation.

In one recent review paper, [Chen et al. (2021)](https://link.springer.com/article/10.1007%2Fs10109-021-00350-w) discussed open source and proprietary software developed for facility location modelling (Location Set Covering Problem (LSCP) and Maximal Coverage Location Problem (MCLP)) including Microsoft Excel (FLP Solver), ArcGIS, R (Maxcovr), and Python (PySpatialOpt). The first two solutions are rooted in commercial software, using a heuristic approach to solve the MCLP and LSCP. Alternatively, Maxcovr and PySpatialOpt are based on open-source software (R/Python) and use an exact approach to solve the same models with generalised optimisation solvers. However, all these tools only provide very limited options for various metrics in the facility location modelling such as facility capacity, distance metrics, demand object shapes, demand weights, and solution approach. None of the software here can provide a single ‘one-stop’ open-source ecosystem to comprehensively address facility location modelling problems for the general users.

During the Google Summer of Code 2021, Germano developed four facility location models including LSCP/MCLP/P-Center/P-Median models in the PySAL Spopt repository. More information about these models can be found in books by Church, R. L., & Murray, A. T.: [Business Site Selection, Location Analysis and GIS](https://onlinelibrary.wiley.com/doi/book/10.1002/9780470432761) and [Location covering models: History, applications and advancements](https://www.springer.com/gp/book/9783319998459). All models are solved by using an exact approach with [PULP](https://github.com/coin-or/pulp) and can compute distance matrices with different metrics, such as Euclidean and Manhattan. The module provides the objective values for each model. Furthermore, for the P-Median model, the module can compute the mean distance of the objective value and the MCLP module can compute the percentage of model coverage.

### Model evaluation and validation

For validation purposes, we first tested the MCLP results with the same example in Chen et al. (2021). It used U.S. census tract centroids as demand points and 16 candidate store sites. The objective is to cover the maximum amount of demand points given the population in the 2000s for each demand point given that only 4 stores can be located within the area. The MCLP results are shown in Figure 1. The figure shows where stores are sited to cover the maximum population in census tracts. The percentage of demand points covered is 87.76% and 21 points are not covered by any of the stores (white dots in the figure).

Figure 1. MCLP results from Pysal Spopt package ([Jupyter Notebook example](https://nbviewer.jupyter.org/github/pysal/spopt/blob/main/notebooks/mclp.ipynb)).

Moreover, we used the same dataset to solve the other three problems supported by the new module developed. Figure 2 represents the solution for the LSCP problem. The objective of this model is to minimize the number of facilities placed to cover all the demand points. Figure 2 shows that 8 facility sites must be placed to achieve full coverage.

Figure 2. LSCP results from Pysal Spopt package ([Jupyter Notebook example](https://nbviewer.jupyter.org/github/pysal/spopt/blob/main/notebooks/lscp.ipynb)).

Figure 3 displays the P-Median problem example. This model aims to minimize the sum of the travel distances from demand to supply by locating a fixed number of facilities. We located 4 facilities in our example here. Besides that, the population in each centroid is the weight of the model. In the solution results, the mean distance is approximately 2982.13 meters.

Figure 3. P-median results from Pysal Spopt package ([Jupyter Notebook example](https://nbviewer.jupyter.org/github/pysal/spopt/blob/main/notebooks/p-median.ipynb)).

Figure 4 displays the P-Center model that aims to minimize the maximum distance between a demand point and store site with a fixed number of stores to be placed. We located 4 facilities in our example here. The maximum distance of a demand point to a facility site in this solution is 7403.06 meters.

Figure 4. P-Center results from Pysal Spopt package ([Jupyter Notebook example](https://nbviewer.jupyter.org/github/pysal/spopt/blob/main/notebooks/p-center.ipynb)).

### Future plans

We plan in the future to add capacity constraints in models and aim to provide a polygon partial coverage, which is another feature that no library supports yet. Since this is an open-source project, feel free to contribute your code and raise issues at our [GitHub repository](https://github.com/pysal/spopt).

Note: One thing to remember is the solver wrapper PULP used by our module as well as PySpatialOpt. PULP makes it possible to use many solvers like Gurobi, CPLEX, CBC, and other solvers if they are installed. Therefore, the module can be used to solve problems that require a large amount of resources.

### Final thoughts on the project from Germano

"Before the start of the programme, I did not have any background on the facility location modelling topic and this inspired me to work hard to get a good understanding of it to develop the module. During the summer, working on an open-source project introduced me to a new world of developing tests and running them automatically using continuous integration and delivery (CI/CD) tools like GitHub Actions. Besides that, I managed to know how the open-source community works were marvellous. Furthermore, I have significantly improved my communication skills including how to elaborate what I was thinking objectively and discuss ideas with my mentors to solve the problems in the best way."

### Project Team

- Germano Barcelos, Universidade Federal de Viçosa, Brazil

- Dr James Gaboardi, Oak Ridge National Laboratory, USA

- Dr Levi John Wolf, School of Geographical Sciences, University of Bristol, UK

- [Dr Qunshan Zhao](https://www.ubdc.ac.uk/about-ubdc/who-we-are/team-profiles/directors/qunshan-zhao/), UBDC and Urban Studies, University of Glasgow, UK
