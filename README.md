# Stat-627-code
##Problem 4
**(a)**
```{r}
library(ISLR)
library("ggplot2")
data(College)
```

**(b)**
```{r}
summary(College)
```

**(c)**
```{r}
pairs(College[, 1:10])
```

**(d)**
```{r}
boxplot(College$Outstate ~ College$Private, xlab = "Private", ylab = "Outstate")
```

**(e)**
```{r}
Elite = rep("No", nrow(College))

Elite [College $ Top10perc > 50] = "Yes"
Elite = as.factor(Elite)
College = data.frame(College, Elite)
```

```{r}
summary(College$Elite)
```

**There are 78 "yes" and 699 "no"**

```{r}
boxplot(College$Outstate ~ College$Elite, xlab = "Elite", ylab = "Outstate")
```


**Histograms for College Apps**
```{r}
par(mfrow = c(2,2))
hist(College$Apps, breaks = 5, freq = TRUE, main = "Histogram for College Apps", xlab = "Apps")
hist(College$Apps, breaks = 10, freq = TRUE, main = "Histogram for College Apps", xlab = "Apps")
hist(College$Apps, breaks = 20, freq = TRUE, main = "Histogram for College Apps", xlab = "Apps")
hist(College$Apps, breaks = 50, freq = TRUE, main = "Histogram for College Apps", xlab = "Apps")
```

**Histograms for College Top 25 percent**
```{r}
par(mfrow = c(2,2))
hist(College$Top25perc, breaks = 5, freq = TRUE, main = "Histogram for College Top 25 Percent", xlab = "Top 25 percent")
hist(College$Top25perc, breaks = 10, freq = TRUE, main = "Histogram for College Top 25 Percent", xlab = "Top 25 percent")
hist(College$Top25perc, breaks = 20, freq = TRUE, main = "Histogram for College Top 25 Percent", xlab = "Top 25 percent")
hist(College$Top25perc, breaks = 50, freq = TRUE, main = "Histogram for College Top 25 Percent", xlab = "Top 25 percent")
```

**Histograms for College Outstate**
```{r}
par(mfrow = c(2,2))
hist(College$Outstate, breaks = 5, freq = TRUE, main = "Histogram for College Outstate", xlab = "Outstate")
hist(College$Outstate, breaks = 10, freq = TRUE, main = "Histogram for College Outstate", xlab = "Outstate")
hist(College$Outstate, breaks = 20, freq = TRUE, main = "Histogram for College Outstate", xlab = "Outstate")
hist(College$Outstate, breaks = 50, freq = TRUE, main = "Histogram for College Outstate", xlab = "Outstate")
```


**(g)**
```{r}
fit = lm(Enroll ~ Grad.Rate + PhD + Terminal + Room.Board + Books + Personal + Expend, College)

summary(fit)
```


##Problem 5

Least square line equation is: **y = b0_hat + b1_hat * x**

So for every x and y, **yi = b0_hat + b1_hat * xi**. 

So **sum(1:n)yi = n*b0_hat + b1_hat * sum(1:n)xi**, divided by n by both sizes, we get **(sum(1:n)yi)/n = b0_hat + b1_hat * sum(1:n)xi/n**

so **y_bar = b0_hat + b1_hat * x_bar**. So least square line always passes through point of averages**(x_bar, y_bar)**.
