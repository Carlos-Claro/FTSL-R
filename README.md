# FTSL-R
Minicurso de R para analise e gestão financeira

https://www.r-project.org/

Download: https://cran-r.c3sl.ufpr.br/ 

http://www.angelfire.com/un/cde/CALCULA_TIR.R

uso:
$~ R
> usa como calculadora
> 12/100->i
> i
[1] 0.12
> -100+40/1+i
[1] -59.88
> 40/(1+i)
[1] 35.71429
> -100+40/(1+i)
[1] -64.28571
> -100+40/(1+i)+50/(1+i)^2
[1] -24.42602
> -100+40/(1+i)+50/(1+i)^2+60/(1+i)^3
[1] 18.28079
> i=30/100
> -100+40/(1+i)+50/(1+i)^2+60/(1+i)^3
[1] -12.335
> i
[1] 0.3
> i=6/100
> -100+40/(1+i)+50/(1+i)^2+60/(1+i)^3
[1] 32.61283
> projeto<-edit(data.frame())

> projeto
  var1 var2
1    0 -100
2    1   40
3    2   50
4    3   60
> colnames
colnames    colnames<-  
> colnames(projeto)<-c("fluxo","valor")
> projeto
  fluxo valor
1     0  -100
2     1    40
3     2    50
4     3    60
> i=12/100
> projeto2<-cbind(projeto,VAL=projeto$valor/(1+i)^projeto$fluxo)
> projeto2
  fluxo valor        VAL
1     0  -100 -100.00000
2     1    40   35.71429
3     2    50   39.85969
4     3    60   42.70681
> i=30/100
> i
[1] 0.3
> projeto3<-cbind(projeto,VAL=projeto$valor/(1+i)^projeto$fluxo)
> projeto3
  fluxo valor        VAL
1     0  -100 -100.00000
2     1    40   30.76923
3     2    50   29.58580
4     3    60   27.30997
> sum(projeto3$VAL)
[1] -12.335
> taxa=1:40
> taxa
 [1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25
[26] 26 27 28 29 30 31 32 33 34 35 36 37 38 39 40
{for(contador in seq(taxa))
+ {x<-sum(projeto$valor/(1+taxa[contador]/100)^projeto$fluxo)
+ ifelse(contador==1,val<-x,val<-c(val,x))}}
> val
 [1]  46.8541717  43.8134654  40.8732465  38.0291306  35.2769679  32.6128280
 [7]  30.0329866  27.5339125  25.1122562  22.7648385  20.4886406  18.2807945
[13]  16.1385740  14.0593867  12.0407660  10.0803641   8.1759451   6.3253789
[19]   4.5266352   2.7777778   1.0769598  -0.5775814  -2.1875287  -3.7544896
[25]  -5.2800000  -6.7655281  -8.2124778  -9.6221924 -10.9959570 -12.3350023
[31] -13.6405065 -14.9135988 -16.1553610 -17.3668304 -18.5490017 -19.7028292
[37] -20.8292288 -21.9290796 -23.0032257 -24.0524781
> length
length           length<-.factor  lengths          
length<-         length.POSIXlt   
> length(taxa)
[1] 40
> length(val
+ )
[1] 40
> plot(val~taxa,type="l",lwd=2,col="blue")
> abline(h=0)

