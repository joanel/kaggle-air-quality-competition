kaggle-air-quality-competition
second effort at GA project

serious issues with data in earlier work has left me regrouping. 

some discussion to consider:  "Without revealing any secret I can say that, indeed, there is a trend, and mortality rates 
for the causes we look at here are decreasing: see general UK cancer and CVD mortality statistics. This is driven largely 
by factors other than the air quality and temperature that is provided in the competition data: advances of health care 
and access to it, perhaps healthier eating habits, decreased smoking, etc. Still, it is known that air pollution has an 
impact on public health and can cause premature deaths."

So,  one approach: try to model the general trend using mortality rates  data in the training dataset first. 

Then, controlling for or removing any trend from the training and test datasets could be a preliminary/"preprocessing"
step before actually training regression models to predict the impact of air quality.

------

One issue that came up: the test set IS different than the train set. Not much time to consider this. HMM.

Spending time considering the difference between 'competitive data science' in the form of these kaggles,
and what I've been trained to do. That there's been techniques developed as work-arounds to score high on a 
competitions is --- bracing.

______

Another issue, without looking up how to model in meteorology, is choosing a model. I'm just not happy about using linear
regression, here, though an effort with least squares was reasonable: least squares is a treatment that allows the correlated
nature of this data to be accounted for.

A polynomial model is beyond the scope of what we've been doing in class, but something I will need to do in the 'real world'
so I'm hoping I can get something up, if only to compare.

A scatterplot made this 'u' shape (didn't keep) and that kind of curve just SAYS 'polynomial'. There's some discussion of
'XGBOOST' that I didn't have time to follow up on, learn about, but I DID learn that it does F-score comparison, and a F
score indicates that day-of-year and temperature, and the highly-correlated days-since-1-Jan-2006 (first day of data storage
which I would discard/not use) are the only variables reasonable to model.

Huh!!!!!!!

Most dangerously, the 'region' didn't make it into the model(s) -- and this can be dangerous, as the slope of the regression
line aggregating all the regions is nearly flat -- and NEGATIVE! Regressions lines region-by-region are all positive slopes when regressed by pollution.

Likely cause: one of the world's largest cities is one of the regions, and is an anomaly: very high (!!) pollution, but surprisingly low mortality: I expect if we could inspect the demographics, we'd find city dwellers to be younger/less exposed.


