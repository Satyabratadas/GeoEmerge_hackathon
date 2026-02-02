# Bias and Uncertainty in Reported Mosquito Habitat Data

## Inspiration  
Mosquito-borne diseases remain a major public health concern, yet predicting mosquito habitat risk depends heavily on the quality and completeness of environmental data. While community science platforms like GLOBE Observer collect large volumes of mosquito observations, we were inspired to explore whether this data is structured in a way that actually supports reliable prediction. Our project was motivated by a simple question: Are we collecting the right data, in the right way, to build effective mosquito habitat models?

## What it does  
This project analyzes community-reported Mosquito Habitat Mapper and Land Cover data to evaluate how data completeness, user behavior, and sampling bias affect the ability to predict mosquito habitat formation. Rather than focusing solely on mosquito presence, we examine whether the necessary environmental context—such as standing water, vegetation, and surface conditions—is consistently collected alongside mosquito observations. Our analysis identifies gaps in data collection that limit predictive modeling and highlights opportunities to improve future data quality.

## How we built it. 
We retrieved Mosquito Habitat Mapper and Land Cover observations using the GLOBE API and processed them using Python, Pandas, and GeoPandas. After filtering data spatially to Florida, we performed exploratory data analysis to assess missingness, contributor behavior, spatial clustering, and variable availability. We merged datasets by site ID where possible and visualized observations using geospatial mapping tools to understand coverage patterns and outliers. Our workflow focused on diagnosing structural limitations in the data rather than fitting a final predictive model.

## Challenges we ran into  
A major challenge was that a large majority of mosquito observations did not have corresponding land cover data at the same site. This significantly reduced the number of usable samples for modeling and introduced bias toward certain users and locations. Additionally, we observed that a small number of contributors accounted for a disproportionate share of extreme larva counts, raising concerns about outlier influence and reporting consistency. Working with incomplete, unevenly sampled community data required careful interpretation to avoid misleading conclusions.

## Accomplishments that we're proud of  
We identified that approximately 87.64% of mosquito observations lacked accompanying land cover data, revealing a critical limitation in the dataset’s predictive utility. We also uncovered evidence of contributor-driven bias, where a small number of users disproportionately influenced extreme observations. Most importantly, we reframed the problem from “predicting mosquito habitats” to optimizing data collection itself, demonstrating how improvements in reporting structure could dramatically enhance future modeling efforts.

## What we learned  
This project reinforced that data quantity alone does not guarantee data usefulness. Predictive modeling requires both outcome variables and explanatory environmental features, and missing context can severely limit model performance. We also learned that community science data is shaped by human behavior, effort, and incentives, making bias detection and mitigation essential. Designing better data collection systems is just as important as building better models.

## What's next for Bias and Uncertainty in Reported Mosquito Habitat Data  
Future work would focus on developing strategies to reduce sampling bias and improve data completeness, such as encouraging or requiring joint submission of mosquito and land cover observations, weighting observations by contributor behavior, or integrating external environmental datasets like rainfall or temperature. With more consistent environmental data, this project could evolve into a robust mosquito habitat risk modeling framework that better supports public health decision-making.
