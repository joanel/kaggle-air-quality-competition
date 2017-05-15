# kaggle-air-quality-competition
# second effort at GA project

serious issues with data in earlier work has left me regrouping. 

# some discussion to consider:  "Without revealing any secret I can say that, indeed, there is a trend, and mortality rates 
# for the causes we look at here are decreasing: see general UK cancer and CVD mortality statistics. This is driven largely 
# by factors other than the air quality and temperature that is provided in the competition data: advances of health care 
# and access to it, perhaps healthier eating habits, decreased smoking, etc. Still, it is known that air pollution has an 
# impact on public health and can cause premature deaths."

# So,  one approach: try to model the general trend using mortality rates  data in the training dataset first. 

# Then, controlling for or removing any trend from the training and test datasets could be a preliminary/"preprocessing"
# step before actually training regression models to predict the impact of air quality.
