# FUTURE_ML_01
Future Interns Internship

During cleaning, it was noted that the dataset included a period of high volatility (2013–2017), including a significant price crash in late 2014. This informed the decision to use a Linear Regression model as a baseline for trend analysis.



# Time Series Analysis
To better understand the model's error margins, a Seasonal Decomposition was performed on the dcoilwtico price data. This process breaks the data into four distinct components:

Observed: The actual raw price data including all market noise and volatility.

Trend: The long-term progression of the price. This confirms that while the general movement was downward, it was not a linear "straight line" drop, but a staggered decline. A company that relies on oil as a raw material can plan for lower procurement costs in their long-term annual budget

Seasonal: This revealed recurring cycles within the data. In the seasonal plot in our data, we can see monthly fluctuations that a standard linear model would typically miss.

Residual (Resid): The "leftover" noise after removing trend and seasonality. Large clusters in the residual plot indicate specific external events (like geopolitical shocks) that cannot be predicted by time alone. The analysis shows that external shocks frequently knock prices off the trend line. Businesses should maintain a "contingency fund" to handle the $13.98 (RMSE) potential price swings that the linear trend cannot predict.

Seasonal Insights
The Seasonal Subseries Plot provides a deeper dive into monthly performance:

Red Lines: Represent the mean price for each month across the entire dataset.

Black Lines: Show the year-over-year variation for that specific month.

Observation: We can see that prices typically peaked around May and June, while reaching their lowest average points in November and December. This suggests a "Heating Oil" seasonality effect in the market. Businesses can use this to "buy ahead" during low-price months.





# Model Evaluation and Error analysis:
R-Squared (0.7024): This is actually quite high. "Date" explains about 70% of the variance in oil prices. However, looking at the graph, this number is a bit "optimistic" because it's just capturing the massive downward crash in 2014-2015.

Mean Absolute Error ($12.17): This is our "reality check." On average, the model is wrong by over $12. For a commodity where a $2 jump is a big deal, a $12 error means the model isn't ready for actual trading, it’s only good for seeing the general multi-year trend.

RMSE ($13.98): Since this is higher than the MAE, it confirms we have some "outliers" or specific periods where the model missed by a huge margin (like the price spike in 2014 or the bottom of the crash in 2016)
