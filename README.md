# 
The Heston model is a mathematical model to predict how option (which is like a contract that gives buyers the right, but not the obligation to buy / sell ,depending wheter its call or put option, an underlying asset by an expiration date at a predecided price called strike price) prices might change over time.
Well that looks intimidating isnt it !?
Heston options pricing model is actually an improvement over a model called Black-Scholes model.The key difference is that the former takes into account that volatility isnt constant, which was a fundamental assumption of Black-Scholes model and its limitation as well.
Heston Model takes volatility to be a stochastic process ( which describes system that evolve over time in a way thats atleast partly random)
Other models that take volatility to be stochastic are SABR model, Chen model, GARCH model, and Stochastic-local mix models.
Now we will move on to describe the model , atleast the basic layout.
In the Heston model, two functions are considered:
● Brownian motion, representing the underlying asset price
● The variance (represents volatility)
Here is the full Heston model formula:
The first equation explains the stock price dynamics by 2 parts, representing expected returns and random fluctuations. The second consists of 2 parts agian representing mean reversion and random shock absorbing term, We cannot discuss these in detail here.
By solving them numerically, we can simulate potential price paths for the underlying asset and its changing volatility. This approach enables more accurate option valuation compared to models that assume constant volatility.
The key limitations of Hestons Model are that it is not accurate for short term options ,as it fails to capture the high implied volatility. Also it is fairly difficult for a regular trader .

AS we proceed through the code, we firstly fetched the data for NVDA for 10 years;
Forth which we calculated the return using divion from previous day price. We then calculated the parameters using method of moments . To improve the model we can utlise other methods like MLE or finite differences method.
Now its a problems of numerical optimization with a given set of constraints. Lastly we tried to compute the baseline comparison over Black Scholes model.
