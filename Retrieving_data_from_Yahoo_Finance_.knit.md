---
title: "Retrieving data from Yahoo Finance"
author: "Andrew Meng"
date: "November 29, 2016"
output: pdf_document
---





```r
#####################################################################
##########   Retrieving data from Yahoo Finance   ####################
#####################################################################

#  Installing 'quantmod' package is needed

library(quantmod)
`

```r
getSymbols("^GSPC",src="yahoo",from="2014-1-1",to=Sys.Date()) 
```

```



```
## [1] "GSPC"
```

```r
print(head(GSPC));print(tail(GSPC))    # Printing the first and last 6 records
```

```
##            GSPC.Open GSPC.High GSPC.Low GSPC.Close GSPC.Volume
## 2014-01-02   1845.86   1845.86  1827.74    1831.98  3080600000
## 2014-01-03   1833.21   1838.24  1829.13    1831.37  2774270000
## 2014-01-06   1832.31   1837.16  1823.73    1826.77  3294850000
## 2014-01-07   1828.71   1840.10  1828.71    1837.88  3511750000
## 2014-01-08   1837.90   1840.02  1831.40    1837.49  3652140000
## 2014-01-09   1839.00   1843.23  1830.38    1838.13  3581150000
##            GSPC.Adjusted
## 2014-01-02       1831.98
## 2014-01-03       1831.37
## 2014-01-06       1826.77
## 2014-01-07       1837.88
## 2014-01-08       1837.49
## 2014-01-09       1838.13
```

```
##            GSPC.Open GSPC.High GSPC.Low GSPC.Close GSPC.Volume
## 2016-11-18   2186.85   2189.89  2180.38    2181.90  3572400000
## 2016-11-21   2186.43   2198.70  2186.43    2198.18  3607010000
## 2016-11-22   2201.56   2204.80  2194.51    2202.94  3957940000
## 2016-11-23   2198.55   2204.72  2194.51    2204.72  3418640000
## 2016-11-25   2206.27   2213.35  2206.27    2213.35  1584600000
## 2016-11-28   2210.21   2211.14  2200.36    2201.72  3505650000
##            GSPC.Adjusted
## 2016-11-18       2181.90
## 2016-11-21       2198.18
## 2016-11-22       2202.94
## 2016-11-23       2204.72
## 2016-11-25       2213.35
## 2016-11-28       2201.72
```

```r
print(class(GSPC))
```

```
## [1] "xts" "zoo"
```

```r
print(is.OHLC(GSPC))
```

```
## [1] TRUE
```

```r
print(is.OHLCV(GSPC))
```

```
## [1] TRUE
```

```r
# is.OHLC (and is.HLC, similarly will return TRUE, when 
# there are columns for Open, High, Low and Close. 
# Additional columns will not affect the value.


##### Retrive Appple Inc. stock data from 2013-1-1 to current date

getSymbols("AAPL", src = "yahoo", from="2013-1-1", to= Sys.Date())
```

```
## Warning in download.file(paste(yahoo.URL, "s=", Symbols.name, "&a=",
## from.m, : downloaded length 71016 != reported length 200
```

```
## [1] "AAPL"
```

```r
print(head(AAPL)); print(tail(AAPL))
```

```
##            AAPL.Open AAPL.High AAPL.Low AAPL.Close AAPL.Volume
## 2013-01-02    553.82    555.00   541.63     549.03   140129500
## 2013-01-03    547.88    549.67   541.00     542.10    88241300
## 2013-01-04    536.97    538.63   525.83     527.00   148583400
## 2013-01-07    522.00    529.30   515.20     523.90   121039100
## 2013-01-08    529.21    531.89   521.25     525.31   114676800
## 2013-01-09    522.50    525.01   515.99     517.10   101901100
##            AAPL.Adjusted
## 2013-01-02      72.07491
## 2013-01-03      71.16516
## 2013-01-04      69.18288
## 2013-01-07      68.77592
## 2013-01-08      68.96103
## 2013-01-09      67.88324
```

```
##            AAPL.Open AAPL.High AAPL.Low AAPL.Close AAPL.Volume
## 2016-11-18    109.72    110.54   109.66     110.06    27404300
## 2016-11-21    110.12    111.99   110.01     111.73    29119100
## 2016-11-22    111.95    112.42   111.40     111.80    25922600
## 2016-11-23    111.36    111.51   110.33     111.23    27387900
## 2016-11-25    111.13    111.87   110.95     111.79    11424400
## 2016-11-28    111.43    112.47   111.39     111.57    27026600
##            AAPL.Adjusted
## 2016-11-18        110.06
## 2016-11-21        111.73
## 2016-11-22        111.80
## 2016-11-23        111.23
## 2016-11-25        111.79
## 2016-11-28        111.57
```

```r
# Print results

# Retrive a list of stocks' data from Yahoo Finance

mySymbols<- c("MSFT", "ORCL", "GOOG", "INTL", "AAPL", "CSCO", "SYMC", "TSLA")
getSymbols(mySymbols,src= "yahoo", from= "2012-1-1", to= Sys.Date())
```

```
## Warning in download.file(paste(yahoo.URL, "s=", Symbols.name, "&a=",
## from.m, : downloaded length 79736 != reported length 200
```

```
## Warning in download.file(paste(yahoo.URL, "s=", Symbols.name, "&a=",
## from.m, : downloaded length 79654 != reported length 200
```

```
## Warning in download.file(paste(yahoo.URL, "s=", Symbols.name, "&a=",
## from.m, : downloaded length 90169 != reported length 200
```

```
## Warning in download.file(paste(yahoo.URL, "s=", Symbols.name, "&a=",
## from.m, : downloaded length 70189 != reported length 200
```

```
## Warning in download.file(paste(yahoo.URL, "s=", Symbols.name, "&a=",
## from.m, : downloaded length 89470 != reported length 200
```

```
## pausing 1 second between requests for more than 5 symbols
```

```
## Warning in download.file(paste(yahoo.URL, "s=", Symbols.name, "&a=",
## from.m, : downloaded length 75769 != reported length 200
```

```
## pausing 1 second between requests for more than 5 symbols
```

```
## Warning in download.file(paste(yahoo.URL, "s=", Symbols.name, "&a=",
## from.m, : downloaded length 74323 != reported length 200
```

```
## pausing 1 second between requests for more than 5 symbols
```

```
## Warning in download.file(paste(yahoo.URL, "s=", Symbols.name, "&a=",
## from.m, : downloaded length 84262 != reported length 200
```

```
## pausing 1 second between requests for more than 5 symbols
```

```
## [1] "MSFT" "ORCL" "GOOG" "INTL" "AAPL" "CSCO" "SYMC" "TSLA"
```

```r
print(head(TSLA)); print(tail(TSLA))
```

```
##            TSLA.Open TSLA.High TSLA.Low TSLA.Close TSLA.Volume
## 2012-01-03     28.94     29.50    27.65      28.08      928100
## 2012-01-04     28.21     28.67    27.50      27.71      630100
## 2012-01-05     27.76     27.93    26.85      27.12     1005500
## 2012-01-06     27.20     27.79    26.41      26.91      986300
## 2012-01-09     27.00     27.49    26.12      27.25      897000
## 2012-01-10     27.44     27.76    27.25      27.62      671800
##            TSLA.Adjusted
## 2012-01-03         28.08
## 2012-01-04         27.71
## 2012-01-05         27.12
## 2012-01-06         26.91
## 2012-01-09         27.25
## 2012-01-10         27.62
```

```
##            TSLA.Open TSLA.High TSLA.Low TSLA.Close TSLA.Volume
## 2016-11-18    190.65    193.00   185.00     185.02     5201100
## 2016-11-21    185.04    188.89   184.41     184.52     4344600
## 2016-11-22    185.84    191.47   183.71     191.17     5600300
## 2016-11-23    190.61    195.64   189.00     193.14     4885300
## 2016-11-25    193.64    197.24   193.64     196.65     2363800
## 2016-11-28    195.48    199.35   194.55     196.12     4487100
##            TSLA.Adjusted
## 2016-11-18        185.02
## 2016-11-21        184.52
## 2016-11-22        191.17
## 2016-11-23        193.14
## 2016-11-25        196.65
## 2016-11-28        196.12
```

```r
print(head(GOOG)); print(tail(GOOG))
```

```
##            GOOG.Open GOOG.High GOOG.Low GOOG.Close GOOG.Volume
## 2012-01-03  652.9411  668.1512 652.3711   665.4111     7380500
## 2012-01-04  665.0312  670.2512 660.6211   668.2812     5749400
## 2012-01-05  662.1312  663.9712 656.2311   659.0111     6590300
## 2012-01-06  659.1512  660.0011 649.7911   650.0211     5405900
## 2012-01-09  646.5011  647.0011 621.2310   622.4610    11688800
## 2012-01-10  629.7511  633.8011 616.9111   623.1411     8824000
##            GOOG.Adjusted
## 2012-01-03      332.3732
## 2012-01-04      333.8068
## 2012-01-05      329.1764
## 2012-01-06      324.6859
## 2012-01-09      310.9196
## 2012-01-10      311.2593
```

```
##            GOOG.Open GOOG.High GOOG.Low GOOG.Close GOOG.Volume
## 2016-11-18    771.37   775.000   760.00     760.54     1526200
## 2016-11-21    762.61   769.700   760.60     769.20     1323000
## 2016-11-22    772.63   776.960   767.00     768.27     1591800
## 2016-11-23    767.73   768.283   755.25     760.99     1477400
## 2016-11-25    764.26   765.000   760.52     761.68      586000
## 2016-11-28    760.00   779.530   759.80     768.24     2172200
##            GOOG.Adjusted
## 2016-11-18        760.54
## 2016-11-21        769.20
## 2016-11-22        768.27
## 2016-11-23        760.99
## 2016-11-25        761.68
## 2016-11-28        768.24
```

```r
#  Similarily, we can also use quantmod package to get data for other financial indexes


# 10 year bond index
getSymbols("^TNX",src="yahoo",from="2005-1-1",to=Sys.Date()) 
```

```
## Warning in download.file(paste(yahoo.URL, "s=", Symbols.name, "&a=",
## from.m, : downloaded length 133380 != reported length 200
```

```
## [1] "TNX"
```

```r
print(head(TNX));print(tail(TNX))
```

```
##            TNX.Open TNX.High TNX.Low TNX.Close TNX.Volume TNX.Adjusted
## 2005-01-03    4.257    4.270   4.203     4.220          0        4.220
## 2005-01-04    4.212    4.307   4.197     4.283          0        4.283
## 2005-01-05    4.298    4.304   4.255     4.277          0        4.277
## 2005-01-06    4.288    4.298   4.257     4.272          0        4.272
## 2005-01-07    4.255    4.313   4.148     4.285          0        4.285
## 2005-01-10    4.270    4.295   4.260     4.278          0        4.278
```

```
##            TNX.Open TNX.High TNX.Low TNX.Close TNX.Volume TNX.Adjusted
## 2016-11-18    2.280    2.355   2.267     2.335          0        2.335
## 2016-11-21    2.315    2.341   2.310     2.339          0        2.339
## 2016-11-22    2.298    2.326   2.287     2.321          0        2.321
## 2016-11-23    2.321    2.417   2.321     2.357          0        2.357
## 2016-11-25    2.379    2.392   2.350     2.372          0        2.372
## 2016-11-28    2.325    2.345   2.314     2.320          0        2.320
```

```r
#  ETF FUND
getSymbols("ACWI",src="yahoo",from="2005-1-1",to=Sys.Date()) 
```

```
## Warning in download.file(paste(yahoo.URL, "s=", Symbols.name, "&a=",
## from.m, : downloaded length 138054 != reported length 200
```

```
## [1] "ACWI"
```

```r
print(head(ACWI));print(tail(ACWI))
```

```
##            ACWI.Open ACWI.High ACWI.Low ACWI.Close ACWI.Volume
## 2008-03-28     50.10     50.10    50.10      50.10         200
## 2008-03-31     50.00     50.00    49.32      49.32         400
## 2008-04-01     50.25     50.65    50.16      50.65         600
## 2008-04-02     51.12     51.40    51.05      51.21       10700
## 2008-04-03     59.70     59.70    50.95      51.50       29100
## 2008-04-04     54.95     54.95    51.47      51.47        9900
##            ACWI.Adjusted
## 2008-03-28      42.65003
## 2008-03-31      41.98602
## 2008-04-01      43.11825
## 2008-04-02      43.59497
## 2008-04-03      43.84185
## 2008-04-04      43.81631
```

```
##            ACWI.Open ACWI.High ACWI.Low ACWI.Close ACWI.Volume
## 2016-11-18     58.12     58.20    57.94      58.02     1457400
## 2016-11-21     58.20     58.50    58.20      58.47     1033900
## 2016-11-22     58.60     58.71    58.43      58.71     2146300
## 2016-11-23     58.38     58.57    58.21      58.57     1866000
## 2016-11-25     58.68     58.79    58.64      58.79      633700
## 2016-11-28     58.70     58.76    58.50      58.57     2626500
##            ACWI.Adjusted
## 2016-11-18         58.02
## 2016-11-21         58.47
## 2016-11-22         58.71
## 2016-11-23         58.57
## 2016-11-25         58.79
## 2016-11-28         58.57
```

```r
# Get the currency exchange
getFX("USD/JPY")
```

```
## [1] "USDJPY"
```

```r
print(head(USDJPY));print(tail(USDJPY))
```

```
##            USD.JPY
## 2015-07-19 124.064
## 2015-07-20 124.207
## 2015-07-21 124.225
## 2015-07-22 123.852
## 2015-07-23 123.927
## 2015-07-24 123.886
```

```
##            USD.JPY
## 2016-11-23 111.511
## 2016-11-24 112.971
## 2016-11-25 113.206
## 2016-11-26 113.246
## 2016-11-27 113.253
## 2016-11-28 112.294
```

```r
getSymbols("EUR/USD",src="oanda")
```

```
## [1] "EURUSD"
```

```r
print(head(EURUSD));print(tail(EURUSD))
```

```
##            EUR.USD
## 2015-07-19 1.08298
## 2015-07-20 1.08380
## 2015-07-21 1.08678
## 2015-07-22 1.09247
## 2015-07-23 1.09659
## 2015-07-24 1.09688
```

```
##            EUR.USD
## 2016-11-23 1.06020
## 2016-11-24 1.05519
## 2016-11-25 1.05824
## 2016-11-26 1.05935
## 2016-11-27 1.05936
## 2016-11-28 1.06188
```

```r
getSymbols("EUR/USD",src="oanda",from="2005-01-01")
```

```
## Warning in getSymbols.oanda(Symbols = "EUR/USD", env = <environment>,
## verbose = FALSE, : Oanda limits data to 5years. Symbol: EUR/USD
```

```
## [1] "EURUSD"
```

```r
print(tail(EURUSD))
```

```
##            EUR.USD
## 2016-11-23 1.06020
## 2016-11-24 1.05519
## 2016-11-25 1.05824
## 2016-11-26 1.05935
## 2016-11-27 1.05936
## 2016-11-28 1.06188
```

```r
# Get the lastest quoted price, take Apple Inc. as an example

tmp <- getQuote("AAPL");print(tmp);print(class(tmp))
```

```
##               Trade Time   Last Change % Change Open High Low Volume
## AAPL 2016-11-28 04:00:00 111.57  -0.22   -0.20%  N/A  N/A N/A   2985
```

```
## [1] "data.frame"
```


```r
# Get Financial info
getFinancials("TSLA")
```

```
## Warning in download.file(paste(google.fin, Symbol, sep = ""), quiet =
## TRUE, : downloaded length 70598 != reported length 200
```

```
## [1] "TSLA.f"
```

```r
viewFin(TSLA.f)
```

```
## Annual Balance Sheet for TSLA
```

```
##                                              2015-12-31 2014-12-31
## Cash & Equivalents                              1196.91    1905.71
## Short Term Investments                               NA         NA
## Cash and Short Term Investments                 1196.91    1905.71
## Accounts Receivable - Trade, Net                 168.97     226.60
## Receivables - Other                                  NA         NA
## Total Receivables, Net                           168.97     226.60
## Total Inventory                                 1277.84     953.67
## Prepaid Expenses                                 115.67      76.13
## Other Current Assets, Total                       22.63      17.95
## Total Current Assets                            2782.01    3180.07
## Property/Plant/Equipment, Total - Gross         3974.46    2121.86
## Accumulated Depreciation, Total                 -571.13    -292.59
## Goodwill, Net                                        NA         NA
## Intangibles, Net                                     NA         NA
## Long Term Investments                                NA         NA
## Other Long Term Assets, Total                     91.20      54.58
## Total Assets                                    8067.94    5830.67
## Accounts Payable                                 916.15     777.95
## Accrued Expenses                                 321.59     197.65
## Notes Payable/Short Term Debt                      0.00       0.00
## Current Port. of LT Debt/Capital Leases          627.93     611.10
## Other Current liabilities, Total                 945.37     520.47
## Total Current Liabilities                       2811.03    2107.17
## Long Term Debt                                  2068.38    1876.98
## Capital Lease Obligations                            NA         NA
## Total Long Term Debt                            2068.38    1876.98
## Total Debt                                      2696.30    2488.08
## Deferred Income Tax                                  NA         NA
## Minority Interest                                    NA         NA
## Other Liabilities, Total                        2104.82     934.81
## Total Liabilities                               6984.23    4918.96
## Redeemable Preferred Stock, Total                    NA         NA
## Preferred Stock - Non Redeemable, Net                NA         NA
## Common Stock, Total                                0.13       0.13
## Additional Paid-In Capital                      3409.45    2345.27
## Retained Earnings (Accumulated Deficit)        -2322.32   -1433.66
## Treasury Stock - Common                              NA         NA
## Other Equity, Total                               -3.56      -0.02
## Total Equity                                    1083.70     911.71
## Total Liabilities & Shareholders&#39; Equity    8067.94    5830.67
## Shares Outs - Common Stock Primary Issue             NA         NA
## Total Common Shares Outstanding                  131.43     125.69
##                                              2013-12-31 2012-12-31
## Cash & Equivalents                               845.89     201.89
## Short Term Investments                               NA         NA
## Cash and Short Term Investments                  845.89     201.89
## Accounts Receivable - Trade, Net                  49.11      26.84
## Receivables - Other                                  NA         NA
## Total Receivables, Net                            49.11      26.84
## Total Inventory                                  340.36     268.50
## Prepaid Expenses                                  27.57       8.44
## Other Current Assets, Total                        3.01      19.09
## Total Current Assets                            1265.94     524.77
## Property/Plant/Equipment, Total - Gross          878.64     609.77
## Accumulated Depreciation, Total                 -140.14     -57.54
## Goodwill, Net                                        NA         NA
## Intangibles, Net                                     NA         NA
## Long Term Investments                                NA         NA
## Other Long Term Assets, Total                     30.07      27.12
## Total Assets                                    2416.93    1114.19
## Accounts Payable                                 303.97     303.38
## Accrued Expenses                                  68.05      30.09
## Notes Payable/Short Term Debt                      0.18       0.00
## Current Port. of LT Debt/Capital Leases            7.72      55.21
## Other Current liabilities, Total                 295.23     150.43
## Total Current Liabilities                        675.16     539.11
## Long Term Debt                                   586.12     401.50
## Capital Lease Obligations                         12.86       9.96
## Total Long Term Debt                             598.97     411.46
## Total Debt                                       606.88     466.67
## Deferred Income Tax                                5.23         NA
## Minority Interest                                    NA         NA
## Other Liabilities, Total                         470.44      38.92
## Total Liabilities                               1749.81     989.49
## Redeemable Preferred Stock, Total                    NA         NA
## Preferred Stock - Non Redeemable, Net                NA         NA
## Common Stock, Total                                0.12       0.12
## Additional Paid-In Capital                      1806.62    1190.19
## Retained Earnings (Accumulated Deficit)        -1139.62   -1065.61
## Treasury Stock - Common                              NA         NA
## Other Equity, Total                                  NA         NA
## Total Equity                                     667.12     124.70
## Total Liabilities & Shareholders&#39; Equity    2416.93    1114.19
## Shares Outs - Common Stock Primary Issue             NA         NA
## Total Common Shares Outstanding                  123.09     114.21
## attr(,"col_desc")
## [1] "As of 2015-12-31" "As of 2014-12-31" "As of 2013-12-31"
## [4] "As of 2012-12-31"
```

```r
viewFin(TSLA.f,"CF","A")   # view the CF statements
```

```
## Annual Cash Flow Statement for TSLA
```

```
##                                        2015-12-31 2014-12-31 2013-12-31
## Net Income/Starting Line                  -888.66    -294.04     -74.01
## Depreciation/Depletion                     422.59     231.93     106.08
## Amortization                                   NA         NA         NA
## Deferred Taxes                                 NA         NA         NA
## Non-Cash Items                             434.86     261.60      83.78
## Changes in Working Capital                -493.29    -256.82     148.96
## Cash from Operating Activities            -524.50     -57.34     264.80
## Capital Expenditures                     -1634.85    -969.88    -264.22
## Other Investing Cash Flow Items, Total     -38.70     -20.56      14.81
## Cash from Investing Activities           -1673.55    -990.44    -249.42
## Financing Cash Flow Items                  551.72    -635.31    -194.44
## Total Cash Dividends Paid                      NA         NA         NA
## Issuance (Retirement) of Stock, Net        856.61     489.62     630.62
## Issuance (Retirement) of Debt, Net         115.19    2288.82     199.24
## Cash from Financing Activities            1523.52    2143.13     635.42
## Foreign Exchange Effects                   -34.28     -35.52      -6.81
## Net Change in Cash                        -708.80    1059.82     644.00
## Cash Interest Paid, Supplemental            32.06      20.54       9.04
## Cash Taxes Paid, Supplemental                9.46       3.12       0.26
##                                        2012-12-31
## Net Income/Starting Line                  -396.21
## Depreciation/Depletion                      28.82
## Amortization                                   NA
## Deferred Taxes                                 NA
## Non-Cash Items                              58.63
## Changes in Working Capital                  44.94
## Cash from Operating Activities            -263.81
## Capital Expenditures                      -239.23
## Other Investing Cash Flow Items, Total      32.30
## Cash from Investing Activities            -206.93
## Financing Cash Flow Items                    0.00
## Total Cash Dividends Paid                      NA
## Issuance (Retirement) of Stock, Net        246.38
## Issuance (Retirement) of Debt, Net         173.25
## Cash from Financing Activities             419.63
## Foreign Exchange Effects                    -2.27
## Net Change in Cash                         -53.38
## Cash Interest Paid, Supplemental               NA
## Cash Taxes Paid, Supplemental                  NA
## attr(,"col_desc")
## [1] "12 months ending 2015-12-31" "12 months ending 2014-12-31"
## [3] "12 months ending 2013-12-31" "12 months ending 2012-12-31"
```

```r
getDividends("AAPL")
```

```
## Warning in download.file(paste(yahoo.URL, Symbol.name, "&a=", from.m,
## "&b=", : downloaded length 1075 != reported length 200
```

```
##               [,1]
## 1987-05-11 0.00214
## 1987-08-10 0.00214
## 1987-11-17 0.00286
## 1988-02-12 0.00286
## 1988-05-16 0.00286
## 1988-08-15 0.00286
## 1988-11-21 0.00357
## 1989-02-17 0.00357
## 1989-05-22 0.00357
## 1989-08-21 0.00357
## 1989-11-17 0.00393
## 1990-02-16 0.00393
## 1990-05-21 0.00393
## 1990-08-20 0.00393
## 1990-11-16 0.00429
## 1991-02-15 0.00429
## 1991-05-20 0.00429
## 1991-08-19 0.00429
## 1991-11-18 0.00429
## 1992-02-14 0.00429
## 1992-06-01 0.00429
## 1992-08-17 0.00429
## 1992-11-30 0.00429
## 1993-02-12 0.00429
## 1993-05-28 0.00429
## 1993-08-16 0.00429
## 1993-11-19 0.00429
## 1994-02-07 0.00429
## 1994-05-27 0.00429
## 1994-08-15 0.00429
## 1994-11-18 0.00429
## 1995-02-13 0.00429
## 1995-05-26 0.00429
## 1995-08-16 0.00429
## 1995-11-21 0.00429
## 2012-08-09 0.37857
## 2012-11-07 0.37857
## 2013-02-07 0.37857
## 2013-05-09 0.43571
## 2013-08-08 0.43571
## 2013-11-06 0.43571
## 2014-02-06 0.43571
## 2014-05-08 0.47000
## 2014-08-07 0.47000
## 2014-11-06 0.47000
## 2015-02-05 0.47000
## 2015-05-07 0.52000
## 2015-08-06 0.52000
## 2015-11-05 0.52000
## 2016-02-04 0.52000
## 2016-05-05 0.57000
## 2016-08-04 0.57000
## 2016-11-03 0.57000
```

```r
getSplits("BIDU")   # 10 for 1
```

```
## Warning in download.file(paste(yahoo.URL, Symbol.name, "&a=", from.m,
## "&b=", : downloaded length 97 != reported length 200
```

```
##            BIDU.spl
## 2010-05-12      0.1
```

```r
getSplits("NKE")
```

```
## Warning in download.file(paste(yahoo.URL, Symbol.name, "&a=", from.m,
## "&b=", : downloaded length 3474 != reported length 200
```

```
##            NKE.spl
## 1990-10-08     0.5
## 1995-10-31     0.5
## 1996-10-24     0.5
## 2007-04-03     0.5
## 2012-12-26     0.5
## 2015-12-24     0.5
```

```r
# Get rid of options and dividents

getSymbols("BIDU", from="2005-01-01", src="yahoo")
```

```
## Warning in download.file(paste(yahoo.URL, "s=", Symbols.name, "&a=",
## from.m, : downloaded length 198949 != reported length 200
```

```
## [1] "BIDU"
```

```r
head(BIDU)
```

```
##            BIDU.Open BIDU.High BIDU.Low BIDU.Close BIDU.Volume
## 2005-08-05     66.00    151.21    60.00     122.54   226811000
## 2005-08-08    137.75    153.98   115.24     115.50   154889000
## 2005-08-09    120.50    125.30    95.69      96.10    86677000
## 2005-08-10    101.00    103.50    88.30      91.75    49638000
## 2005-08-11     91.20    100.50    90.60      97.90    73248000
## 2005-08-12     98.00     99.75    94.58      95.00    29949000
##            BIDU.Adjusted
## 2005-08-05        12.254
## 2005-08-08        11.550
## 2005-08-09         9.610
## 2005-08-10         9.175
## 2005-08-11         9.790
## 2005-08-12         9.500
```

```r
head(BIDU.a  <- adjustOHLC(BIDU))  
```

```
## Warning in download.file(paste(yahoo.URL, Symbol.name, "&a=", from.m,
## "&b=", : downloaded length 15 != reported length 200
```

```
## Warning in download.file(paste(yahoo.URL, Symbol.name, "&a=", from.m,
## "&b=", : downloaded length 97 != reported length 200
```

```
##            BIDU.Open BIDU.High BIDU.Low BIDU.Close BIDU.Volume
## 2005-08-05     6.600    15.121    6.000     12.254   226811000
## 2005-08-08    13.775    15.398   11.524     11.550   154889000
## 2005-08-09    12.050    12.530    9.569      9.610    86677000
## 2005-08-10    10.100    10.350    8.830      9.175    49638000
## 2005-08-11     9.120    10.050    9.060      9.790    73248000
## 2005-08-12     9.800     9.975    9.458      9.500    29949000
##            BIDU.Adjusted
## 2005-08-05        12.254
## 2005-08-08        11.550
## 2005-08-09         9.610
## 2005-08-10         9.175
## 2005-08-11         9.790
## 2005-08-12         9.500
```

```r
head(BIDU.uA <- adjustOHLC(BIDU, use.Adjusted=T)) 
```

```
##            BIDU.Open BIDU.High BIDU.Low BIDU.Close BIDU.Volume
## 2005-08-05     6.600    15.121    6.000     12.254   226811000
## 2005-08-08    13.775    15.398   11.524     11.550   154889000
## 2005-08-09    12.050    12.530    9.569      9.610    86677000
## 2005-08-10    10.100    10.350    8.830      9.175    49638000
## 2005-08-11     9.120    10.050    9.060      9.790    73248000
## 2005-08-12     9.800     9.975    9.458      9.500    29949000
##            BIDU.Adjusted
## 2005-08-05        12.254
## 2005-08-08        11.550
## 2005-08-09         9.610
## 2005-08-10         9.175
## 2005-08-11         9.790
## 2005-08-12         9.500
```

```r
head(cbind(OpCl(BIDU),OpCl(BIDU.a),OpCl(BIDU.uA)))
```

```
##              OpCl.BIDU OpCl.BIDU.a OpCl.BIDU.uA
## 2005-08-05  0.85666665  0.85666665   0.85666665
## 2005-08-08 -0.16152446 -0.16152446  -0.16152446
## 2005-08-09 -0.20248966 -0.20248966  -0.20248966
## 2005-08-10 -0.09158417 -0.09158417  -0.09158417
## 2005-08-11  0.07346492  0.07346492   0.07346492
## 2005-08-12 -0.03061226 -0.03061226  -0.03061226
```

```r
head(cbind(ClCl(BIDU),ClCl(BIDU.a),ClCl(BIDU.uA)))
```

```
##              ClCl.BIDU ClCl.BIDU.a ClCl.BIDU.uA
## 2005-08-05          NA          NA           NA
## 2005-08-08 -0.05745059 -0.05745059  -0.05745063
## 2005-08-09 -0.16796541 -0.16796541  -0.16796537
## 2005-08-10 -0.04526530 -0.04526530  -0.04526535
## 2005-08-11  0.06702995  0.06702995   0.06702997
## 2005-08-12 -0.02962206 -0.02962206  -0.02962206
```

```r
# Get option info
BIDU.OPT <- getOptionChain("BIDU")
print(class(BIDU.OPT)) 
```

```
## [1] "list"
```

```r
print(BIDU.OPT)        
```

```
## $calls
##                     Strike  Last        Chg   Bid   Ask  Vol OI
## BIDU161202C00140000  140.0 22.75  0.0000000 22.25 26.80    1  2
## BIDU161202C00152500  152.5 13.40  0.0000000  9.65 14.30    1  8
## BIDU161202C00155000  155.0 12.32  0.0000000  0.00  0.00    8  0
## BIDU161202C00157500  157.5 10.24  0.0000000  0.00  0.00    7  0
## BIDU161202C00160000  160.0  7.35  0.0000000  0.00  0.00    5  0
## BIDU161202C00162500  162.5  5.50  0.0000000  0.00  0.00   96  0
## BIDU161202C00165000  165.0  3.35  0.0000000  0.00  0.00  621  0
## BIDU161202C00167500  167.5  1.84  0.0000000  0.00  0.00 1218  0
## BIDU161202C00170000  170.0  0.88  0.0000000  0.00  0.00 1881  0
## BIDU161202C00172500  172.5  0.41  0.0000000  0.00  0.00 1395  0
## BIDU161202C00175000  175.0  0.17  0.0000000  0.00  0.00  468  0
## BIDU161202C00177500  177.5  0.07  0.0000000  0.00  0.00  205  0
## BIDU161202C00180000  180.0  0.06  0.0000000  0.00  0.00  536  0
## BIDU161202C00182500  182.5  0.07  0.0000000  0.00  0.00   71  0
## BIDU161202C00185000  185.0  0.05  0.0000000  0.00  0.09   10 33
## BIDU161202C00187500  187.5  0.05  0.0000000  0.00  0.09    2 47
## BIDU161202C00190000  190.0  0.22  0.0000000  0.00  0.00    1  0
## BIDU161202C00192500  192.5  0.09  0.0000000  0.00  0.10    1 47
## BIDU161202C00195000  195.0  0.12 -0.1500000  0.01  0.10    2  9
## BIDU161202C00197500  197.5  0.90 -0.2000001  0.87  0.98    4 10
## BIDU161202C00205000  205.0  1.00  0.0000000  1.00  1.10    1  1
## BIDU161202C00210000  210.0  0.08  0.0000000  0.00  0.12    1  4
## 
## $puts
##                     Strike  Last  Chg   Bid   Ask Vol  OI
## BIDU161202P00125000  125.0  0.06 0.00  0.00  0.07   1   3
## BIDU161202P00140000  140.0  0.01 0.00  0.00  0.00  75   0
## BIDU161202P00144000  144.0  0.33 0.00  0.34  0.53  20  20
## BIDU161202P00146000  146.0  1.04 0.55  0.55  0.62  17 285
## BIDU161202P00149000  149.0  0.10 0.00  0.04  0.09   1  19
## BIDU161202P00150000  150.0  0.03 0.00  0.00  0.00  64   0
## BIDU161202P00152500  152.5  0.05 0.00  0.00  0.00  31   0
## BIDU161202P00155000  155.0  0.10 0.00  0.00  0.00  24   0
## BIDU161202P00157500  157.5  0.14 0.00  0.00  0.00 294   0
## BIDU161202P00160000  160.0  0.29 0.00  0.00  0.00 168   0
## BIDU161202P00162500  162.5  0.60 0.00  0.00  0.00 466   0
## BIDU161202P00167500  167.5  2.30 0.00  0.00  0.00 339   0
## BIDU161202P00170000  170.0  3.90 0.00  0.00  0.00  59   0
## BIDU161202P00175000  175.0  8.02 0.00  0.00  0.00  80   0
## BIDU161202P00177500  177.5 10.51 0.00  0.00  0.00  10   0
## BIDU161202P00182500  182.5 20.59 0.00 18.75 21.20   1   1
## BIDU161202P00185000  185.0 17.60 0.00 18.70 22.05   5   5
## BIDU161202P00190000  190.0 23.63 0.00 25.30 29.25   1  29
```

```r
print(BIDU.OPT$symbol)  
```

```
## NULL
```

```r
print(BIDU.OPT$calls)  
```

```
##                     Strike  Last        Chg   Bid   Ask  Vol OI
## BIDU161202C00140000  140.0 22.75  0.0000000 22.25 26.80    1  2
## BIDU161202C00152500  152.5 13.40  0.0000000  9.65 14.30    1  8
## BIDU161202C00155000  155.0 12.32  0.0000000  0.00  0.00    8  0
## BIDU161202C00157500  157.5 10.24  0.0000000  0.00  0.00    7  0
## BIDU161202C00160000  160.0  7.35  0.0000000  0.00  0.00    5  0
## BIDU161202C00162500  162.5  5.50  0.0000000  0.00  0.00   96  0
## BIDU161202C00165000  165.0  3.35  0.0000000  0.00  0.00  621  0
## BIDU161202C00167500  167.5  1.84  0.0000000  0.00  0.00 1218  0
## BIDU161202C00170000  170.0  0.88  0.0000000  0.00  0.00 1881  0
## BIDU161202C00172500  172.5  0.41  0.0000000  0.00  0.00 1395  0
## BIDU161202C00175000  175.0  0.17  0.0000000  0.00  0.00  468  0
## BIDU161202C00177500  177.5  0.07  0.0000000  0.00  0.00  205  0
## BIDU161202C00180000  180.0  0.06  0.0000000  0.00  0.00  536  0
## BIDU161202C00182500  182.5  0.07  0.0000000  0.00  0.00   71  0
## BIDU161202C00185000  185.0  0.05  0.0000000  0.00  0.09   10 33
## BIDU161202C00187500  187.5  0.05  0.0000000  0.00  0.09    2 47
## BIDU161202C00190000  190.0  0.22  0.0000000  0.00  0.00    1  0
## BIDU161202C00192500  192.5  0.09  0.0000000  0.00  0.10    1 47
## BIDU161202C00195000  195.0  0.12 -0.1500000  0.01  0.10    2  9
## BIDU161202C00197500  197.5  0.90 -0.2000001  0.87  0.98    4 10
## BIDU161202C00205000  205.0  1.00  0.0000000  1.00  1.10    1  1
## BIDU161202C00210000  210.0  0.08  0.0000000  0.00  0.12    1  4
```

