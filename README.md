### Measuring the Impact of Amenities of Market Share and Revenue 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;In this project, we evaluate the ROI of offering meeting rooms for a Mountain View hotel by measuring the impact of hotel amenities on online reviews and ratings using linear and multinomial logistic regressions. 

-	Our goal is to identity one impactful (and statistically significant) amenity that Best Western Crest View does not currently offer and recommend, using breakeven analysis, whether offering the amenity makes economic sense. 
-	To do so, we measure the impact of different amenities (e.g. pool, gym, and meeting rooms) on a hotel’s average ratings and number of reviews.  
-	Then, using the model given in the Cornell paper as representative of the Mountain View market, we estimate the impact that increasing Crest View’s number of reviews—by offering the amenity—would  have on its market share (i.e. probability that a user purchases). We assume:
o	That Crest View’s 5% market share reflects customers who book through online travel agencies, such as Travelocity. 
o	That the list of amenities shown on a hotel’s TripAdvisor page is complete. In other words, hotels list all amenities offered on 
TripAdvisor. 

### Data Understanding 
We scrapped the following data from the 18 listed hotels in Mountain View on Sunday, February 2nd:
1.	Composite (i.e. average) Rating Score 
2.	Number of Reviews
3.	Total number of amenities listed and type (e.g. pool, gym)


### Data Preparation 
-	To regress amenities on rating score and number of reviews, each amenity was given its own column. Hotels with an amenity were given 1s and hotels without an amenity were given 0s in the amenity’s respective column. 
Modeling
-	First, a linear regression is used to predict the number of reviews using type of amenities offered. It is reasonable to assume that offering or not offering certain amenities might motivate guests to write reviews. Indeed, we observe that many reviews written center around service, quality, and/or presence of an amenity. Because we have more covariates (i.e. amenities) than observations, stepwise feature selection was employed to select the most important variables. 
-	Next, a multinomial logistic regression—since ratings are categorical—is used to predict ratings using type of amenities offered. 
 
### Impact of Amenities on Reviews 
 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The linear regression output above shows the impact of certain amenities (chosen using stepwise feature selection) on number of reviews. Of the amenities listed, meeting rooms is statistically significant at a 5% level and laundry service is statistically significant at 10% level.
Impact of Amenities on Ratings 
 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Above, we display the output of the multinomial logistic regression, including coefficients and p-values, which displays the impact that certain amenities have on the likelihood that a hotel received a certain rating. The coefficients represent the marginal impact of an amenity on the logit of outcome relative to the referent group, which we set as 3.5, the current compositive rating of Crest View. For example, adding a meeting room increases that chances that a hotel has a 4-star rating vs a 3.5-star rating. We note, however, that none of our coefficients is statistically significant. 

### Recommendation 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;We identify “meeting rooms” as an important amenity, given its impact on number of reviews. Crest View does not currently offer meeting rooms. 
 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;To evaluate the value of a meeting room at Crest view, we compare the benefit to the costs. To estimate the benefit, we measure how much the probability of purchase would change as we increase reviews through the introduction of meeting rooms. From our linear regression, we see that adding a meeting room would increase reviews by 322, on average, holding all else constant. This corresponds to a .805 change in the logit, or 5% additional market share for Crest View. 
Current market share	5%
Implied logit	-2.945
Change in Logit	.805
New Implied Logit	-2.14
New Market Share	10.5%
New customers gained	(.105-.05)*500,000=27,500
Increase in Market Share from offering “Meeting Rooms”
 
### Total Value of New Customers Gained
 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;If we compare the $12.5M in incremental value to the estimated $1M in costs (finding cost estimates for adding a meeting room to a hotel is extremely difficult so we took 1/22 of the overall price of constructing a hotel), we would recommend that Crest View offer meeting rooms in its hotel to increase market share and profitability. This is consistent with Crest View’s strategy to cater more to the business segment, having introduce a brand new business center in early spring 2019. If you read through Crest Views review, you will notice that a number of reviews mention Crest View’s business focused amenities—or lack of.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Admittedly, $12.5M seems like a very high number. While our method is sound, we point out a few limitations of our analysis that could contribute to a less than accurate final value. For one, we are only able to collect data on 18 hotels. Secondly, we use a representative model to measure the impact of reviews on market share—it is possible, and likely, that the mountain view market behaves very differently than the market studies in the Cornell paper.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Nevertheless, our analysis shows how one can connect an amenity, which lives at the bottom of the CRM framework, to profit, which sits at the top of the framework. To improve on this analysis, we would collect better data and train more sophisticated models. 


