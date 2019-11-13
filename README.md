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

## Citation

If you use this implementation in your work, please cite the following:

```
@article{FamaFrench,
  title   = "Common risk factors in the returns on stocks and bonds",
  journal = "Journal
of Financial Economics" ,
    volume  = "33",
  pages   = "3--56 ",
  year    = "1993",
  author  = "Fama, E. F. and K. R. French"
}
```

```
@article{KahnGinold,
  title   = "Active Portfolio Management : A quantitative approach for producing superior returns and selecting superior money managers",
  journal = "McGraw-Hill Education" ,
  pages   = "-- ",
  year    = "1999,
  author  = "R. Grinold and R. Kahn"
}
```

```
@article{FactorInRL,
  title   = "Factor Selection with Deep Reinforcement Learning for Financial Forecasting",
  journal = "University of Chicago, McKinley Capital Management",
  pages   = "-- ",
  year    = "Oct 2018",
  doi     = " https://ssrn.com/abstract=3128678",
  author  = "Ziwei Wang and Nelson Leung"
}
```

## License

Released under MIT License. See [LICENSE][license] for details.
