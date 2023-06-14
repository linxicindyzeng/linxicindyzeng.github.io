---
layout: page
title: CCAS in China
description: Graphs on the Evolution of CCAS in China
img: assets/img/H.png
importance: 1
category: work
---

## Graphs on the Evolution of CCAS in China

A Centralized Choice and Assignment System (CCAS) at an education level is defined by the simultaneous existence of educational institutions whose enrollment is at least partially determined by an external agency or platform, applicants who submit a list of their preferences to the agency, and the agency then giving the applicants a single offer, using certain criteria and allocation rules. Neilson (2019) documents the rise of CCAS in primary, secondary and tertiary education markets worldwide, and increasing research is being conducted on characteristics of existing CCAS (e.g., time of establishment, form of preference list, assignment mechanisms) and how they can be designed to facilitate education equity (see Akbarpour et al. (2022), Arteaga et al. (2022), Kapor, Neilson, & Zimmerman (2020)).

This project started as a sub-project of "Worldwide CCAS," focusing on [China's 135 cities whose population exceeded 1 million in 2020](https://www.citypopulation.de/en/china/cities/). I collected a cross-section data set documenting CCAS characteristics in primary and secondary education in these cities primarily from reading 2022's policy documents by local bureaus of education. Variables include: Existence of a CCAS, Participating institutions, List length, Website to apply, Implementation year of a CCAS, Priority groups, and Mechanisms (Deferred Acceptance, Boston, Serial Dictatorship, etc.)

I then put together a panel data set of the 135 cities, 2003-2022, using the above and National Bureau of Statistics's China City Statistical Yearbook, which has a rich set of city-level socio-economic indices. Variables on city characteristics are: City name, CCAS switch year, Characteristic year, Household registered population year-end, Gross Regional Product, Per capita GRP, GRP Growth Rate (%), Expenditure on education (10 000 yuan), Number of regular secondary Schools, Regular Primary Schools, and number of students in colleges, secondary schools, vocational secondary schools, and elementary schools.

### Descriptive Statistics
Number and percentage of city-level CCAS in primary, middle, and high school admission (2003-2022) among 129 cities whose 2020 population exceeds 1 million.

![Descriptive Statistics](/assets/img/Comb1.png)

Below is an interactive graph of the age of each 1m city's high school CCAS in 2020. I plan to develop this into a graph containing information from 2003 to 2022, and each year is a layer the user can select to display or hide. This would be a good visualization of the first movers (the cities with darker shades) and the dynamic spread over time. It will be easy given that I've already visualized 2020's data. I will only need a bit more time to learn addTiles().

It can already be seen that the "biggest" cities in China, Beijing, Shanghai, Shenzhen, and more generally, the south-east coastal cities were pioneers in implementing a CCAS on the high school level.

![Interactive Graph](/assets/img/Agein2020.html)

Flow graphs:

![Flow Graph 1](/assets/img/H_flow.png)

![Flow Graph 2](/assets/img/PM_flow.png)

Establishment year of existing CCAS:

![Establishment Year 1](/assets/img/H.png)

![Establishment Year 2](/assets/img/PM.png)

### Prediction Model

The following is an extremely preliminary fit using a simple logit model on the data (sample size = 2495). Specification:
$$ swi = \alpha + \gamma year + \beta X + e $$
								
where $swi$ is a switch year indicator that equals 1 if switch year ≤ characteristic year, 0 otherwise. $X$ are explanatory variables including population, GRP per capita, and goverment expenditure on education.

(/assets/img/plot_popu.png)
(/assets/img/plot_grppc.png)

(/assets/img/plot_eduexp.png)
(/assets/img/plot_year.png)

(/assets/img/regression_table.html)
(/assets/img/3d_plot.html)