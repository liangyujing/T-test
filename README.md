t.test(holland,mu=178)  #（data，null H 规定的mean）
t.test(holland, france)   #sequences are independent
t.test(male,female,paired=TRUE)  #sequences are paired

## 得到T值和自由度，求概率Pr
#问题：Pr(t4>2.1318)
a = pt(2.1318,4, lower.tail = F)， 或者a = 1-pt(2.1318,4)
#问题：Pr(|t6|>2.6122)
b = 2*pt(2.6122,6, lower.tail = F)，或者c = 2*(1-pt(2,3))
#一次性很多个：df = c(1,2,4,10,30) 
e = pt(3,df,lower.tail = F)
