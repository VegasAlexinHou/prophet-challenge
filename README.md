#Forecasting Net Prophet
###prophet-challenge
###mercado_libre
You’re a growth analyst at MercadoLibre. With over 200 million users, MercadoLibre is the most popular e-commerce site in Latin America. You've been tasked with analyzing the company's financial and user data in clever ways to make the company grow. So, you want to find out if the ability to predict search traffic can translate into the ability to successfully trade the stock.

The instructions for this Challenge are divided into four steps, as follows:

Step 1: Find unusual patterns in hourly Google search traffic

Step 2: Mine the search traffic data for seasonality

Step 3: Relate the search traffic to stock price patterns

Step 4: Create a time series model with Prophet

The following subsections detail these steps.


Install and import the required libraries and dependencies

Step 1: Find Unusual Patterns in Hourly Google Search Traffic
The data science manager asks if the Google search traffic for the company links to any financial events at the company. Or, does the search traffic data just present random noise? To answer this question, pick out any unusual patterns in the Google search data for the company, and connect them to the corporate financial events.

To do so, complete the following steps:

Read the search data into a DataFrame, and then slice the data to just the month of May 2020. (During this month, MercadoLibre released its quarterly financial results.) Visualize the results. Do any unusual patterns exist?

Calculate the total search traffic for the month, and then compare the value to the monthly median across all months. Did the Google search traffic increase during the month that MercadoLibre released its financial results?

Step 1: Read the search data into a DataFrame, and then slice the data to just the month of May 2020. (During this month, MercadoLibre released its quarterly financial results.) Visualize the results. Do any unusual patterns exist?

**Question:** Did the Google search traffic increase during the month that MercadoLibre released its financial results?

**Answer:** Yes, the search traffic for May 2020 is higher than the monthly median value across all months, indicating an increase in search traffic during May 2020 when the financial results were released. The comparison ratio of 1.0855 also confirms this increase.

Step 2: Mine the Search Traffic Data for Seasonality
Marketing realizes that they can use the hourly search data, too. If they can track and predict interest in the company and its platform for any time of day, they can focus their marketing efforts around the times that have the most traffic. This will get a greater return on investment (ROI) from their marketing budget.

To that end, you want to mine the search traffic data for predictable seasonal patterns of interest in the company. To do so, complete the following steps:

Group the hourly search data to plot the average traffic by the hour of day. Does the search traffic peak at a particular time of day or is it relatively consistent?

Group the hourly search data to plot the average traffic by the day of the week (for example, Monday vs. Friday). Does the search traffic get busiest on any particular day of the week?

Group the hourly search data to plot the average traffic by the week of the year. Does the search traffic tend to increase during the winter holiday period (weeks 40 through 52)?

Question: Are there any time based trends that you can see in the data?

Answer: More searches tend to happen as the typical "work day" progresses with more searches happening early in the week. More searches happen in the beginning of the year vs as the year progresses.

Step 3: Relate the Search Traffic to Stock Price Patterns
You mention your work on the search traffic data during a meeting with people in the finance group at the company. They want to know if any relationship between the search data and the company stock price exists, and they ask if you can investigate.

To do so, complete the following steps:

Read in and plot the stock price data. Concatenate the stock price data to the search data in a single DataFrame.

Market events emerged during the year of 2020 that many companies found difficult. But, after the initial shock to global financial markets, new customers and revenue increased for e-commerce platforms. Slice the data to just the first half of 2020 (2020-01 to 2020-06 in the DataFrame), and then plot the data. Do both time series indicate a common trend that’s consistent with this narrative?

Create a new column in the DataFrame named “Lagged Search Trends” that offsets, or shifts, the search traffic by one hour. Create two additional columns:

“Stock Volatility”, which holds an exponentially weighted four-hour rolling average of the company’s stock volatility

“Hourly Stock Return”, which holds the percent change of the company's stock price on an hourly basis

Review the time series correlation, and then answer the following question: Does a predictable relationship exist between the lagged search traffic and the stock volatility or between the lagged search traffic and the stock price returns?

Step 1: Read in and plot the stock price data. Concatenate the stock price data to the search data in a single DataFrame.

Step 2: Market events emerged during the year of 2020 that many companies found difficult. But, after the initial shock to global financial markets, new customers and revenue increased for e-commerce platforms. Slice the data to just the first half of 2020 (2020-01 to 2020-06 in the DataFrame), and then plot the data. Do both time series indicate a common trend that’s consistent with this narrative?

Answer the following question:
Question: Do both time series indicate a common trend that’s consistent with this narrative?

Answer: Yes. Market price rose in 2020 with what looks to be beginning in May, when the financial information was released. Market price appears to be trending upward.

Step 3: Create a new column in the DataFrame named “Lagged Search Trends” that offsets, or shifts, the search traffic by one hour. Create two additional columns:
“Stock Volatility”, which holds an exponentially weighted four-hour rolling average of the company’s stock volatility

“Hourly Stock Return”, which holds the percent change of the company's stock price on an hourly basis

Solution Note: Note how volatility spiked, and tended to stay high, during the first half of 2020. This is a common characteristic of volatility in stock returns worldwide: high volatility days tend to be followed by yet more high volatility days. When it rains, it pours.

Step 4: Review the time series correlation, and then answer the following question: Does a predictable relationship exist between the lagged search traffic and the stock volatility or between the lagged search traffic and the stock price returns?

Question: Does a predictable relationship exist between the lagged search traffic and the stock volatility or between the lagged search traffic and the stock price returns?

Answer: Based on the correlation values provided, it appears that there is a weak negative relationship between lagged search trends and stock volatility (-0.148938), and a very weak positive relationship between lagged search trends and hourly stock return (0.017929).

These correlation values suggest that there may be some very limited predictability between lagged search traffic and stock volatility or stock price returns, but the relationships are not strong. It is important to note that correlation does not imply causation, so further analysis would be needed to determine if there is a truly predictable relationship between these variables.

Step 4: Create a Time Series Model with Prophet
Now, you need to produce a time series model that analyzes and forecasts patterns in the hourly search data. To do so, complete the following steps:

Set up the Google search data for a Prophet forecasting model.

After estimating the model, plot the forecast. How's the near-term forecast for the popularity of MercadoLibre?

Plot the individual time series components of the model to answer the following questions:

What time of day exhibits the greatest popularity?

Which day of the week gets the most search traffic?

What's the lowest point for search traffic in the calendar year?

Step 1: Set up the Google search data for a Prophet forecasting model.

 After estimating the model, plot the forecast. How's the near-term forecast for the popularity of MercadoLibre?
 
 Step 3: Plot the individual time series components of the model to answer the following questions:
What time of day exhibits the greatest popularity?

Which day of the week gets the most search traffic?

What's the lowest point for search traffic in the calendar year?

Solutions Note: yhat represents the most likely (average) forecast, whereas yhat_lower and yhat_upper represents the worst and best case prediction (based on what are known as 95% confidence intervals).

Question: What time of day exhibits the greatest popularity?

Answer: Evening hours have the most visits peaking at mindnight

Question: Which day of week gets the most search traffic?

Answer: Tuesday

Question: What's the lowest point for search traffic in the calendar year?

Answer: Late October just before November.
