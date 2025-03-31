**### Rebecca Jones Project Reflection
**
## Brief Overview of the Project

Our climate forecasting project analysed climate projection data across the UK from 2006-2080. Six NETCDF datasets were used with the same dimensions across 66 grid points throughout the United Kingdom. The data contained identical climatological variables such as temperature, precipitation, and radiation, however they differ in their values. Our aims were to understand how climate variables would change over time, identify which variables showed the greatest changes between early and future decades, and compare machine learning and statistical models for predicting temperature time series. After performing some transformations on the data, we conducted extensive exploratory data analysis, visualising temperature changes by decade. We also explored the options of external datasets that could be used to enhance our predictive model, settling on a greenhouse gas emissions dataset from the Office for National Statistics. We implemented a number of different forecasting models, including Long Short Term Memory (LSTM), Linear Regression, Random Forest, and Support Vector Regression. 

## Personal Reflections on the Process

## What went well:

# Effective data exploration and Manipulation

A fellow team member and I took responsibility for the exploratory data analysis phase of the project. Our decision to proceed immediately with extensive EDA before jumping to modelling provided us with valuable insights into the structure of the data, the variables included, and climate trends within the data that ultimately shaped our project direction. I created a range of visualisations including decadal heat maps and linear regression analyses of all variables, which revealed critical insights into the data patterns that informed our later modelling choices.  

# Successful Use of the Six NetCDF Datasets

One of my key strengths was manipulating the complex multidimensional climate data. Initially, I was unfamiliar with how to work with the NetCDF file format, and learning to manipulate these complex multidimensional datasets using xarray was a challenge. However, I was able to successfully develop techniques to extract meaningful insights from the data, including calculating temporal means across the entire timescale, converting longitude values from the 0-360° range to the standard -180-180° range, and computing spatial averages for more effective mapping by region. I also gained valuable experience in transforming xarray data arrays into NumPy arrays for regression analysis. 

# Usage of the Cartopy Package

My visualisation work using Cartopy's Plate Carrée projection, which was completely new to me, successfully helped to communicate our findings. I created UK temperature maps showing warming patterns by decade using all six datasets, which clearly illustrated the spatial differences in temperature changes across regions. These visualisations helped us identify the consistent warming trend across all datasets that became the backbone of our project narrative, as well as recognise that temperature variables showed more consistent patterns than other variables such as precipitation rate, guiding our analytical focus. 

# Technical Infrastructure Implementation

Despite my limited experience with advanced GitHub features prior to this project, I successfully set up a functional repository structure that supported our collaborative workflow. I was able to set up a well-organised repository by creating clear folders for data, notebooks, and helper functions. The helper.py module I developed was particularly useful, simplifying the data loading procedure.

## Challenges and Learning Outcomes

# Environment Configuration Struggles

As part of the task of creating the collaborative GitHub environment, setting up the environment.yml file was much more difficult than I had anticipated. I encountered several challenges during this process, including conflicts between packages such as xarray and it's dependencies, as well as platform-specific differences that enabled the environment to work on my machine but fail on my teammates' machines and vice versa. Following some troubleshooting, I was able to finally create a stable environment that worked consistently across our team. This experience taught me the importance of tracking dependencies and systematically testing the environment on different systems during the early stages of the project. 

# Git Branching Strategy Issues

Another challenging part of the GitHub element of the project was the implementation of a Git branching workflow early in the project, and I made several mistakes during this process. For example, I accidentally pushed my own version of the exploratory data analysis to the main branch instead of creating sub-branches beforehand where my teammate and I could compare our EDA results before committing the final notebook. My teammate and I also encountered merge conflicts that were difficult to resolve when we first tried to combine our notebooks. These issues highlighted the importance of establishing clearer guidelines and understanding of the branching procedure from the beginning, and through trial and error we were eventually able to understand the purpose and details of the branching function. 

# External Data Integration Difficulties

Selecting an external data source to complement our climate datasets and combine with our predictive model was unexpectedly challenging and time-consuming. Whilst my teammates handled the technical integration of greenhouse gas emissions data with our climate datasets, I was partly responsible for researching and identifying appropriate candidate external data sources. This investigation was more complex than I originally anticipated as I struggled to determine what types of data would enhance our analysis and help to build a more meaningful, accurate model. I struggled with the broad range of analytical possibilities with their being such a vast range of data available, as well as the technical challenges for integration. I explored various government and research repositories, evaluating datasets based on their temporal coverage, spatial resolution, and potential relevance to our research questions. This process was difficult as many datasets had incompatible formats and coverage periods that did not align well with our climate projections. After choosing the GHG emissions dataset, I was unsure whether quarterly emissions data could be combined with our daily climate variables meaningfully, and without a clear understanding of how xarray handles datasets with different temporal resolutions, I couldn't confidently assess the technical feasibility of integration. While I eventually identified potential datasets for my team to consider, my limited understanding of advanced xarray operations made it difficult to predict which datasets would integrate most smoothly with our existing data. In future projects, I would spend more time researching how xarray can be used with other data formats and available integration approaches before beginning the data search process.

# Time Series and Spatial Visualisation Complexity

One of the most significant technical challenges I encountered was determining how to effectively visualise the large number of timestamps in our datasets. Each dataset contained 27,374 time points between 2006 and 2080, which created difficulties with visualisation approaches when trying to plot time series data. When I initially attempted to visualise all timestamps across the six datasets together, the result was an extremely cluttered and uninterpretable plot where trends were not able to be analysed due to the density of overlapping lines. I tested various approaches to visualising this data, including plotting all points on separate graphs for each dataset, creating annual aggregations to reduce the number of points, and splitting the analysis into "early" and "later" periods to highlight long-term changes. Eventually, I developed a complementary approach with my teammate - I focused on annual aggregations that preserved more temporal detail and deeper insights, while they created decadal visualisations that highlighted long-term trends. For spatial visualisations, rather than attempting to show all time points on maps, I created temporal means for an overall view of the data. This experience taught me valuable lessons about data reduction strategies and the importance of tailoring visualisations to our specific questions rather than trying to show everything at once. 

## Future Improvements

# Implementation of Helper Functions

During this project, I created a single helper function to load in the 6 datasets quickly, which was a great first step in modularising our code. In the future, I hope to be able to develop a more comprehensive set of helper functions to enhance efficiency and maintainability. By creating multiple targeted helper functions, I can accelerate repetitive tasks, reduce code duplication, and ensure more consistent data processing across our team's workflow. In future projects, I aim to improve my abilities in identifying opportunities for helper functions so that I can break down complex processes into smaller, reusable components that can be easily shared and used by all team members. This improvement would not only aid code readability, but also make our development process more flexible and efficient. I would also like to explore implementing automated testing for these helper functions to ensure I catch any potential issues in the early stages of the project.

# Improving Git Collaboration and Version Control

In future projects, I will improve the Git workflow to address the collaborative challenges we encountered. My main focus will be on establishing clear branching strategies from the very start of the project. To do this, I will immediately create dedicated feature branches for different work streams, such as separate branches for exploratory data analysis, data preprocessing, model development, and visualisation. I will ensure a more thorough review process so that no changes are directly pushed to the main branch without careful review and approval beforehand. Additionally, I hope to create documentation about the branching workflow, including guidelines for branch naming conventions, commit message standards, and merge procedures. By providing clear guidelines to all team members, I hope this will minimise merge conflicts and reduce the time spent resolving version control issues.

# Environment Configuration and Dependency Management

The challenges I faced when creating the 'climate-analysis' environment highlighted the importance of creating stable, reproducible environments. In subsequent projects, I will take a more systematic approach to managing project dependencies by creating a more detailed environment.yml file that specifies all package versions and accounts for potential cross-platform compatibility issues. I plan to implement a more thorough testing process, which includes creating the environment on multiple operating systems (Windows, macOS, Linux), and documenting specific version conflicts and their resolutions.

# Strategic External Data Integration

Finding and integrating external datasets proved to be one of the most challenging aspects of our project. In future work, I will develop a more methodical approach to external data selection and integration. This will involve conducting a thorough literature review to identify potentially relevant external datasets beforehand, and 
assessing dataset compatibility including temporal resolution and coverage and spatial granularity. I will also spend more time understanding the relationships between different types of climate-related datasets and develop a more sophisticated approach to handling a mix of temporal and spatial resolutions.

## Conclusion

While this project presented a number of technical challenges — particularly with environment configuration, Git branching, and handling large NetCDF datasets — overcoming these obstacles provided me with valuable learning experiences which can be brought into future projects using similar data formats. The successful aspects of the project, including the effective visualisations and well-organised repository structure, demonstrate that pushing myself beyond my comfort zone yielded significant growth in my environmental data science and collaboration skills.

This climate forecasting project has given me practical experience with the technical aspects of earth science data that are essential for my future aspirations. Despite the difficulties, I feel better equipped to handle complex data formats, manage collaborative workflows, and create reproducible research environments.




