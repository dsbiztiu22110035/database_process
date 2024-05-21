# database_process

---
title: "database_process"
output: html_document
date: "2024-05-21"
---

```{r}
library(tidyverse)

d <- data.frame(
  name = c("太郎", "花子", "三郎", "良子", "次郎", "桜子", "四郎", "松子", "愛子"),
  school = c("南", "南", "南", "南", "南", "東", "東", "東", "東"),
  teacher = c("竹田", "竹田", "竹田", "竹田",  "佐藤", "佐藤", "佐藤", "鈴木", "鈴木"),
  gender = c("男", "女", "男", "女", "男", "女", "男", "女", "女"),
  math = c(4, 3, 2, 4, 3, 4, 5, 4, 5),
  reading = c(1, 5, 2, 4, 5, 4, 1, 5, 4) )

library(DT)

datatable(d)


d |> select(name,math)



d |> select(-gender)



d |> slice(3:6)
  


d |> arrange(name)

  

d |> arrange(desc(math))

  

d |> arrange(desc(math),desc(reading))
  
  

d |> select(name,reading)

  

d |> summarise(mean(math))
  
  

d |> group_by(teacher) |> summarize(mean(math))

  

d |> filter(gender=='女') |> select(-school,-teacher)
  
  

d |> filter(school=='南',gender=='男') |> select(name,school,teacher,gender,math,reading)



d |> group_by(teacher) |> filter(n()>=3) |> select(name,school,teacher,gender,math,reading)

  

d |> mutate(total=math+reading)


d |> mutate(math100=math*20)


```