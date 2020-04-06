---
layout: default
---

## Projects 
[1] **[Where Are All The Women in Modern Art?](https://towardsdatascience.com/where-are-all-the-women-in-modern-art-7c5fd08ea1cd)**  
I wrangled data from an open data set released by New York's Museum of Modern Art, and conducted exploratory data analysis. My analysis was published by Towards Data Science, an industry publication with 10+ million monthly views. Repo: https://github.com/elliotgunn/MoMA-data-analysis

[2] **[Predictor App: Toronto Subway Delays](https://toronto-subway-delay.herokuapp.com/)**  
I assembled open data on subway delay from the City of Toronto and created a Plotly Dash web app, deployed on Heroku, that uses a Random Forest model to predict TTC train delays. Repo: https://github.com/elliotgunn/toronto-subway-delay

[3] **[Flask API: AirBnB Optimal Price](https://github.com/elliotgunn/airbnb-optimal-price)**  
Created an API for a full-stack web app that uses historical booking data to predict the optimal price for an AirBnB in Berlin. The Flask API was deployed on Heroku, processed incoming JSON data, generated a prediction, and then returned it as JSON data. The Flask routes served as the API endpoints.

[4] **[Chloropleth: Forecasting Deforestation Trends](https://github.com/elliotgunn/deforestation)**  
I feature engineered and built a time-series model to forecast global deforestation trends through 2025. 

[5] **[Using Machine Learning to Tackle Arms Proliferation In Russian Trade Data](https://towardsdatascience.com/using-machine-learning-to-tackle-arms-proliferation-in-russian-trade-data-e457f44002c0?source=friends_link&sk=b99118751e39eb7edd42a318c40854ee)**  
This was part of a data science internship at [C4ADS](https://c4ads.org/). The goal was to identify companies involved in the illicit international weapons trade using a ML model on 65 million row, 170GB trade dataset. I documented our research, process, tech stack, and findings in a piece published at [Towards Data Science](https://towardsdatascience.com/using-machine-learning-to-tackle-arms-proliferation-in-russian-trade-data-e457f44002c0?source=friends_link&sk=b99118751e39eb7edd42a318c40854ee). We successfully trained a GradientBoostingClassifier in Python to identify 50 illegal arms exporters. Tech stack: AWS (S3, Sagemaker, RDS, Glue); Python; Dask; PySpark; Pandas

[6] **[NYC Taxi Trips Model Deployment](https://github.com/elliotgunn/nyc-taxi-trips)** _Ongoing_  
The goal: an end-to-end machine learning model of ~30 million taxi trips to predict tip amounts, deployed to both Heroku and AWS. Feature engineered data in Python, used CI/CD, testing, and built data pipelines to productionise the ML model.

## Notes
[1] [On Breiman's 2001 paper (data vs algorithmic modelling)](./on-breiman-statistical-modeling.md)

[2] [On a data science workflow in Amazon Web Services](./on-aws-workflow.md)

