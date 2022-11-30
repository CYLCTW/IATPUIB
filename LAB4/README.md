## 1. Сколько встроенных в пакет nycflights13 датафреймов?

    library(dplyr)

    ## 
    ## Attaching package: 'dplyr'

    ## The following objects are masked from 'package:stats':
    ## 
    ##     filter, lag

    ## The following objects are masked from 'package:base':
    ## 
    ##     intersect, setdiff, setequal, union

    a<-nycflights13::airlines
    b<-nycflights13::airports
    c<-nycflights13::flights
    d<-nycflights13::planes
    e<-nycflights13::weather
    list<-list(a,b,c,d,e )
    list[1]

    ## [[1]]
    ## # A tibble: 16 × 2
    ##    carrier name                       
    ##    <chr>   <chr>                      
    ##  1 9E      Endeavor Air Inc.          
    ##  2 AA      American Airlines Inc.     
    ##  3 AS      Alaska Airlines Inc.       
    ##  4 B6      JetBlue Airways            
    ##  5 DL      Delta Air Lines Inc.       
    ##  6 EV      ExpressJet Airlines Inc.   
    ##  7 F9      Frontier Airlines Inc.     
    ##  8 FL      AirTran Airways Corporation
    ##  9 HA      Hawaiian Airlines Inc.     
    ## 10 MQ      Envoy Air                  
    ## 11 OO      SkyWest Airlines Inc.      
    ## 12 UA      United Air Lines Inc.      
    ## 13 US      US Airways Inc.            
    ## 14 VX      Virgin America             
    ## 15 WN      Southwest Airlines Co.     
    ## 16 YV      Mesa Airlines Inc.

    list[2]

    ## [[1]]
    ## # A tibble: 1,458 × 8
    ##    faa   name                             lat    lon   alt    tz dst   tzone    
    ##    <chr> <chr>                          <dbl>  <dbl> <dbl> <dbl> <chr> <chr>    
    ##  1 04G   Lansdowne Airport               41.1  -80.6  1044    -5 A     America/…
    ##  2 06A   Moton Field Municipal Airport   32.5  -85.7   264    -6 A     America/…
    ##  3 06C   Schaumburg Regional             42.0  -88.1   801    -6 A     America/…
    ##  4 06N   Randall Airport                 41.4  -74.4   523    -5 A     America/…
    ##  5 09J   Jekyll Island Airport           31.1  -81.4    11    -5 A     America/…
    ##  6 0A9   Elizabethton Municipal Airport  36.4  -82.2  1593    -5 A     America/…
    ##  7 0G6   Williams County Airport         41.5  -84.5   730    -5 A     America/…
    ##  8 0G7   Finger Lakes Regional Airport   42.9  -76.8   492    -5 A     America/…
    ##  9 0P2   Shoestring Aviation Airfield    39.8  -76.6  1000    -5 U     America/…
    ## 10 0S9   Jefferson County Intl           48.1 -123.    108    -8 A     America/…
    ## # … with 1,448 more rows

    list[3]

    ## [[1]]
    ## # A tibble: 336,776 × 19
    ##     year month   day dep_time sched_de…¹ dep_d…² arr_t…³ sched…⁴ arr_d…⁵ carrier
    ##    <int> <int> <int>    <int>      <int>   <dbl>   <int>   <int>   <dbl> <chr>  
    ##  1  2013     1     1      517        515       2     830     819      11 UA     
    ##  2  2013     1     1      533        529       4     850     830      20 UA     
    ##  3  2013     1     1      542        540       2     923     850      33 AA     
    ##  4  2013     1     1      544        545      -1    1004    1022     -18 B6     
    ##  5  2013     1     1      554        600      -6     812     837     -25 DL     
    ##  6  2013     1     1      554        558      -4     740     728      12 UA     
    ##  7  2013     1     1      555        600      -5     913     854      19 B6     
    ##  8  2013     1     1      557        600      -3     709     723     -14 EV     
    ##  9  2013     1     1      557        600      -3     838     846      -8 B6     
    ## 10  2013     1     1      558        600      -2     753     745       8 AA     
    ## # … with 336,766 more rows, 9 more variables: flight <int>, tailnum <chr>,
    ## #   origin <chr>, dest <chr>, air_time <dbl>, distance <dbl>, hour <dbl>,
    ## #   minute <dbl>, time_hour <dttm>, and abbreviated variable names
    ## #   ¹​sched_dep_time, ²​dep_delay, ³​arr_time, ⁴​sched_arr_time, ⁵​arr_delay

    list[4]

    ## [[1]]
    ## # A tibble: 3,322 × 9
    ##    tailnum  year type                   manuf…¹ model engines seats speed engine
    ##    <chr>   <int> <chr>                  <chr>   <chr>   <int> <int> <int> <chr> 
    ##  1 N10156   2004 Fixed wing multi engi… EMBRAER EMB-…       2    55    NA Turbo…
    ##  2 N102UW   1998 Fixed wing multi engi… AIRBUS… A320…       2   182    NA Turbo…
    ##  3 N103US   1999 Fixed wing multi engi… AIRBUS… A320…       2   182    NA Turbo…
    ##  4 N104UW   1999 Fixed wing multi engi… AIRBUS… A320…       2   182    NA Turbo…
    ##  5 N10575   2002 Fixed wing multi engi… EMBRAER EMB-…       2    55    NA Turbo…
    ##  6 N105UW   1999 Fixed wing multi engi… AIRBUS… A320…       2   182    NA Turbo…
    ##  7 N107US   1999 Fixed wing multi engi… AIRBUS… A320…       2   182    NA Turbo…
    ##  8 N108UW   1999 Fixed wing multi engi… AIRBUS… A320…       2   182    NA Turbo…
    ##  9 N109UW   1999 Fixed wing multi engi… AIRBUS… A320…       2   182    NA Turbo…
    ## 10 N110UW   1999 Fixed wing multi engi… AIRBUS… A320…       2   182    NA Turbo…
    ## # … with 3,312 more rows, and abbreviated variable name ¹​manufacturer

    list[5]

    ## [[1]]
    ## # A tibble: 26,115 × 15
    ##    origin  year month   day  hour  temp  dewp humid wind_dir wind_speed wind_g…¹
    ##    <chr>  <int> <int> <int> <int> <dbl> <dbl> <dbl>    <dbl>      <dbl>    <dbl>
    ##  1 EWR     2013     1     1     1  39.0  26.1  59.4      270      10.4        NA
    ##  2 EWR     2013     1     1     2  39.0  27.0  61.6      250       8.06       NA
    ##  3 EWR     2013     1     1     3  39.0  28.0  64.4      240      11.5        NA
    ##  4 EWR     2013     1     1     4  39.9  28.0  62.2      250      12.7        NA
    ##  5 EWR     2013     1     1     5  39.0  28.0  64.4      260      12.7        NA
    ##  6 EWR     2013     1     1     6  37.9  28.0  67.2      240      11.5        NA
    ##  7 EWR     2013     1     1     7  39.0  28.0  64.4      240      15.0        NA
    ##  8 EWR     2013     1     1     8  39.9  28.0  62.2      250      10.4        NA
    ##  9 EWR     2013     1     1     9  39.9  28.0  62.2      260      15.0        NA
    ## 10 EWR     2013     1     1    10  41    28.0  59.6      260      13.8        NA
    ## # … with 26,105 more rows, 4 more variables: precip <dbl>, pressure <dbl>,
    ## #   visib <dbl>, time_hour <dttm>, and abbreviated variable name ¹​wind_gust

    length(list)

    ## [1] 5

## 2. Сколько строк в каждом датафрейме?

    df<-as.data.frame(list[1])
    df%>% nrow()

    ## [1] 16

    df<-as.data.frame(list[2])
    df%>% nrow()

    ## [1] 1458

    df<-as.data.frame(list[3])
    df%>% nrow()

    ## [1] 336776

    df<-as.data.frame(list[4])
    df%>% nrow()

    ## [1] 3322

    df<-as.data.frame(list[5])
    df%>% nrow()

    ## [1] 26115

## 3. Сколько столбцов в каждом датафрейме?

    df<-as.data.frame(list[1])
    df%>% ncol()

    ## [1] 2

    df<-as.data.frame(list[2])
    df%>% ncol()

    ## [1] 8

    df<-as.data.frame(list[3])
    df%>% ncol()

    ## [1] 19

    df<-as.data.frame(list[4])
    df%>% ncol()

    ## [1] 9

    df<-as.data.frame(list[5])
    df%>% ncol()

    ## [1] 15

## 4. Как просмотреть примерный вид датафрейма?

    df<-as.data.frame(list[1])
    df%>% glimpse()

    ## Rows: 16
    ## Columns: 2
    ## $ carrier <chr> "9E", "AA", "AS", "B6", "DL", "EV", "F9", "FL", "HA", "MQ", "O…
    ## $ name    <chr> "Endeavor Air Inc.", "American Airlines Inc.", "Alaska Airline…

    df<-as.data.frame(list[2])
    df%>% glimpse()

    ## Rows: 1,458
    ## Columns: 8
    ## $ faa   <chr> "04G", "06A", "06C", "06N", "09J", "0A9", "0G6", "0G7", "0P2", "…
    ## $ name  <chr> "Lansdowne Airport", "Moton Field Municipal Airport", "Schaumbur…
    ## $ lat   <dbl> 41.13047, 32.46057, 41.98934, 41.43191, 31.07447, 36.37122, 41.4…
    ## $ lon   <dbl> -80.61958, -85.68003, -88.10124, -74.39156, -81.42778, -82.17342…
    ## $ alt   <dbl> 1044, 264, 801, 523, 11, 1593, 730, 492, 1000, 108, 409, 875, 10…
    ## $ tz    <dbl> -5, -6, -6, -5, -5, -5, -5, -5, -5, -8, -5, -6, -5, -5, -5, -5, …
    ## $ dst   <chr> "A", "A", "A", "A", "A", "A", "A", "A", "U", "A", "A", "U", "A",…
    ## $ tzone <chr> "America/New_York", "America/Chicago", "America/Chicago", "Ameri…

    df<-as.data.frame(list[3])
    df%>% glimpse()

    ## Rows: 336,776
    ## Columns: 19
    ## $ year           <int> 2013, 2013, 2013, 2013, 2013, 2013, 2013, 2013, 2013, 2…
    ## $ month          <int> 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1…
    ## $ day            <int> 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1…
    ## $ dep_time       <int> 517, 533, 542, 544, 554, 554, 555, 557, 557, 558, 558, …
    ## $ sched_dep_time <int> 515, 529, 540, 545, 600, 558, 600, 600, 600, 600, 600, …
    ## $ dep_delay      <dbl> 2, 4, 2, -1, -6, -4, -5, -3, -3, -2, -2, -2, -2, -2, -1…
    ## $ arr_time       <int> 830, 850, 923, 1004, 812, 740, 913, 709, 838, 753, 849,…
    ## $ sched_arr_time <int> 819, 830, 850, 1022, 837, 728, 854, 723, 846, 745, 851,…
    ## $ arr_delay      <dbl> 11, 20, 33, -18, -25, 12, 19, -14, -8, 8, -2, -3, 7, -1…
    ## $ carrier        <chr> "UA", "UA", "AA", "B6", "DL", "UA", "B6", "EV", "B6", "…
    ## $ flight         <int> 1545, 1714, 1141, 725, 461, 1696, 507, 5708, 79, 301, 4…
    ## $ tailnum        <chr> "N14228", "N24211", "N619AA", "N804JB", "N668DN", "N394…
    ## $ origin         <chr> "EWR", "LGA", "JFK", "JFK", "LGA", "EWR", "EWR", "LGA",…
    ## $ dest           <chr> "IAH", "IAH", "MIA", "BQN", "ATL", "ORD", "FLL", "IAD",…
    ## $ air_time       <dbl> 227, 227, 160, 183, 116, 150, 158, 53, 140, 138, 149, 1…
    ## $ distance       <dbl> 1400, 1416, 1089, 1576, 762, 719, 1065, 229, 944, 733, …
    ## $ hour           <dbl> 5, 5, 5, 5, 6, 5, 6, 6, 6, 6, 6, 6, 6, 6, 6, 5, 6, 6, 6…
    ## $ minute         <dbl> 15, 29, 40, 45, 0, 58, 0, 0, 0, 0, 0, 0, 0, 0, 0, 59, 0…
    ## $ time_hour      <dttm> 2013-01-01 05:00:00, 2013-01-01 05:00:00, 2013-01-01 0…

    df<-as.data.frame(list[4])
    df%>% glimpse()

    ## Rows: 3,322
    ## Columns: 9
    ## $ tailnum      <chr> "N10156", "N102UW", "N103US", "N104UW", "N10575", "N105UW…
    ## $ year         <int> 2004, 1998, 1999, 1999, 2002, 1999, 1999, 1999, 1999, 199…
    ## $ type         <chr> "Fixed wing multi engine", "Fixed wing multi engine", "Fi…
    ## $ manufacturer <chr> "EMBRAER", "AIRBUS INDUSTRIE", "AIRBUS INDUSTRIE", "AIRBU…
    ## $ model        <chr> "EMB-145XR", "A320-214", "A320-214", "A320-214", "EMB-145…
    ## $ engines      <int> 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, …
    ## $ seats        <int> 55, 182, 182, 182, 55, 182, 182, 182, 182, 182, 55, 55, 5…
    ## $ speed        <int> NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, N…
    ## $ engine       <chr> "Turbo-fan", "Turbo-fan", "Turbo-fan", "Turbo-fan", "Turb…

    df<-as.data.frame(list[5])
    df%>% glimpse()

    ## Rows: 26,115
    ## Columns: 15
    ## $ origin     <chr> "EWR", "EWR", "EWR", "EWR", "EWR", "EWR", "EWR", "EWR", "EW…
    ## $ year       <int> 2013, 2013, 2013, 2013, 2013, 2013, 2013, 2013, 2013, 2013,…
    ## $ month      <int> 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1,…
    ## $ day        <int> 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1,…
    ## $ hour       <int> 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 13, 14, 15, 16, 17, 18, …
    ## $ temp       <dbl> 39.02, 39.02, 39.02, 39.92, 39.02, 37.94, 39.02, 39.92, 39.…
    ## $ dewp       <dbl> 26.06, 26.96, 28.04, 28.04, 28.04, 28.04, 28.04, 28.04, 28.…
    ## $ humid      <dbl> 59.37, 61.63, 64.43, 62.21, 64.43, 67.21, 64.43, 62.21, 62.…
    ## $ wind_dir   <dbl> 270, 250, 240, 250, 260, 240, 240, 250, 260, 260, 260, 330,…
    ## $ wind_speed <dbl> 10.35702, 8.05546, 11.50780, 12.65858, 12.65858, 11.50780, …
    ## $ wind_gust  <dbl> NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, 20.…
    ## $ precip     <dbl> 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,…
    ## $ pressure   <dbl> 1012.0, 1012.3, 1012.5, 1012.2, 1011.9, 1012.4, 1012.2, 101…
    ## $ visib      <dbl> 10, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10,…
    ## $ time_hour  <dttm> 2013-01-01 01:00:00, 2013-01-01 02:00:00, 2013-01-01 03:00…

## 5. Сколько компаний-перевозчиков (carrier) учитывают эти наборы данных (представлено в наборах данных)?

    df<-as.data.frame(list[1])
    length(unique(df$carrier))

    ## [1] 16

## 6. Сколько рейсов принял аэропорт John F Kennedy Intl в мае?

    df<-as.data.frame(list[2])
    df2<-as.data.frame(list[3])
    airport<-"John F Kennedy Intl"
    airport<-df[which(df$name==airport),1]
    month<-5
    df2<-df2[which(df2$dest==airport & df2$month==month),1]
    length(df2)

    ## [1] 0

## 7. Какой самый северный аэропорт?

    df<-as.data.frame(list[2])
    airport<-df[which.max(df$lat),2]
    airport

    ## [1] "Dillant Hopkins Airport"

## 8. Какой аэропорт самый высокогорный (находится выше всех над уровнем моря)?

    df<-as.data.frame(list[2])
    airport2<-df[which.max(df$alt),2]
    airport2

    ## [1] "Telluride"

## 9. Какие бортовые номера у самых старых самолетов?

    df<-as.data.frame(list[4])
    df<-df[,c("tailnum","year")]
    df<-df[order(df$year),]
    df<-df%>%head(10)
    for(i in 1:nrow(df))
      df[ i, 2] <- 2022-df[ i, 2]
    colnames(df) <- c("Number", "Age")
    df

    ##      Number Age
    ## 1038 N381AA  66
    ## 425  N201AA  63
    ## 1695 N567AA  63
    ## 1028 N378AA  59
    ## 1726 N575AA  59
    ## 192  N14629  57
    ## 1868 N615AA  55
    ## 1191 N425AA  54
    ## 1046 N383AA  50
    ## 894  N364AA  49

## 10. Какая средняя температура воздуха была в сентябре в аэропорту John F Kennedy Intl (в градусах Цельсия).

    df<-as.data.frame(list[5])
    df<-df[which(df$origin==airport & df$month==9),]
    df<-df[,c("origin","month","temp")]
    for(i in 1:nrow(df))
      df[ i, 3] <- 5/9*(df[ i, 3]-32)
    df%>%summarise(mean_temp = mean(temp))

    ##   mean_temp
    ## 1        NA

## 11. Самолеты какой авиакомпании совершили больше всего вылетов в июне?

    df<-as.data.frame(list[3])
    df<-df[,c("tailnum","month")]
    df<-df[which(df$month==6),]
    df<-df%>%group_by(df$tailnum)
    df2<-as.data.frame(list[4])
    df<-merge(df, df2)
    df<-df[,c("tailnum","manufacturer")]
    df<-df%>%count(manufacturer,sort=TRUE)
    df%>%head(1)

    ##   manufacturer    n
    ## 1       BOEING 7085

## 12. Самолеты какой авиакомпании задерживались чаще других в 2013 году?

    df<-as.data.frame(list[3])
    df<-df[,c("tailnum","year","dep_delay")]
    df<-df[which(df$year==2013 & df$dep_delay>0),]
    df2<-as.data.frame(list[4])
    df<-merge(df, df2)
    df<-df[,c("tailnum","manufacturer")]
    df<-df%>%count(manufacturer,sort=TRUE)
    df%>%head(1)

    ##   manufacturer   n
    ## 1       BOEING 864
