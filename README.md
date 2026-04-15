# Workflows for undertaking the terrestrial Red List index of ecosystems (RLIe) assessment

## National Biodiversity Assessment - South Africa

#### South African National Biodiversity Institute (SANBI)

April 2025

**Summary**

This GitHub repository contains the analytical workflow for the Red List Index of Ecosystems (RLIe), a [Global Biodiversity Framework (GBF)](https://www.cbd.int/gbf) headline indicator under Goal A, applied to South Africa's terrestrial ecosystem types and the summary results of the RLIe indicator. The RLIe tracks genuine changes in ecosystem status over time and draws exclusively on outcomes from the Red List of Ecosystems (RLE) assessments, itself a GBF headline indicator.

**Data inputs**

The workflow integrates RLE assessment outcomes derived from multi-temporal land cover data across four time points: 2014, 2018, 2020, and 2022, which together form the baseline for monitoring changes in ecosystem status.

| Data | year | Description |
|--------------------|---------------------|------------------------------------------|
| National vegetation map | 2024 | The vegetation map is a model of the historical extent of the vegetation types prior to the year 1750 |
| National land cover | 2014, 2018, 2020 and 2022 | National Land Cover dataset comprising classified raster pixels representing broad land cover classes, used to derive spatially explicit estimates of ecosystem extent and temporal change for RLE assessments |

**Scope of the 2025 assessment**

The 2025 iteration of terrestrial ecosystem assessments considered a wide range of pressures to strengthen the credibility and confidence of both the assessments and the listed ecosystems (see the [terrestrial RLE repo](SANBI-TER-ECO/RLE_terr) for details). However, only ecosystems threatened by anthropogenic land use were included in the RLIe, as their spatial changes can be independently validated, a prerequisite of the indicator, which requires demonstrable real-world change in ecosystem condition to trigger a shift in status.

**Backcasting rules**

To backcast the risk of ecosystem collapse attributable to anthropogenic change, the following rules were applied to adjust threat status for qualifying ecosystem types:

-   **Retain 2014 spatial status** — If an ecosystem type was classified as threatened under any spatial sub-criterion (A2b, A3, B1(a)i, B2(a)ii, or a combination thereof) in the 2014 assessment, and was subsequently reassessed under the 2024 core spatial assessment, then the 2014 RLE status is retained as the final status, regardless of the category assigned in 2024.

-   **No change** — Where the threat status is consistent between the 2014 and 2024 assessments, the classification is retained without change

-   **2024 takes precedence for mixed-criteria outcomes** — If the threat status differs between assessments and classification is based on a combination of spatial and functional criteria, the 2024 RLE assessment takes precedence.

> ## Note
>
> - The backcasting process described above was also applied to the 2018 and 2020 assessment periods.  
> - For the 2022 land cover dataset, assessments were conducted in 2024; the assessment period is therefore referred to as 2024 throughout this workflow.  
> - The functions used to compute the RLIe scores were sourced from the [`rle_indices`](https://github.com/red-list-ecosystem/rle_indices) repository and adapted to calculate RLIe scores and their associated uncertainty across the four assessment periods (2014, 2018, 2020, and 2024) at the biome level.


**Calculation of the Index**

The RLIe enables the calculation of scores for ecosystem types across multiple levels, including biomes, functional groups, global types, and sub-global types. In this national reporting context, RLIe scores were calculated at the biome level

The RLIe is expressed by this mathematical equation:

$$
RLIe = 1- \frac{\sum_{i = 1}^{n} W_{C_{i,j}}}{W_{{CO}^n}}
$$


Where $W_{C_{i,j}}$ represents the risk category rank for ecosystem $i$ in year $t$, with the following values:

-   Collapsed = 5

-   Critically Endangered = 4

-   Endangered = 3

-   Vulnerable = 2

-   Near Threatened = 1

-   Least Concern = 0

$W_{CO}$ is the maximum category rank (Collapsed=5), and $n$ is the total number of ecosystem types excluding Data Deficient or Not Evaluated ecosystem types.

**The technical workflow and summary results are published as a website and are accessible [here](https://sanbi-ter-eco.github.io/RLIe_terr/).**
