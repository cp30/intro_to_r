Tutorial 4 Help in R
======================

R has a good integration of help files and functions. There is also a large amount of help online, which will be discussed in the lectures. 

In this tutorial we will test whether the variances of two variables are significantly different. This can be challenging when we do not know how to use the available functions. 

First we will define two vectors:


```r
vector1 <- rnorm(100)
vector2 <- vector1^2
```


We have used a new function rnorm(). This function samples from a standard normal distribution. In this case we obtained 100 samples.

Open a browser window and google "variance test in R". You should find that you can use the function var.test()

Try the following commands in the R prompt to get the help files for the var.test() function.

```
??"variance test"
?var.test
help(var.test)
```

With ?? we can use quotes to query the help files in R, and it is not necessary to know the name of the function.

Inspect the output. In some operating systems typing "q" is required to exit the help file.

Now we can find out which arguments are needed to run the var.test() function:


```r
args(var.test)
```

```
## function (x, ...) 
## NULL
```


To see an example of how to use the function, in addition to some test data, use:


```r
example(var.test)
```

```
## 
## vr.tst> x <- rnorm(50, mean = 0, sd = 2)
## 
## vr.tst> y <- rnorm(30, mean = 1, sd = 1)
## 
## vr.tst> var.test(x, y)                  # Do x and y have the same variance?
## 
## 	F test to compare two variances
## 
## data:  x and y
## F = 6.041, num df = 49, denom df = 29, p-value = 1.954e-06
## alternative hypothesis: true ratio of variances is not equal to 1
## 95 percent confidence interval:
##   3.035 11.366
## sample estimates:
## ratio of variances 
##              6.041 
## 
## 
## vr.tst> var.test(lm(x ~ 1), lm(y ~ 1))  # The same.
## 
## 	F test to compare two variances
## 
## data:  lm(x ~ 1) and lm(y ~ 1)
## F = 6.041, num df = 49, denom df = 29, p-value = 1.954e-06
## alternative hypothesis: true ratio of variances is not equal to 1
## 95 percent confidence interval:
##   3.035 11.366
## sample estimates:
## ratio of variances 
##              6.041
```


Now use the function on the vectors created above and determine whether the variances are significantly different or not.

Keep this in hand for using any functions.
