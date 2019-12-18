[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

random_list = np.random.random(1000)

random_pmf == thinkstats2.Pmf(random_list)

# Each number has a unique probability of 1/1000th

random_cdf = thinkstats2.Cdf(random_list)
thinkplot.Cdf(random_cdf)
