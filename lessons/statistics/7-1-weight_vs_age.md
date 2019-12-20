[Think Stats Chapter 7 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2008.html#toc70) (weight vs. age)

'''python
  import first

  live, firsts, others = first.MakeFrames()
  live = live.dropna(subset=['agepreg', 'totalwgt_lb'])

  preg_age = live['agepreg']
  birth_weight = live['totalwgt_lb']
  thinkplot.Scatter(preg_age, birth_weight, alpha=0.1, s=10)
  thinkplot.Config(xlabel='Mother\'s Ave (yrs)',
                   ylabel='Birth Weight (lbs)',
                   axis=[12, 50, 0, 20],
                   legend=False)
'''
**Plot output here**
'''Python
  birth_bins = np.arange(10,50, 1)
  birth_indices = np.digitize(preg_age, birth_bins)
  birth_groups = live.groupby(birth_indices)
  birth_mean_ages = [group.agepreg.mean() for i, group in birth_groups]
  birth_cdfs = [thinkstats2.Cdf(group.totalwgt_lb) for i, group in birth_groups]

  for percent in [75, 50, 25]:
      birth_weight_percentiles = [cdf.Percentile(percent) for cdf in birth_cdfs]
      label = '%dth' % percent
      thinkplot.Plot(birth_mean_ages, birth_weight_percentiles, label=label)

  thinkplot.Config(xlabel='Birth Age (years)',
                   ylabel='Birth Weight (lbs)',
                   axis=[10,50,0,14],
                   legend=False)
'''
                 
**Plot output here**
'''
np.corrcoef(preg_age, birth_weight)
'''

*Output
array([[1.        , 0.06883397],
       [0.06883397, 1.        ]])*

SpearmanCorr(preg_age, birth_weight)

*Output
0.09461004109658226

Pregnancy age and birth weight are not very strongly correlated
