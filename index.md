# Machine Learning in Finance

## Overview

Our main objective in this short course is to familiarize ourselves with the first two principles of successful machine learning projects

* Problem identification: what problem is of sufficient economic value to merit attention, and is it one where data is likely to help?
* Data science over data mining: it is essential to understand the nature of the problem, what one needs to predict and what variables are most likely to be relevant. Building a machine learning model over the right analytical framework is essential to success.

The machine learning space is far to wide to cover in a short series of lectures. There is no attempt to represent fairly the various techniques used in machine learning in finance, or even drill down deep into one particular technique. Instead, in this course we will  review some industry applications of machine learnings from the practitioner's viewpoint. We will use these examples to illustrate some of the common pitfalls found in machine learning applications. 

There is only one way to learn machine learning, and that is to play with data. We will provide some datasets for that purpose, students are encouraged to select one and come up with something to say about the data. For those more theoretically inclined or not yet handy with computer programming, an alternative option is to find a paper relevant to the course and prepare a short summary breaking down the work of the author(s) along the lines described in the present course. The last session will be dedicated to flash 5-minute presentations of selected submissions.

## Course summary

The course consists in eight sessions over four days.

1. Problem identification and solution planning
2. Market microstructure and volume forecasting
3. Trade execution 1: predictinbg an algorithm's participation rate
4. Trade execution 2: alpha profiling
5. Volatility forecasting
6. Options pricing and volatility attribution
7. Corporate bonds in a crisis
8. Flash presentations

## Datasets

1. Daily10AmSignals.csv (470MB, and shorter version for 2017)
You are running a quant fund that places orders at 10AM and exits all trades at the close. What to buy, what to short? To help you in your decision, you collected and combined a couple of unusual datasets.

* the prior-five-minute order flow metrics describing how much people are buying or selling, whether this activity is taking place in displayed market activity or through hidden orders, and how it relates to price dynamics over the same 5-minute window.
* an advanced analysis on options prices to determine implied volatilities even for relatively illiquid issuers using an ensemble average pricing technique, and the related implied one-day jump magnitude.
* the StreetAccount news feed and a ranking of stories by their likelihood of triggering large price changes.

The dataset comprises one record each market day for a specified universe of securities, over the ranve covering July 2011 – September 2017. I am holding back Oct 2018-to-date and will let you know if you made any profits over that period.

|Header      	        |Description                                                         	| 
| ------------------	|:-------------------------------------------------------------------:|
|Trade_dt_key 	      | The date of the signal					                                    |
|Symbol             	| The stock trading symbol			                                    	|
|Price		            | The last sale price as of 10AM				                              |
|Bid		              | The best bid price					                                        |
|Ask		              | The best offer price					                                      |
|Price_High	          |The highest traded price in the prior 5 minutes		                  |
|Price_Low	          |The Lowest traded price in the prior 5 minutes		                    |
|SPY		              |The S&P500 exchange traded fund last sale		                        |
|SPY_High	            |The SPY 5-minute high					                                      |
|SPY_Low	            | The SPY 5-minute low					                                      |
|Price_STD	          |The 5-min standard deviation of the stock price	                    |
|SPY_STD	            | The 5-min standard deviation of SPY			                            |
|VWAP		              |The volume-weighted 5-minute average price		                        |
|Ticks		            |The number of trades in last 5 minutes			                          |
|Market_Buy         	|The number of shares bought from a displayed offer	                  |
|Market_Sell	        |The number of shares sold to a displayed bid		                      |
|Dark_Buy	            |Additional shares bought at the offer			                          |
|Dark_Sell	          |Additional shares sold at the bid			                              |
|Dark_Cross	          |Number of shares traded between the bid and offer	                  |
|Limit_Buy	          |Number of shares added to the best bid		                            |
|Limit_Sell	          | Number of shares added to the best offer		                        |
|Canceled_Buy	        | Number of shares cancelled from the best bid		                    |
|Canceled_Sell	      | Number of shares cancelled from the best offer	                    |
|Volume               |Market_Buy+Market_Sell+Dark_Buy+Dark_Sell+Dark_Cross	                |
|Open_Qty	            |Number of shares traded at the open			                            |
|Close_Price	        |*Ex-post: day’s closing price*				                                |
|Intra_High_Price     |*The intra-day high price*				                                    |
|Intra_Low_Price      |*The intra-day low price*				                                    |
|Intra_Volume         |*The intra-day volume*					                                      |
|Intra_VWAP           |*The intra-day volume-weighted average price*		                    |
|Near-term IV	        |The implied volatility to the first option expiration	              |
|Next-term IV	        | The implied volatility to the second option expiration	            |
|Near_ IV_Ensemble    |The implied volatility from ensemble-average prices                  |
|One_Day_IV_Ensemble  |The one-day implied jump magnitude 		                              |
|Jump_Threshold       | A threshold for one-day-jump to be significant	                    |
|Expiration_Date      |The first expiration date				                                    |
|Base_IV	            |The base volatility excluding one-day-jump estimate	                |
|Earnings           	|Is an earnings announcement expected by expiry	                      |
|Scale_Factor	        |corporate actions require dividing prices by a factor 	              |
|Close_Price	        |the closing price					                                          |
|Next_Price         	|the closing price for the next market day		                        |
|Next_Scale	          |the next day’s close is measured relative to this	                  |
|Expiration_Price     |The closing price on the near expiration date		                    |
|Expiration_Scale     |The expiration price is measured relative to this	                  |
|Headline	            |The StreetAccount story headline			                                |
|Subjects	            |The subject labels attached to the story		                          |
|Event_type	          |The subject category (unique)				                                |
|Event_rank	          |How this subject category ranks for influence on prices	            |

2. PsychologySampleEnriched, 60MB

Purpose: to determine whether psychological metrics of authors of financial tweets are related to, and potentiall predictive of, market performance

* Metrics from Social Market Analytics: buzz, sentiment, etc.
* Metrics reflecting the state of mind of authors, from Receptivity.ai
* Market prices from 60 days prior to 60 days after

3. OptionsAndNews.csv (960MB)

Purpose: option markets are a fantastic window into the future: options capture the implied distribution of returns to the expiration date. So whereas a stock price gives the expected future price, the options montage informs on the distribution. To understand why the options market is implying what it does, it is necessary to couple options data to news stories. 

This dataset combines StreetAccount news stories and option prices, together with advanced analytics on the options montage including the implied base volatility and one-day implied jump magnitude from the ensemble average pricing of the options montage and time value-weighted average implied volatilities. This dataset comprises one record per story covering the date range Jan 2012 – Sept 2018.

* Underlying symbol, date, close price, next close price and price at expiration
* Implied volatility and implied jump at the close based on ensemble method
* Earnings expected by expiration label
* StreetAccount news story, subject classification and relevancy rank

The column header descriptions may be found in the above dataset descriptions.

4. OptionsMontageByEvent.csv (1.3GB)

Purpose: as noted above, the options market encodes valuable predictive insight into the distribution of future returns. This dataset aims to determine whether the shape of the volatility surface can be categorized by specific news subjects. 

In addition to data fields described previously, we have the following columns.

|Header      		            |Description                                                       	| 
| -------------------------	|:----------------------------------------------------------------: |
|p_opt_underlying_price 	  | The date of the signal					                                  |
|p_opt_exp_daten            | The stock trading symbol				                                  |
|days_to_expiration		      |Number of days to expiration				                                |
|p_opt_strike_price		      |The strike price					                                          |
|ensemble_iv_putcall		    |The implied volatility, considering both puts and calls	          |
|ensemble_price_putcall	    |The put option price					                                      |
|uncertainty_putcall		    |The uncertainty on the put option price		                        |
|daysto_EPS			            |Number of days to the earnings announcement	                      |       	
|histvol30			            |A 3-day trailing measure of volatility			                        |
|ImpliedJump		            |The implied jump magnitude, from the informed jump model	          |
|InformedJump			          |The informed jump component of the implied jump	                  |
|InformedSkew			          |The skewness parameter in the informed jump		                    |
|PoissonJump			          |The jump magnitude of Poisson jump process		                      |
|PoissonRate			          |The Poisson rate for the institutional response		                |
|Poisson_Sigma_1		        |The standard deviation parameter in a Merton model	                |
|Poisson_Jump_1		          |The implied jump magnitude in the Merton model	                    |
|Poisson_Rate_1		          |The Poisson rate for the Merton model                              |

