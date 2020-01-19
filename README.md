# t.test

t.test(holland,mu=178)  #（data，null H 规定的mean）
t.test(prejudice, mu = 0, alternative = "two.sided")

t.test(holland, france)   #sequences are independent
t.test(liedetection, prejudice, alternative = "two.sided", var.equal = FALSE)

t.test(male,female,paired=TRUE)  #sequences are paired

# lm
#Main effect of valence, prediction: positive > negative 
#Independent 2-group t-test
Ttest_AT<- lm(my_data_age_T$value~my_data_age_T$valence, alternative = "two.sided")
sum_Ttest_AT<- summary(Ttest_AT)

## two.sided
# one-sample
##R function to compute one-sample t-test:
t.test(prejudice, mu = 0, alternative = "two.sided")
## two-samples t-test comparing the means of two independent samples (x & y)
t.test(liedetection, prejudice, alternative = "two.sided", var.equal = FALSE)

## one-tailed
# one sample
##if you want to test whether the mean weight of mice is less than 25g (one-tailed test), type this:
t.test(my_data$weight, mu = 25,alternative = "less")
##if you want to test whether the mean weight of mice is greater than 25g (one-tailed test), type this:
t.test(my_data$weight, mu = 25,alternative = "greater")
# two sample
##if you want to test whether the average men’s weight is less than the average women’s weight, type this:
t.test(weight ~ group, data = my_data,
         var.equal = TRUE, alternative = "less")
##if you want to test whether the average men’s weight is greater than the average women’s weight, type this
t.test(weight ~ group, data = my_data,
       var.equal = TRUE, alternative = "greater")

# Graph: Plot weight by group and color by group
library("ggpubr")
ggboxplot(my_data, x = "group", y = "weight", 
          color = "group", palette = c("#00AFBB", "#E7B800"),
          ylab = "Weight", xlab = "Groups")

## Preleminary test to check independent t-test assumptions
http://www.sthda.com/english/wiki/unpaired-two-samples-t-test-in-r
#Assumption 1: Are the two samples independents?      Yes, since the samples from men and women are not related.
#Assumtion 2: Are the data from each of the 2 groups follow a normal distribution?
#Assumption 3. Do the two populations have the same variances?

## 得到T值和自由度，求概率Pr
#问题：Pr(t4>2.1318)
a = pt(2.1318,4, lower.tail = F)， 或者a = 1-pt(2.1318,4)
#问题：Pr(|t6|>2.6122)
b = 2*pt(2.6122,6, lower.tail = F)，或者c = 2*(1-pt(2,3))
#一次性很多个：df = c(1,2,4,10,30) 
e = pt(3,df,lower.tail = F)


