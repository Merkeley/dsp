[Think Stats Chapter 8 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2009.html#toc77) (scoring)

Exercise: Suppose you draw a sample with size n=10 from an exponential distribution with λ=2. Simulate this experiment 1000 times and plot the sampling distribution of the estimate L. Compute the standard error of the estimate and the 90% confidence interval.


```Python
# define a function to run the estimate that returns the estimate

def newEstimate(n=10) :
    lam = 2

    means = []
    medians = []

    xs = np.random.exponential(1.0/lam, n)
    L = 1 / np.mean(xs)
    Lm = np.log(2) / thinkstats2.Median(xs)

    return L, Lm

def runSeries(n=10, m=1000) :
    estimateList = []
    log_estimate_list = []
    for i in range(m) :
        newL, newLm = newEstimate(n)
        estimateList.append(newL)
        log_estimate_list.append(newLm)
    return(log_estimate_list)                                                                  


# Run the estimate 1000 times and save the return values
Lm_list = runSeries(10, 1000)

estimate_cdf = thinkstats2.Cdf(Lm_list)
thinkplot.Cdf(estimate_cdf)
thinkplot.Config(xlabel='Sample mean',
                 ylabel='CDF')


# Compute the standard error and 90% confidence interval
estimate_ci = estimate_cdf.Percentile(5), estimate_cdf.Percentile(95)

estimate_err = RMSE(Lm_list, 2)
estimate_ci, estimate_err

```

---

***Graph Output Here***

___

Repeat the experiment with a few different values of n and make a plot of standard error versus n.

```Python
n_values = [5, 7, 10, 12, 15, 20, 25, 30, 35, 40, 45, 50, 55, 60, 70, 80, 90, 100, 500, 1000]
error_list = []

# run the same test for a series of values of n
for test in n_values :
    Lm_list = runSeries(test, 1000)
    error_list.append(RMSE(Lm_list, 2))

thinkplot.Plot(n_values, error_list)
thinkplot.Config(xlabel='Sample Count',
                 ylabel='Standard Error')

```

---

***Graph Output Here***

---
