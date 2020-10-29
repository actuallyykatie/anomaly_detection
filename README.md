# Anomaly Detection

## project description
Conducted as a part of test task for VK in May, 2019.  

**Task:** 
1. Reproduce the ad impressions plot;  
2. Find the reason for the increase of advertising impressions and explain what happened;  
3. \*Suggest a way that would help to automatically detect abnormal changes in metrics on advertising statistics charts.  

## short summary

### task 2

> Find the reason for the increase of advertising impressions and explain what happened


There are several main hypotheses & conclusions:

1. Most likely, no errors occurred during the data collection stage. There are very few duplicates, and the overall picture does not change when they are removed. Here the anomaly is observable only for one campaign of a particular agency.
2. Clickbait did not take place as the number of impressions increased, but not the clicks. More precisely, there are almost no clicks at all.
3. The only option that is remained: incorrect advertising settings. There are quite a lot of impressions – it means that the advertisement was shown to some users. But there are almost no clicks, therefore, users are not interested in this ad. The number of reports is low as well, and everything should be fine with the ad text itself (+ they are also being moderated). The payment type is CPC, i.e. per click, not impressions, so the client himself did not suffer that much c:


In order to investigate the anomaly in more detail, it would be nice to examine the target settings, the place where the ads were displayed (feed / explore / other) and, possibly, on the ads themselves. And users who saw the ad – were they real?

### task 3

> Suggest a way that would help to automatically detect abnormal changes in metrics on advertising statistics charts.  

One of the possible and simple ways: calculate the moving average in order to smooth the trend, build confidence intervals, and if the value goes beyond it, consider it as anomaly. In general, this method is based on the assumption that the latter value depends on the mean  n previous observations. 

In this section, I implemented the moving average, moving median and exponential moving average functions, that analyse the data for the specified period, and if it is out of the general trend, print that there is a problem. Then I compared the methods and showcased how they work depending on the resampling rule, window size and confidence intervals parameters.