# UCB-MLAI-Mod5
UCB ML &amp; AI Module 5

Files:


Data:
This data is from the UCI Machine Learning Repository and was collected via a survey on Amazon Mechanical Turk. The survey describes different driving scenarios, including the destination, current time, weather, and passenger, and then asks people whether they will accept the coupon if they are the driver. There are three possible answers people can choose from:

“Right away”
“Later, before the coupon expires”
“No, I do not want the coupon”
The first two responses are labeled as “Y = 1,” and the third is labeled as “Y = 0.” There are five different types of coupons: Less expensive restaurants (under $20), coffee houses, carryout and takeaway, bars, and more expensive restaurants ($20–$50).

Analysis:
The independent study that was performed was done on 'coupon' - 'Coffee House'.  We took a look at the relevant columns for coffee ('destination','temperature','time','expiration','gender','age','income','CoffeeHouse','occupation') to see where the coupon conversion rates were the hightest.  Looking at the seaborn plots, we made the following conclusions:
- gender: male/female does not matter
- age: between 0-36, there is a decline in coupon usage as drivers get older. There is a slight increase between 36-46, but then it declines again.
- income: in general, the data slowly declines as income becomes higher. Between 62.5 - 87.5k there is a significant dip, but usage once again climbs above 87.5k
- CoffeeHouse: those that drink more than 1 cup/mo are about 65% likely to use the coupon.
- time: 10AM is peak time to offer a coupon
- temp: temp 80 results in a higher success rate.
- destination: if someone has no urgent place to go they are the most likely to use the coupon, followed by Work, then Home.
- expiration: 1 day expiration has a much higher acceptance rate than 2h.
- occupation: those in healthcare, building maintenance, students, and transportation maintenance are the most likely to use the coupon. Least are legal, social services, production, and sales.upation

We then created a couple of combined plots to investigate the data further.

Problem 1: we see that 10AM has the highest conversion rate for Coffee House coupons. Let's take a look at where everyone seems to be going at each time. Should we create "Work" and "Home" coupons?
Answer 1: We can see that at the most popular time of 10AM people have no urgent place to go.  The second most popular time for coffee coupon usage is 2PM.  Again, at 2PM we find that people have no urgent place to go.  The only time that people are on their way to work is 7AM, and the only times that people are on their way home are 6PM and 10PM.  From this, we can surmise that we don't need to target drivers going to or from work or home because the acceptance rates are less for those times.

Problem 2: We see a big dropoff at income level 75k - 87.5k.  Let's see if Coffee House frequency is related to this drop-off.
Answer 2: If the hypothesis was correct, we should see a spike in 'never' and 'less1' columns for 75k - 87.5k. We can see that this was NOT the case so there is no correlation.

Conclusion:

Dataset
The dataset does not offer a lot of statistical analysis because most of the columns are in "bins" (i.e. non-numeric). So, our plots are mostly bar plots.
The best use of this data is actually to figure out which coupon to offer each driver, but since the assignment is limited to investigate a single type of coupon, we don't do this exercise.

Coffee House data
Strong indicators that a coupon will be converted:
- CoffeeHouse frequency > 1/mo
- driver has no urgent place to go
- coupon last 1 day
- temp is 80 deg
-the time is between 10AM and 2PM

If we targeted this customer, the converison rate would be 79%.
