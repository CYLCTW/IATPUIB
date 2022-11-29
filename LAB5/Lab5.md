## Подготовка данных 1.. Импортируйте данные DNS

    library(dplyr)

    ## 
    ## Attaching package: 'dplyr'

    ## The following objects are masked from 'package:stats':
    ## 
    ##     filter, lag

    ## The following objects are masked from 'package:base':
    ## 
    ##     intersect, setdiff, setequal, union

    inf = read.csv("dns.log", header = FALSE,sep = "\t",encoding = "UTF-8")

## 2. Добавьте пропущенные данные о структуре данных (назначении столбцов)

    head=read.csv("header.csv", header = TRUE)

    field<-head[,1]
    inf = read.csv("dns.log", header = FALSE,sep = "\t",encoding = "UTF-8")
    names(inf)<-field

## 3. Преобразуйте данные в столбцах в нужный формат

## Анализ 4. Сколько участников информационного обмена в сети Доброй Организации?

    orig_ip<-unique(inf$`orig_ip `)
    resp_ip<-unique(inf$`resp_ip `)
    all_ip<-merge(orig_ip,resp_ip)
    NROW(unique(all_ip$`x`))

    ## [1] 253

## 5. Какое соотношение участников обмена внутри сети и участников обращений к внешним ресурсам?count(inf\[grep(“192.168.202.87”,inf)\])

    m51<-unique(inf$`orig_ip `,sort=TRUE)
    m52<-unique(inf$`resp_ip `,sort=TRUE)
    new_vector <- c(m51, m52)
    new_vector<-new_vector[!duplicated(new_vector)]
    lall=length(new_vector)
    l1=length(unique(grep(paste("192.168",collapse="|"), 
                            new_vector, value=TRUE)))
    l2=lall-l1
    contr=l1/l2
    contr

    ## [1] 10.2314

## 6. Найдите топ-10 участников сети, проявляющих наибольшую сетевую активность.

    m1<-inf%>%
    count(inf$`orig_ip `,sort=TRUE)
    colnames(m1) <- c("Person", "count")
    m2<-inf%>%
    count(inf$`resp_ip `,sort=TRUE)
    colnames(m2) <- c("Person", "count")
    mm<-rbind(m1,m2)
    mm<-mm %>%
      group_by(Person) %>%
      summarise(count)

    ## `summarise()` has grouped output by 'Person'. You can override using the
    ## `.groups` argument.

    mm<-mm[order(mm$Person, decreasing = TRUE), ]   
    mm

    ## # A tibble: 1,483 × 2
    ## # Groups:   Person [1,359]
    ##    Person                    count
    ##    <chr>                     <int>
    ##  1 ff02::fb                   3298
    ##  2 ff02::1:3                 14411
    ##  3 fec0:0:0:ffff::3             44
    ##  4 fec0:0:0:ffff::2             47
    ##  5 fec0:0:0:ffff::1             47
    ##  6 fe80::f2de:f1ff:fe9b:ad6a    30
    ##  7 fe80::d840:5635:ef48:b032   276
    ##  8 fe80::d69a:20ff:fef9:b49c   141
    ##  9 fe80::d69a:20ff:fef9:b49c     2
    ## 10 fe80::c62c:3ff:fe37:efc     126
    ## # … with 1,473 more rows

## 7. Найдите топ-10 доменов, к которым обращаются пользователи сети и соответственное количество обращений

    m7<-inf%>%
    count(inf$`query `,sort=TRUE)
    m7head<-m7%>%
    head(10)
    m7head

    ##                                                               inf$`query `
    ## 1                                                teredo.ipv6.microsoft.com
    ## 2                                                         tools.google.com
    ## 3                                                            www.apple.com
    ## 4                                                           time.apple.com
    ## 5                                          safebrowsing.clients.google.com
    ## 6  *\\x00\\x00\\x00\\x00\\x00\\x00\\x00\\x00\\x00\\x00\\x00\\x00\\x00\\x00
    ## 7                                                                     WPAD
    ## 8                                              44.206.168.192.in-addr.arpa
    ## 9                                                                 HPE8AA67
    ## 10                                                                  ISATAP
    ##        n
    ## 1  39273
    ## 2  14057
    ## 3  13390
    ## 4  13109
    ## 5  11658
    ## 6  10401
    ## 7   9134
    ## 8   7248
    ## 9   6929
    ## 10  6569

## 8. Опеределите базовые статистические характеристики (функция summary()) интервала времени между последовательным обращениями к топ-10 доменам.

    m7head%>%summary()

    ##  inf$`query `             n        
    ##  Length:10          Min.   : 6569  
    ##  Class :character   1st Qu.: 7720  
    ##  Mode  :character   Median :11030  
    ##                     Mean   :13177  
    ##                     3rd Qu.:13320  
    ##                     Max.   :39273

## 9. Часто вредоносное программное обеспечение использует DNS канал в качестве канала управления, периодически отправляя запросы на подконтрольный злоумышленникам DNS сервер. По периодическим запросам на один и тот же домен можно выявить скрытый DNS канал. Есть ли такие IP адреса в исследуемом датасете?

## Обогащение данных 10. Определите местоположение (страну, город) и организацию-провайдера для топ-10 доменов. Для этого можно использовать сторонние сервисы, например <https://v4.ifconfig.co/>.
