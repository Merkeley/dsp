[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

firsts = live[live.birthord == 1] others = live[live.birthord != 1]

print(firsts['totalwgt_lb'].mean(), others['totalwgt_lb'].mean())

output 7.2010944 7.325855
