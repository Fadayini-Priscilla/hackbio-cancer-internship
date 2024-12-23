\# Set seed for reproducibility

set.seed(1001)

x1 = 1:100+rnorm(100, mean=0, sd=15)

y1 = 1:100

\# Scatterplot with title, axis label, and correlation coefficient

plot(x1, y1, main = "Scatterplot of x1 and y1", xlab = "x1", ylab = "y1")

cor(x1, y1)

mtext(text=paste("Correlation Coefficient:", cor(x1, y1)), side = 3)

plot(x1, y1, main = "Scatterplot of x1 and y1", xlab = "x1", ylab = "y1", col = "red")

plot(x1, y1, main = "Scatterplot of x1 and y1", xlab = "x1", ylab = "y1", col = "red", pch = 18)

mtext(text=paste("Correlation Coefficient:", cor(x1, y1)), side = 3)

\# Histogram of x1

hist(x1, main = "Histogram of x1", xlab = "x1", ylab = "Frequency", col = "skyblue", border = "black")

\# Box plot of y1

boxplot(y1, main = "Boxplot of y1")

\# Boxplots of x1 and y1 on the same plot

boxplot(x1, y1, names = c("x1", "y1"), main = "Boxplots of x1 and y1")

\# Horizontal box plot of x1 and y1 together

boxplot(x1, y1, names = c("x1", "y1"), horizontal = TRUE, main = "Boxplots of x1 and y1")

\# Multiple plots in a 2x1 layout

par(mfrow = c(1, 2))

boxplot(x1, main = "Boxplot of x1")

hist(x1, main = "Histogram of x1", xlab = "x1", ylab = "Frequency", col = "skyblue", border = "black")


