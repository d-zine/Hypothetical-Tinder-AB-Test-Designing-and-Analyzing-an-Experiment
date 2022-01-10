<h2 align="center"> Hypothetical Tinder A/B Test: Designing and Analyzing an Experiment</h2>

<b>Initial Hypothesis</b>: Offering a one-week free trial on the Tinder Plus Subscription will improve overall revenue. Tinder Plus is a big source of revenue for Tinder.

Tinder Plus is a subscription worth $5 / month that rewinds, removes ads, and gives you a passport to travel on the app.

<i>Control Group Experience</i>: On the app, a pop-up will ask users who use the free service to sign up and pay for Tinder Plus upfront to gain extra features.

<i>Treatment Group Experience</i>: On the app, a pop-up will tell users who use the free service they can sign up for Tinder Plus for free for one week to try the additional features. After the free trial, users can choose to cancel. The trial will automatically convert to the paid subscription if no action is taken.

<b>Evaluation Metrics</b>

Short term Metric: Conversion Rate (calculated after the free trial ends)

Conversion rate=# of subscribers/# served the ad

Long Term Metrics: Retention rate or 12-month Customer value

CLV = $5/month x Number of Subscribers x Avg. Subscriber Lifetime in months

Because Tinder Plus is subscription and the fee is the same ($5), we can also just look at number of user signups and retention to measure CLV. 

Treatment users who enroll in the free trial but then do not continue with the paid subscription do not count as Subscribers because they do not generate any revenue. 

Our overall objective is to maximize user revenue, as measured by CLV. Since CLV is a long-term metric, we can use conversion rate as a short-term predictor of CLV, and incorporate projections and measurements of subscriber retention in the short- to medium-term.

<b>Complementary Data Analysis</b>

Let’s track/evaluate the uses who are served the ad and do not sign up for Tinder Plus. 

Specifically, this population includes 1) users that see pop up for the free trial, and 2) users that see the pop up to pay upfront AND still decide not to sign up for Tinder Plus.

We want to examine if 1) these users go on to upgrade to Tinder Plus later, 2) there is no effect, or 3) they abandon Tinder at higher rates.

To track users that see and do not sign up for the free trial, we can look at revenue/user for those who don’t sign up over the next month.

<b>Confidence Interval</b>

<i>Hypothesis Test Confidence level</i>: I would set a 95% confidence interval, which is the interval we construct around our sample mean to cover the true value of the population 95% of the time. This implies that 5% of the time we will incorrectly conclude that there is a difference when there is none, which is a Type I error. 

<b>Hypothesis Testing</b>

<i>The Null hypothesis is:</i>

There is no difference in CLV between users who must pay for Tinder Plus upfront and users that have a one-week free trial.

<i>The Alternative Hypothesis is: </i>

There is an increase in the CLV for users offered a one-week free trial v. paying upfront.

This is a one-sided test since we only care that the alternative hypothesis outperforms the null hypothesis. If the Treatment results in statistically-significantly less revenue than the Control group, we still consider that a failure.

We’re observing a binomial distribution because for any individual, the two outcomes are success and failure. With enough samples it can by approximated by a normal distribution.

<b>Compare two samples</b>

Power has an inverse tradeoff with size. The Smaller change you want to detect means more samples are needed.  Assume Statistical Power=0.80, the probability of correctly rejecting the null hypothesis when it is false (equivalent to 1 minus Type II error). 

<b>How many samples are needed need to get a practically significant result?</b>

Assuming Sensitivity = 10%, 1% Conversion Rate, 1000 Unique Visitors, one week, use website below to calculate minimum sample size per test variation:
https://abtestguide.com/abtestsize/

<p align="center">
<img src="images/Sample Size.JPG" width=825>
</p>
 
<b>Sample size</b>: 260,000 users (130,000 in control and 130,000 in treatment). Select randomized user IDs of 20-30 year old’s from a major metropolitan city such as Chicago, using stratified random sampling  to select 50/50 males and females and 50/50 Apple and Android. Remove any bots based on user agent/IP address prior to the experiment. This sample size should mitigate risk that the test is underpowered. We will focus on testing the treatment effect on the entire test sample. However, should any of the subgroup test results (based on gender or mobile platform) differ from the overall test result, we will run a retest focusing only on the subgroup of interest.

<b>Duration</b>: I would deploy this test Dec 4th, Saturday 6pm, and run it for a week to prevent risk of the day of the week effect. We should also be aware of concurrent tests going on. We can slowly ramp up the treatment and control sample sizes to make sure there aren’t problems with the test.

After the experiment, we can analyze results with a one-sided t-test. 

<b>Other Analysis</b>

We can also do a sensitivity analysis, because our ultimate long-term objective is to know which ad version (treatment or control) will result in more paying subscribers after 12 months. We cannot know that until a year after the test, and we cannot wait one year to decide whether the test was successful.  So, we evaluate the short-term results: we know how many paying subscribers we obtained from the Treatment group, and how many from the Control group. We can now make projections of the outcome after 12 months based on different potential retention scenarios. Based on low, medium, high retention scenarios, we can observe if the treatment usually wins or if it’s too hard to tell.

We can also use cohort analysis to examine user retention. Since we only have a week’s worth of data, we can look at how prior cohorts of newly acquired subscribers behaved in the past during their first year as subscribers, and calculate their retention rates over time. We can produce a retention curve for Tinder Plus subscribers, a great baseline for Control group retention over time. 

For the Treatment group, their retention rate over time may differ, since these users were acquired via a free trial. We should check if Tinder has offered a free trial in the past and see what the subscriber retention rates were for those prior experiments to use as a baseline for Treatment group retention. If that data is unavailable, we can use cohort analysis to identify actions from previous cohorts of acquired subscribers that are predictive of either churn or retention. Logging in a certain number of days in a row might be an indicator of higher retention and less churn.  Using this as a proxy, we can evaluate after only a few weeks whether Treatment group subscribers are behaving more similarly to subscribers that are likely to churn or that have higher retention.

This will help us conclude if offering a one-week free trial of the Tinder Plus Subscription vs. paying upfront will improve overall revenue.
