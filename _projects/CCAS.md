---
layout: post
title: CCAS in China
date: 2023-05-20
description: "The adoption of centralized student choice and assignment systems in China"
img: assets/img/Comb1.png
importance: 1
category: Work

---

<object data="{{ site.url }}{{ site.baseurl }}/assets/pdf/CCAS_China_230812.pdf" width="800" height="1000" type="application/pdf"></object>



Advisor: [Christopher Neilson](https://christopherneilson.github.io/)


<!-- ## Graphs on the Evolution of CCAS in China

A Centralized Choice and Assignment System (CCAS) at an education level is defined by the simultaneous existence of educational institutions whose enrollment is at least partially determined by an external agency or platform, applicants who submit a list of their preferences to the agency, and the agency then giving the applicants a single offer, using certain criteria and allocation rules. Neilson (2019) documents the rise of CCAS in primary, secondary and tertiary education markets worldwide, and increasing research is being conducted on characteristics of existing CCAS (e.g., time of establishment, form of preference list, assignment mechanisms) and how they can be designed to facilitate education equity (see Akbarpour et al. (2022), Arteaga et al. (2022), Kapor, Neilson, & Zimmerman (2020)).

This project started as a sub-project of "Worldwide CCAS," focusing on [China's 135 cities whose population exceeded 1 million in 2020](https://www.citypopulation.de/en/china/cities/). I collected a cross-section data set documenting CCAS characteristics in primary and secondary education in these cities primarily from reading 2022's policy documents by local bureaus of education. Variables include: Existence of a CCAS, Participating institutions, List length, Website to apply, Implementation year of a CCAS, Priority groups, and Mechanisms (Deferred Acceptance, Boston, Serial Dictatorship, etc.)

I then put together a panel data set of the 135 cities, 2003-2022, using the above and National Bureau of Statistics's China City Statistical Yearbook, which has a rich set of city-level socio-economic indices. Variables on city characteristics are: City name, CCAS switch year, Characteristic year, Household registered population year-end, Gross Regional Product, Per capita GRP, GRP Growth Rate (%), Expenditure on education (10 000 yuan), Number of regular secondary Schools, Regular Primary Schools, and number of students in colleges, secondary schools, vocational secondary schools, and elementary schools.

### Descriptive Statistics

#### Stock Graphs

<div style="text-align: center; margin: 16px;">
Number and percentage of city-level CCAS in primary, middle, and high school admission (2003-2022) among 129 cities whose 2020 population exceeds 1 million
</div>

![Number and percentage of city-level CCAS in primary, middle, and high school admission (2003-2022) among 129 cities whose 2020 population exceeds 1 million](/assets/img/Comb1.png) -->

## Additional Graphs
---
### Descriptive

Below is an interactive graph of the age of each city's high school CCAS in 2020. <!-- I plan to develop this into a graph containing information from 2003 to 2022, and each year is a layer the user can select to display or hide. This would be a good visualization of the first movers (the cities with darker shades) and the dynamic spread over time. It will be easy given that I've already visualized 2020's data. I will only need a bit more time to learn addTiles(). -->

The biggest cities in China, Beijing, Shanghai, Shenzhen, and the south-east coastal cities were pioneers in implementing a CCAS for high school admissions.

<iframe src="/assets/img/Agein2020.html"></iframe>

<!-- #### Flow Graphs

![Number of New City-Level CCAS for High School Admission/Year](/assets/img/H_flow.png)

![Number of New City-Level CCAS for Primary and Middle School Admission/Year](/assets/img/PM_flow.png) -->

Below are maps showing the establishment years of CCAS for all investigated cities.

![High School CCAS Establishment Year](/assets/img/H.png)

![Primary and Middle School CCAS Establishment Year](/assets/img/PM.png)

### Prediction Model

A simple logit prediction model:

$$ swi = \alpha + \gamma year + \beta X + e $$
								
where $$swi$$ is a switch year indicator that equals 1 if switch year $$\le$$ year in which a city characteristic was recoreded, 0 otherwise. $$X$$ are explanatory variables including population, GRP per capita, and government expenditure on education.

{::comment}
<table>
  <tr>
    <td>
      <img src="/assets/img/plot_popu.png" alt="Plot 1">
    </td>
    <td>
      <img src="/assets/img/plot_grppc.png" alt="Plot 2">
    </td>
  </tr>
  <tr>
    <td>
      <img src="/assets/img/plot_eduexp.png" alt="Plot 3">
    </td>
    <td>
      <img src="/assets/img/plot_year.png" alt="Plot 4">
    </td>
  </tr>
</table>
{:/comment}

Estimated coefficients are extremely close to 0, which is expected due to the small sample size (2495) and the limited availability of control variables. To construct a valid prediction model, we look forward to exploiting a <a href="https://www.ccas-project.org/">world-wide CCAS</a> data set that is currently being collected.

<!--
<iframe src="/assets/img/regression_table.html"></iframe> -->

