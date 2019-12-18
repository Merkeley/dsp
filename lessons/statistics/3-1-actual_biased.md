[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

resp = nsfg.ReadFemResp() pmf = thinkstats2.Pmf(resp['numkdhh', label = 'actual'])

bias_pmf = BiasPmf(pmf, label='bias') bias_mean = bias_pmf.Mean() pmf_mean = pmf.Mean() print(pmf_mean, bias_mean)

Output>> 1.024205155043831 2.403679100664282
