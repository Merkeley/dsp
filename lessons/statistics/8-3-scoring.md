[Think Stats Chapter 8 Exercise 3](http://greenteapress.com/thinkstats2/html/thinkstats2009.html#toc77)

---
```Python
def SimulateMany(lam, game_count) :
    goals = []
    
    for i in range(game_count) :
        goals.append(SimulateGame(lam))
    
    errs = list(np.array(goals) - lam)
    mean_err = np.mean(errs)
    rmse = RMSE(goals, lam)
    
    return(mean_err, rmse, goals)

mean_err, rmse, goals = SimulateMany(3, 100)
mean_err, rmse, goals
```
The sample size (number of goals) is small which will lead to biased estimates.

---

Plot the sampling distribution of the estimates and the 90% confidence interval.

What happens to sampling error for increasing values of lam?

```Python

goal_cdf = thinkstats2.Cdf(goals)
thinkplot.Cdfs([goal_cdf])

ci = (goal_cdf.Percentile(5), goal_cdf.Percentile(95))
ci
```

Sampling error will increase as the average number of goals increases.

---
