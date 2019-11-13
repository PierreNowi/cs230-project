# cs230-project
# Deep Reinforcement Learning Framework for Factor Investing

## Data: Data for Finanical Markets uploaded with Information Coefficients Calculations. 

```
Structure:
	Readme.mf
	/Data-snapshot
		/Commodities
		/Commodities Static
		/Description
		/Economic
		/Economic Poll
		/Economic Static
		/Futures
		/Futures Static
		/FX
		/FX Static
		/Index
		/Index Static
		/Interest Rates
		/Interest Rates Static
		/Options Index
		/Options Index Static
		/US Stocks
		/US Stocks Static
	/Data-processed
	/Data-factor
	/Output
```

Data description:
* "Data-snapshot" ("Data" can be obtained through downloading at [DataStream Refinitiv](http://solutions.refinitiv.com/datastream-macroeconomic-analysis/?utm_content=Refinitiv%20Brand%20Product-UKI-EMEA-G-EN-BMM&utm_medium=cpc&utm_source=google&utm_campaign=68832_RefinitivBAUPaidSearch&elqCampaignId=5917&utm_term=%20+refinitiv%20+datastream&&gclid=EAIaIQobChMImtHOtIfj5QIVVoXVCh1sSQPDEAAYASAAEgIb5_D_BwE)) contains the raw time-series of market informations (Stocks, Commodities, Economic information, Futures, Currencies(FX), Stock and Credit Indices, Interest Rates, Options on Stock Indices). "Static" extension contains the information describing the nature of the financial contracts, i.e. for a stock options: the expiry, the underlying stock, the name of the contract: Put or Call, etc.

* "Data-processed" contains the information of raw time-series grouped along the time axis $t$ split in 2 arrays: 
_(Currenty under development)_
..* __data_stocks__ collects from "Data-snapshot" the time-series of the values of the stocks to help compute the $Q(s,a)$ function by simulating the value of the agent composition of the positions searched. 

..* __mrkt_info__ collects from "Data-snapshot" the time-series of the market conditions such as the implied volatility, the momentum factors, positions of currencies, oil prices etc. This data is usefull in constructing the Information Coefficient (IC) factors that will feed the Deep Neural Network in the model. This is the dataset used for the Back-testing in the model.
..* __mrkt_info__ collects from "Data-snapshot" the time-series of the market conditions such as the implied volatility, the momentum factors, positions of currencies, oil prices etc. This data is usefull in constructing the Information Coefficient (IC) factors that will feed the Deep Neural Network in the model. 
* "Data-factor" contains the time-series of factors build from __mrkt_info__ that will feed the DNN in the model.
* "Output" contains the time-series of the positions taken by the $Q(s,a)$ function.



## Model 

Model Description
![input-content](/markdown-here/images/Network-proposal-4.png)


<img src="https://latex.codecogs.com/svg.latex?\Large&space;\alpha = IC_{i,z} \times \sigma_j \times z" title="IC" />
