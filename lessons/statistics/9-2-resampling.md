[Think Stats Chapter 9 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2010.html#toc90) (resampling)
```Python

class DiffMeansResample(DiffMeansPermute) :
    def RunModel(self) :
        group1 = np.random.choice(self.pool, self.n, replace=True)
        group2 = np.random.choice(self.pool, self.m, replace=True)

        
        return group1, group2
        
```

```Python
import first

live, firsts, others = first.MakeFrames()
data = firsts.prglngth.values, others.prglngth.values

ht = DiffMeansResample(data)
pvalue = ht.PValue()
print('Resample p-value for Pregnancy Length', pvalue)
print('Resample acutal for Pregnancy Length', ht.actual)
print('Resample t-max for Pregnancy Length', ht.MaxTestStat())

ht = DiffMeansPermute(data)
pvalue = ht.PValue()
print('Permute p-value for Pregnancy Length', pvalue)
print('Permute actual for Pregnancy Length' , ht.actual)
print('Permute t-max for Pregnancy Lenght', ht.MaxTestStat())

```
---
**Output:**
Resample p-value for Pregnancy Length 0.157
Resample acutal for Pregnancy Length 0.07803726677754952
Resample t-max for Pregnancy Length 0.1906588267217586
Permute p-value for Pregnancy Length 0.17
Permute actual for Pregnancy Length 0.07803726677754952
Permute t-max for Pregnancy Lenght 0.23126602763123572

```Pthon
data = firsts.dropna(subset=['totalwgt_lb']).totalwgt_lb.values, others.dropna(subset=['totalwgt_lb']).totalwgt_lb.values
ht = DiffMeansResample(data)
pvalue = ht.PValue()
print('Resample p-value for Birth Weight', pvalue)
print('Resample actual for Birth Weight', ht.actual)
print('Resample t-max for Birth Weight', ht.MaxTestStat())

ht = DiffMeansPermute(data)
pvalue = ht.PValue()
print('Permute p-value for Birth Weight', pvalue)
print('Permute actual for Birth Weight', ht.actual)
print('Permute t-max for Birth Weight', ht.MaxTestStat())
```
**Output:**
Resample p-value for Birth Weight 0.0
Resample actual for Birth Weight 0.12476118453549034
Resample t-max for Birth Weight 0.0891502590451303
Permute p-value for Birth Weight 0.001
Permute actual for Birth Weight 0.12476118453549034
Permute t-max for Birth Weight 0.1265335998754722

The model used made some minor difference in p-values for both pregnancy length and birth weight
   
