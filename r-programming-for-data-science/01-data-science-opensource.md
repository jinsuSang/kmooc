# 데이터 과학과 오픈소스

## 데이터 분석

- 데이터 curation : 데이터 추출 변환 (SQL, R, Python)
- 데이터 visualization : 그래픽
- 통계모형, 인공지능 : 머신러닝, 회귀분석

## R 프로그램

- 오픈소스 통계분석 프로그램
- 빅데이터 분석 도구
- 통계 기법 및 시각화 도구(ggplot) 제공

- 다른 프로그래밍 언어와 쉽게 연동

## R 코드

- `class()` : 범주 구하기
- `is.numeric()`, `is.integer()`, `is.vector()` :  범주에 속하는지 체크
- `help()`, `help.search()`: help menu  사용, R 함수 검색

```R
  x1<-c(1,3,5,7,9)
  
  # x1 is numeric or character?
  class(x1)
  is.numeric(x1)
  
  # x1 is a integer?
  is.integer(x1)
  
  # need to define as.integer as.numeric as.character
  x2<-as.integer(x1)
  
  # length of x1
  length(x1)
  
  # x1 is a vector?
  is.vector(x1)
  
  # class - 범주 구하기
  "I like apple"
  class("I like apple")
  class(x1)
  class(x2)

  #help menu
  
  help(factor)
  
  help(boxplot)
  
  # R 함수 검색
  help.search("linear")
  
```

##  기본 스크립트와 추가 패키지

- `plot()` : 산점도
- `rm()`: object 삭제
- `rnorm(n, mean, std)`: 정규분포로부터 랜덤 데이터 생성 함수
- `install.package()`: 패키지 설치
- `library()`: 패키지 가져오기, 패키지 사용 전 필수

```R
# Basic operations
  
  x2<-c(1,4,9)
  sqrt(x2)  # 제곱근
  min(x2)   # 최소값 
  max(x2)   # 최대값
  mean(x2)  # 평균균
  
  y2=2+x2
  
  plot(x2, y2) # 산점도
  
  # functions
  
  log10(10) # 로그
  log(10) 
  log2(10)
  exp(10)   # 지수분포
  sin(pi/2)
  
  # list : 현재 생성된 데이터 나열
  ls()
  
  # remove object
  rm(x1)
  
  # change to lower or upper case for variable (name)
  
  c1 <- "MiXeD cAsE 123"
  tolower(c1)
  toupper(c1)
  
  # generating data from distributions
  # 100 values from normal distribution with mean=0, sd=1
  # rnorm(n, mean, std)
  x3<-rnorm(100) # 정규분포로부터 랜덤 데이터 생성 함수
  head(x3)
  mean(x3)
  sd(x3)
  min(x3)
  max(x3)
  
  hist(x3)
  
  # 10000 values from normal distribution with mean=0, sd=1
  x4<-rnorm(100000)
  mean(x4)
  sd(x4)
  
  hist(x4)
  
 
# install package 
  
install.packages("ggplot2")
library(ggplot2)
help(ggplot2)
    
# install scatterplot3d
    
install.packages("scatterplot3d")
library(scatterplot3d)
help(scatterplot3d)
    
# example program using scatterplot3d
z <- seq(-10, 10, 0.01)
x <- cos(z)  
y <- sin(z)
scatterplot3d(x, y, z, highlight.3d=TRUE, col.axis="blue",
                  col.grid="lightblue", main="scatterplot3d - 1", pch=20)
  
help(scatterplot3d)
  
    
# to find out the package in google 
# example 1 : support vector machine
    
# step1 : install package
install.packages('e1071')
library(e1071)
    
# step2 
help.search("support vector")
help.search("linear")
```

