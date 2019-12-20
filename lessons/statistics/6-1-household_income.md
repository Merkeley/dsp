[Think Stats Chapter 6 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2007.html#toc60) (household income)

**For Upper Bound on Income of 1M**
Mean(sample), Median(sample), Skewness(sample), PearsonMedianSkewness(sample)
*Output
(74278.70753118733, 51226.45447894046, 4.949920244429583, 0.7361258019141782)*

sample_mean = Mean(sample)
cdf[sample_mean]

*Output
0.660005879566872*

Increasing the upper bound on income will increase the skew to the right and increase the mean.  Therefore it will increase the percentage of the population with income at or below the mean.

**For Upper Bound on Income of 10M**


Mean(sample), Median(sample), Skewness(sample), PearsonMedianSkewness(sample)

*Output:
(124267.39722164685,
 51226.45447894046,
 11.603690267537793,
 0.39156450927742087)*
 
 sample_mean = Mean(sample)
cdf[sample_mean]

*Output:
0.8565630665207663*
