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
    df[,c("tailnum","manufacturer")]

    ##      tailnum     manufacturer
    ## 1     N150UW           AIRBUS
    ## 2     N150UW           AIRBUS
    ## 3     N150UW           AIRBUS
    ## 4     N150UW           AIRBUS
    ## 5     N150UW           AIRBUS
    ## 6     N150UW           AIRBUS
    ## 7     N150UW           AIRBUS
    ## 8     N150UW           AIRBUS
    ## 9     N150UW           AIRBUS
    ## 10    N150UW           AIRBUS
    ## 11    N150UW           AIRBUS
    ## 12    N150UW           AIRBUS
    ## 13    N150UW           AIRBUS
    ## 14    N151UW           AIRBUS
    ## 15    N151UW           AIRBUS
    ## 16    N151UW           AIRBUS
    ## 17    N151UW           AIRBUS
    ## 18    N151UW           AIRBUS
    ## 19    N151UW           AIRBUS
    ## 20    N151UW           AIRBUS
    ## 21    N151UW           AIRBUS
    ## 22    N151UW           AIRBUS
    ## 23    N151UW           AIRBUS
    ## 24    N152UW           AIRBUS
    ## 25    N152UW           AIRBUS
    ## 26    N152UW           AIRBUS
    ## 27    N152UW           AIRBUS
    ## 28    N152UW           AIRBUS
    ## 29    N152UW           AIRBUS
    ## 30    N152UW           AIRBUS
    ## 31    N152UW           AIRBUS
    ## 32    N152UW           AIRBUS
    ## 33    N152UW           AIRBUS
    ## 34    N152UW           AIRBUS
    ## 35    N152UW           AIRBUS
    ## 36    N152UW           AIRBUS
    ## 37    N152UW           AIRBUS
    ## 38    N152UW           AIRBUS
    ## 39    N152UW           AIRBUS
    ## 40    N153UW           AIRBUS
    ## 41    N153UW           AIRBUS
    ## 42    N153UW           AIRBUS
    ## 43    N153UW           AIRBUS
    ## 44    N153UW           AIRBUS
    ## 45    N153UW           AIRBUS
    ## 46    N153UW           AIRBUS
    ## 47    N153UW           AIRBUS
    ## 48    N153UW           AIRBUS
    ## 49    N153UW           AIRBUS
    ## 50    N153UW           AIRBUS
    ## 51    N153UW           AIRBUS
    ## 52    N153UW           AIRBUS
    ## 53    N153UW           AIRBUS
    ## 54    N154UW           AIRBUS
    ## 55    N154UW           AIRBUS
    ## 56    N154UW           AIRBUS
    ## 57    N154UW           AIRBUS
    ## 58    N154UW           AIRBUS
    ## 59    N154UW           AIRBUS
    ## 60    N154UW           AIRBUS
    ## 61    N154UW           AIRBUS
    ## 62    N154UW           AIRBUS
    ## 63    N154UW           AIRBUS
    ## 64    N154UW           AIRBUS
    ## 65    N154UW           AIRBUS
    ## 66    N154UW           AIRBUS
    ## 67    N154UW           AIRBUS
    ## 68    N155UW           AIRBUS
    ## 69    N155UW           AIRBUS
    ## 70    N155UW           AIRBUS
    ## 71    N155UW           AIRBUS
    ## 72    N155UW           AIRBUS
    ## 73    N155UW           AIRBUS
    ## 74    N155UW           AIRBUS
    ## 75    N155UW           AIRBUS
    ## 76    N155UW           AIRBUS
    ## 77    N156UW           AIRBUS
    ## 78    N156UW           AIRBUS
    ## 79    N156UW           AIRBUS
    ## 80    N156UW           AIRBUS
    ## 81    N156UW           AIRBUS
    ## 82    N156UW           AIRBUS
    ## 83    N156UW           AIRBUS
    ## 84    N156UW           AIRBUS
    ## 85    N157UW           AIRBUS
    ## 86    N157UW           AIRBUS
    ## 87    N157UW           AIRBUS
    ## 88    N157UW           AIRBUS
    ## 89    N157UW           AIRBUS
    ## 90    N157UW           AIRBUS
    ## 91    N157UW           AIRBUS
    ## 92    N157UW           AIRBUS
    ## 93    N157UW           AIRBUS
    ## 94    N157UW           AIRBUS
    ## 95    N157UW           AIRBUS
    ## 96    N198UW           AIRBUS
    ## 97    N198UW           AIRBUS
    ## 98    N198UW           AIRBUS
    ## 99    N198UW           AIRBUS
    ## 100   N198UW           AIRBUS
    ## 101   N198UW           AIRBUS
    ## 102   N198UW           AIRBUS
    ## 103   N198UW           AIRBUS
    ## 104   N198UW           AIRBUS
    ## 105   N198UW           AIRBUS
    ## 106   N198UW           AIRBUS
    ## 107   N198UW           AIRBUS
    ## 108   N198UW           AIRBUS
    ## 109   N198UW           AIRBUS
    ## 110   N198UW           AIRBUS
    ## 111   N198UW           AIRBUS
    ## 112   N198UW           AIRBUS
    ## 113   N198UW           AIRBUS
    ## 114   N199UW           AIRBUS
    ## 115   N199UW           AIRBUS
    ## 116   N199UW           AIRBUS
    ## 117   N199UW           AIRBUS
    ## 118   N199UW           AIRBUS
    ## 119   N199UW           AIRBUS
    ## 120   N199UW           AIRBUS
    ## 121   N199UW           AIRBUS
    ## 122   N199UW           AIRBUS
    ## 123   N199UW           AIRBUS
    ## 124   N199UW           AIRBUS
    ## 125   N199UW           AIRBUS
    ## 126   N199UW           AIRBUS
    ## 127   N199UW           AIRBUS
    ## 128   N272PQ   BOMBARDIER INC
    ## 129   N272PQ   BOMBARDIER INC
    ## 130   N272PQ   BOMBARDIER INC
    ## 131   N272PQ   BOMBARDIER INC
    ## 132   N272PQ   BOMBARDIER INC
    ## 133   N272PQ   BOMBARDIER INC
    ## 134   N272PQ   BOMBARDIER INC
    ## 135   N272PQ   BOMBARDIER INC
    ## 136   N272PQ   BOMBARDIER INC
    ## 137   N272PQ   BOMBARDIER INC
    ## 138   N272PQ   BOMBARDIER INC
    ## 139   N272PQ   BOMBARDIER INC
    ## 140   N272PQ   BOMBARDIER INC
    ## 141   N272PQ   BOMBARDIER INC
    ## 142   N272PQ   BOMBARDIER INC
    ## 143   N272PQ   BOMBARDIER INC
    ## 144   N272PQ   BOMBARDIER INC
    ## 145   N27477           BOEING
    ## 146   N27477           BOEING
    ## 147   N27477           BOEING
    ## 148   N27477           BOEING
    ## 149   N27477           BOEING
    ## 150   N27477           BOEING
    ## 151   N27477           BOEING
    ## 152   N27477           BOEING
    ## 153   N27477           BOEING
    ## 154   N27477           BOEING
    ## 155   N27477           BOEING
    ## 156   N27477           BOEING
    ## 157   N27477           BOEING
    ## 158   N27477           BOEING
    ## 159   N27477           BOEING
    ## 160   N27477           BOEING
    ## 161   N27477           BOEING
    ## 162   N27477           BOEING
    ## 163   N27477           BOEING
    ## 164   N27477           BOEING
    ## 165   N27477           BOEING
    ## 166   N27477           BOEING
    ## 167   N27477           BOEING
    ## 168   N27477           BOEING
    ## 169   N279PQ   BOMBARDIER INC
    ## 170   N279PQ   BOMBARDIER INC
    ## 171   N279PQ   BOMBARDIER INC
    ## 172   N279PQ   BOMBARDIER INC
    ## 173   N279PQ   BOMBARDIER INC
    ## 174   N279PQ   BOMBARDIER INC
    ## 175   N279PQ   BOMBARDIER INC
    ## 176   N279PQ   BOMBARDIER INC
    ## 177   N279PQ   BOMBARDIER INC
    ## 178   N279PQ   BOMBARDIER INC
    ## 179   N279PQ   BOMBARDIER INC
    ## 180   N279PQ   BOMBARDIER INC
    ## 181   N279PQ   BOMBARDIER INC
    ## 182   N279PQ   BOMBARDIER INC
    ## 183   N279PQ   BOMBARDIER INC
    ## 184   N279PQ   BOMBARDIER INC
    ## 185   N279PQ   BOMBARDIER INC
    ## 186   N279PQ   BOMBARDIER INC
    ## 187   N279PQ   BOMBARDIER INC
    ## 188   N279PQ   BOMBARDIER INC
    ## 189   N279PQ   BOMBARDIER INC
    ## 190   N279PQ   BOMBARDIER INC
    ## 191   N279PQ   BOMBARDIER INC
    ## 192   N28478           BOEING
    ## 193   N28478           BOEING
    ## 194   N28478           BOEING
    ## 195   N28478           BOEING
    ## 196   N28478           BOEING
    ## 197   N28478           BOEING
    ## 198   N28478           BOEING
    ## 199   N28478           BOEING
    ## 200   N28478           BOEING
    ## 201   N28478           BOEING
    ## 202   N28478           BOEING
    ## 203   N28478           BOEING
    ## 204   N28478           BOEING
    ## 205   N28478           BOEING
    ## 206   N28478           BOEING
    ## 207   N28478           BOEING
    ## 208   N28478           BOEING
    ## 209   N28478           BOEING
    ## 210   N28478           BOEING
    ## 211   N28478           BOEING
    ## 212   N28478           BOEING
    ## 213   N28478           BOEING
    ## 214   N28478           BOEING
    ## 215   N28478           BOEING
    ## 216   N28478           BOEING
    ## 217   N28478           BOEING
    ## 218   N28478           BOEING
    ## 219   N28478           BOEING
    ## 220   N28478           BOEING
    ## 221   N28478           BOEING
    ## 222   N292PQ   BOMBARDIER INC
    ## 223   N292PQ   BOMBARDIER INC
    ## 224   N292PQ   BOMBARDIER INC
    ## 225   N292PQ   BOMBARDIER INC
    ## 226   N292PQ   BOMBARDIER INC
    ## 227   N292PQ   BOMBARDIER INC
    ## 228   N292PQ   BOMBARDIER INC
    ## 229   N292PQ   BOMBARDIER INC
    ## 230   N292PQ   BOMBARDIER INC
    ## 231   N292PQ   BOMBARDIER INC
    ## 232   N292PQ   BOMBARDIER INC
    ## 233   N292PQ   BOMBARDIER INC
    ## 234   N292PQ   BOMBARDIER INC
    ## 235   N292PQ   BOMBARDIER INC
    ## 236   N292PQ   BOMBARDIER INC
    ## 237   N292PQ   BOMBARDIER INC
    ## 238   N292PQ   BOMBARDIER INC
    ## 239   N292PQ   BOMBARDIER INC
    ## 240   N292PQ   BOMBARDIER INC
    ## 241   N292PQ   BOMBARDIER INC
    ## 242   N292PQ   BOMBARDIER INC
    ## 243   N292PQ   BOMBARDIER INC
    ## 244   N292PQ   BOMBARDIER INC
    ## 245   N292PQ   BOMBARDIER INC
    ## 246   N292PQ   BOMBARDIER INC
    ## 247   N292PQ   BOMBARDIER INC
    ## 248   N293PQ   BOMBARDIER INC
    ## 249   N293PQ   BOMBARDIER INC
    ## 250   N293PQ   BOMBARDIER INC
    ## 251   N293PQ   BOMBARDIER INC
    ## 252   N293PQ   BOMBARDIER INC
    ## 253   N293PQ   BOMBARDIER INC
    ## 254   N293PQ   BOMBARDIER INC
    ## 255   N293PQ   BOMBARDIER INC
    ## 256   N293PQ   BOMBARDIER INC
    ## 257   N293PQ   BOMBARDIER INC
    ## 258   N293PQ   BOMBARDIER INC
    ## 259   N293PQ   BOMBARDIER INC
    ## 260   N293PQ   BOMBARDIER INC
    ## 261   N293PQ   BOMBARDIER INC
    ## 262   N293PQ   BOMBARDIER INC
    ## 263   N293PQ   BOMBARDIER INC
    ## 264   N293PQ   BOMBARDIER INC
    ## 265   N293PQ   BOMBARDIER INC
    ## 266   N293PQ   BOMBARDIER INC
    ## 267   N293PQ   BOMBARDIER INC
    ## 268   N293PQ   BOMBARDIER INC
    ## 269   N293PQ   BOMBARDIER INC
    ## 270   N293PQ   BOMBARDIER INC
    ## 271   N294PQ   BOMBARDIER INC
    ## 272   N294PQ   BOMBARDIER INC
    ## 273   N294PQ   BOMBARDIER INC
    ## 274   N294PQ   BOMBARDIER INC
    ## 275   N294PQ   BOMBARDIER INC
    ## 276   N294PQ   BOMBARDIER INC
    ## 277   N294PQ   BOMBARDIER INC
    ## 278   N294PQ   BOMBARDIER INC
    ## 279   N294PQ   BOMBARDIER INC
    ## 280   N294PQ   BOMBARDIER INC
    ## 281   N294PQ   BOMBARDIER INC
    ## 282   N294PQ   BOMBARDIER INC
    ## 283   N294PQ   BOMBARDIER INC
    ## 284   N294PQ   BOMBARDIER INC
    ## 285   N295PQ   BOMBARDIER INC
    ## 286   N295PQ   BOMBARDIER INC
    ## 287   N295PQ   BOMBARDIER INC
    ## 288   N295PQ   BOMBARDIER INC
    ## 289   N295PQ   BOMBARDIER INC
    ## 290   N295PQ   BOMBARDIER INC
    ## 291   N295PQ   BOMBARDIER INC
    ## 292   N295PQ   BOMBARDIER INC
    ## 293   N295PQ   BOMBARDIER INC
    ## 294   N295PQ   BOMBARDIER INC
    ## 295   N295PQ   BOMBARDIER INC
    ## 296   N295PQ   BOMBARDIER INC
    ## 297   N295PQ   BOMBARDIER INC
    ## 298   N295PQ   BOMBARDIER INC
    ## 299   N295PQ   BOMBARDIER INC
    ## 300   N296PQ   BOMBARDIER INC
    ## 301   N296PQ   BOMBARDIER INC
    ## 302   N296PQ   BOMBARDIER INC
    ## 303   N296PQ   BOMBARDIER INC
    ## 304   N296PQ   BOMBARDIER INC
    ## 305   N296PQ   BOMBARDIER INC
    ## 306   N296PQ   BOMBARDIER INC
    ## 307   N296PQ   BOMBARDIER INC
    ## 308   N296PQ   BOMBARDIER INC
    ## 309   N296PQ   BOMBARDIER INC
    ## 310   N296PQ   BOMBARDIER INC
    ## 311   N296PQ   BOMBARDIER INC
    ## 312   N296PQ   BOMBARDIER INC
    ## 313   N296PQ   BOMBARDIER INC
    ## 314   N296PQ   BOMBARDIER INC
    ## 315   N296PQ   BOMBARDIER INC
    ## 316   N296PQ   BOMBARDIER INC
    ## 317   N296PQ   BOMBARDIER INC
    ## 318   N296PQ   BOMBARDIER INC
    ## 319   N296PQ   BOMBARDIER INC
    ## 320   N297PQ   BOMBARDIER INC
    ## 321   N297PQ   BOMBARDIER INC
    ## 322   N297PQ   BOMBARDIER INC
    ## 323   N297PQ   BOMBARDIER INC
    ## 324   N297PQ   BOMBARDIER INC
    ## 325   N297PQ   BOMBARDIER INC
    ## 326   N297PQ   BOMBARDIER INC
    ## 327   N297PQ   BOMBARDIER INC
    ## 328   N297PQ   BOMBARDIER INC
    ## 329   N297PQ   BOMBARDIER INC
    ## 330   N297PQ   BOMBARDIER INC
    ## 331   N297PQ   BOMBARDIER INC
    ## 332   N297PQ   BOMBARDIER INC
    ## 333   N298PQ   BOMBARDIER INC
    ## 334   N298PQ   BOMBARDIER INC
    ## 335   N298PQ   BOMBARDIER INC
    ## 336   N298PQ   BOMBARDIER INC
    ## 337   N298PQ   BOMBARDIER INC
    ## 338   N298PQ   BOMBARDIER INC
    ## 339   N298PQ   BOMBARDIER INC
    ## 340   N298PQ   BOMBARDIER INC
    ## 341   N298PQ   BOMBARDIER INC
    ## 342   N298PQ   BOMBARDIER INC
    ## 343   N298PQ   BOMBARDIER INC
    ## 344   N298PQ   BOMBARDIER INC
    ## 345   N298PQ   BOMBARDIER INC
    ## 346   N298PQ   BOMBARDIER INC
    ## 347   N298PQ   BOMBARDIER INC
    ## 348   N298PQ   BOMBARDIER INC
    ## 349   N299PQ   BOMBARDIER INC
    ## 350   N299PQ   BOMBARDIER INC
    ## 351   N299PQ   BOMBARDIER INC
    ## 352   N299PQ   BOMBARDIER INC
    ## 353   N299PQ   BOMBARDIER INC
    ## 354   N299PQ   BOMBARDIER INC
    ## 355   N299PQ   BOMBARDIER INC
    ## 356   N299PQ   BOMBARDIER INC
    ## 357   N299PQ   BOMBARDIER INC
    ## 358   N299PQ   BOMBARDIER INC
    ## 359   N354JB          EMBRAER
    ## 360   N354JB          EMBRAER
    ## 361   N354JB          EMBRAER
    ## 362   N354JB          EMBRAER
    ## 363   N354JB          EMBRAER
    ## 364   N354JB          EMBRAER
    ## 365   N354JB          EMBRAER
    ## 366   N354JB          EMBRAER
    ## 367   N354JB          EMBRAER
    ## 368   N354JB          EMBRAER
    ## 369   N354JB          EMBRAER
    ## 370   N354JB          EMBRAER
    ## 371   N354JB          EMBRAER
    ## 372   N354JB          EMBRAER
    ## 373   N354JB          EMBRAER
    ## 374   N354JB          EMBRAER
    ## 375   N354JB          EMBRAER
    ## 376   N354JB          EMBRAER
    ## 377   N354JB          EMBRAER
    ## 378   N354JB          EMBRAER
    ## 379   N354JB          EMBRAER
    ## 380   N354JB          EMBRAER
    ## 381   N354JB          EMBRAER
    ## 382   N354JB          EMBRAER
    ## 383   N354JB          EMBRAER
    ## 384   N354JB          EMBRAER
    ## 385   N354JB          EMBRAER
    ## 386   N354JB          EMBRAER
    ## 387   N354JB          EMBRAER
    ## 388   N354JB          EMBRAER
    ## 389   N354JB          EMBRAER
    ## 390   N354JB          EMBRAER
    ## 391   N354JB          EMBRAER
    ## 392   N354JB          EMBRAER
    ## 393   N354JB          EMBRAER
    ## 394   N354JB          EMBRAER
    ## 395   N354JB          EMBRAER
    ## 396   N354JB          EMBRAER
    ## 397   N354JB          EMBRAER
    ## 398   N354JB          EMBRAER
    ## 399   N354JB          EMBRAER
    ## 400   N354JB          EMBRAER
    ## 401   N354JB          EMBRAER
    ## 402   N354JB          EMBRAER
    ## 403   N354JB          EMBRAER
    ## 404   N354JB          EMBRAER
    ## 405   N354JB          EMBRAER
    ## 406   N354JB          EMBRAER
    ## 407   N354JB          EMBRAER
    ## 408   N354JB          EMBRAER
    ## 409   N354JB          EMBRAER
    ## 410   N354JB          EMBRAER
    ## 411   N354JB          EMBRAER
    ## 412   N354JB          EMBRAER
    ## 413   N354JB          EMBRAER
    ## 414   N354JB          EMBRAER
    ## 415   N354JB          EMBRAER
    ## 416   N354JB          EMBRAER
    ## 417   N354JB          EMBRAER
    ## 418   N354JB          EMBRAER
    ## 419   N354JB          EMBRAER
    ## 420   N354JB          EMBRAER
    ## 421   N354JB          EMBRAER
    ## 422   N354JB          EMBRAER
    ## 423   N354JB          EMBRAER
    ## 424   N354JB          EMBRAER
    ## 425   N354JB          EMBRAER
    ## 426   N354JB          EMBRAER
    ## 427   N354JB          EMBRAER
    ## 428   N354JB          EMBRAER
    ## 429   N354JB          EMBRAER
    ## 430   N354JB          EMBRAER
    ## 431   N354JB          EMBRAER
    ## 432   N354JB          EMBRAER
    ## 433   N354JB          EMBRAER
    ## 434   N354JB          EMBRAER
    ## 435   N354JB          EMBRAER
    ## 436   N354JB          EMBRAER
    ## 437   N354JB          EMBRAER
    ## 438   N354JB          EMBRAER
    ## 439   N354JB          EMBRAER
    ## 440   N354JB          EMBRAER
    ## 441   N354JB          EMBRAER
    ## 442   N354JB          EMBRAER
    ## 443   N354JB          EMBRAER
    ## 444   N354JB          EMBRAER
    ## 445   N354JB          EMBRAER
    ## 446   N354JB          EMBRAER
    ## 447   N354JB          EMBRAER
    ## 448   N354JB          EMBRAER
    ## 449   N354JB          EMBRAER
    ## 450   N354JB          EMBRAER
    ## 451   N354JB          EMBRAER
    ## 452   N354JB          EMBRAER
    ## 453   N354JB          EMBRAER
    ## 454   N354JB          EMBRAER
    ## 455   N354JB          EMBRAER
    ## 456   N354JB          EMBRAER
    ## 457   N354JB          EMBRAER
    ## 458   N354JB          EMBRAER
    ## 459   N354JB          EMBRAER
    ## 460   N354JB          EMBRAER
    ## 461   N354JB          EMBRAER
    ## 462   N354JB          EMBRAER
    ## 463   N354JB          EMBRAER
    ## 464   N355JB          EMBRAER
    ## 465   N355JB          EMBRAER
    ## 466   N355JB          EMBRAER
    ## 467   N355JB          EMBRAER
    ## 468   N355JB          EMBRAER
    ## 469   N355JB          EMBRAER
    ## 470   N355JB          EMBRAER
    ## 471   N355JB          EMBRAER
    ## 472   N355JB          EMBRAER
    ## 473   N355JB          EMBRAER
    ## 474   N355JB          EMBRAER
    ## 475   N355JB          EMBRAER
    ## 476   N355JB          EMBRAER
    ## 477   N355JB          EMBRAER
    ## 478   N355JB          EMBRAER
    ## 479   N355JB          EMBRAER
    ## 480   N355JB          EMBRAER
    ## 481   N355JB          EMBRAER
    ## 482   N355JB          EMBRAER
    ## 483   N355JB          EMBRAER
    ## 484   N355JB          EMBRAER
    ## 485   N355JB          EMBRAER
    ## 486   N355JB          EMBRAER
    ## 487   N355JB          EMBRAER
    ## 488   N355JB          EMBRAER
    ## 489   N355JB          EMBRAER
    ## 490   N355JB          EMBRAER
    ## 491   N355JB          EMBRAER
    ## 492   N355JB          EMBRAER
    ## 493   N355JB          EMBRAER
    ## 494   N355JB          EMBRAER
    ## 495   N355JB          EMBRAER
    ## 496   N355JB          EMBRAER
    ## 497   N355JB          EMBRAER
    ## 498   N355JB          EMBRAER
    ## 499   N355JB          EMBRAER
    ## 500   N355JB          EMBRAER
    ## 501   N355JB          EMBRAER
    ## 502   N355JB          EMBRAER
    ## 503   N355JB          EMBRAER
    ## 504   N355JB          EMBRAER
    ## 505   N355JB          EMBRAER
    ## 506   N355JB          EMBRAER
    ## 507   N355JB          EMBRAER
    ## 508   N355JB          EMBRAER
    ## 509   N355JB          EMBRAER
    ## 510   N355JB          EMBRAER
    ## 511   N355JB          EMBRAER
    ## 512   N355JB          EMBRAER
    ## 513   N355JB          EMBRAER
    ## 514   N355JB          EMBRAER
    ## 515   N355JB          EMBRAER
    ## 516   N355JB          EMBRAER
    ## 517   N355JB          EMBRAER
    ## 518   N355JB          EMBRAER
    ## 519   N355JB          EMBRAER
    ## 520   N355JB          EMBRAER
    ## 521   N355JB          EMBRAER
    ## 522   N355JB          EMBRAER
    ## 523   N355JB          EMBRAER
    ## 524   N355JB          EMBRAER
    ## 525   N355JB          EMBRAER
    ## 526   N355JB          EMBRAER
    ## 527   N355JB          EMBRAER
    ## 528   N355JB          EMBRAER
    ## 529   N355JB          EMBRAER
    ## 530   N355JB          EMBRAER
    ## 531   N355JB          EMBRAER
    ## 532   N355JB          EMBRAER
    ## 533   N355JB          EMBRAER
    ## 534   N355JB          EMBRAER
    ## 535   N355JB          EMBRAER
    ## 536   N355JB          EMBRAER
    ## 537   N355JB          EMBRAER
    ## 538   N355JB          EMBRAER
    ## 539   N355JB          EMBRAER
    ## 540   N355JB          EMBRAER
    ## 541   N355JB          EMBRAER
    ## 542   N355JB          EMBRAER
    ## 543   N355JB          EMBRAER
    ## 544   N355JB          EMBRAER
    ## 545   N355JB          EMBRAER
    ## 546   N355JB          EMBRAER
    ## 547   N355JB          EMBRAER
    ## 548   N355JB          EMBRAER
    ## 549   N355JB          EMBRAER
    ## 550   N355JB          EMBRAER
    ## 551   N355JB          EMBRAER
    ## 552   N355JB          EMBRAER
    ## 553   N355JB          EMBRAER
    ## 554   N355JB          EMBRAER
    ## 555   N355JB          EMBRAER
    ## 556   N355JB          EMBRAER
    ## 557   N355JB          EMBRAER
    ## 558   N355JB          EMBRAER
    ## 559   N355JB          EMBRAER
    ## 560   N355JB          EMBRAER
    ## 561   N355JB          EMBRAER
    ## 562   N355JB          EMBRAER
    ## 563   N355JB          EMBRAER
    ## 564   N355JB          EMBRAER
    ## 565   N355JB          EMBRAER
    ## 566   N355JB          EMBRAER
    ## 567   N355JB          EMBRAER
    ## 568   N358JB          EMBRAER
    ## 569   N358JB          EMBRAER
    ## 570   N358JB          EMBRAER
    ## 571   N358JB          EMBRAER
    ## 572   N358JB          EMBRAER
    ## 573   N358JB          EMBRAER
    ## 574   N358JB          EMBRAER
    ## 575   N358JB          EMBRAER
    ## 576   N358JB          EMBRAER
    ## 577   N358JB          EMBRAER
    ## 578   N358JB          EMBRAER
    ## 579   N358JB          EMBRAER
    ## 580   N358JB          EMBRAER
    ## 581   N358JB          EMBRAER
    ## 582   N358JB          EMBRAER
    ## 583   N358JB          EMBRAER
    ## 584   N358JB          EMBRAER
    ## 585   N358JB          EMBRAER
    ## 586   N358JB          EMBRAER
    ## 587   N358JB          EMBRAER
    ## 588   N358JB          EMBRAER
    ## 589   N358JB          EMBRAER
    ## 590   N358JB          EMBRAER
    ## 591   N358JB          EMBRAER
    ## 592   N358JB          EMBRAER
    ## 593   N358JB          EMBRAER
    ## 594   N358JB          EMBRAER
    ## 595   N358JB          EMBRAER
    ## 596   N358JB          EMBRAER
    ## 597   N358JB          EMBRAER
    ## 598   N358JB          EMBRAER
    ## 599   N358JB          EMBRAER
    ## 600   N358JB          EMBRAER
    ## 601   N358JB          EMBRAER
    ## 602   N358JB          EMBRAER
    ## 603   N358JB          EMBRAER
    ## 604   N358JB          EMBRAER
    ## 605   N358JB          EMBRAER
    ## 606   N358JB          EMBRAER
    ## 607   N358JB          EMBRAER
    ## 608   N358JB          EMBRAER
    ## 609   N358JB          EMBRAER
    ## 610   N358JB          EMBRAER
    ## 611   N358JB          EMBRAER
    ## 612   N358JB          EMBRAER
    ## 613   N358JB          EMBRAER
    ## 614   N358JB          EMBRAER
    ## 615   N358JB          EMBRAER
    ## 616   N358JB          EMBRAER
    ## 617   N358JB          EMBRAER
    ## 618   N358JB          EMBRAER
    ## 619   N358JB          EMBRAER
    ## 620   N358JB          EMBRAER
    ## 621   N358JB          EMBRAER
    ## 622   N358JB          EMBRAER
    ## 623   N358JB          EMBRAER
    ## 624   N358JB          EMBRAER
    ## 625   N358JB          EMBRAER
    ## 626   N358JB          EMBRAER
    ## 627   N358JB          EMBRAER
    ## 628   N358JB          EMBRAER
    ## 629   N358JB          EMBRAER
    ## 630   N358JB          EMBRAER
    ## 631   N358JB          EMBRAER
    ## 632   N358JB          EMBRAER
    ## 633   N358JB          EMBRAER
    ## 634   N358JB          EMBRAER
    ## 635   N358JB          EMBRAER
    ## 636   N358JB          EMBRAER
    ## 637   N361VA           AIRBUS
    ## 638   N361VA           AIRBUS
    ## 639   N361VA           AIRBUS
    ## 640   N361VA           AIRBUS
    ## 641   N361VA           AIRBUS
    ## 642   N361VA           AIRBUS
    ## 643   N361VA           AIRBUS
    ## 644   N361VA           AIRBUS
    ## 645   N361VA           AIRBUS
    ## 646   N361VA           AIRBUS
    ## 647   N361VA           AIRBUS
    ## 648   N361VA           AIRBUS
    ## 649   N361VA           AIRBUS
    ## 650   N361VA           AIRBUS
    ## 651   N361VA           AIRBUS
    ## 652   N361VA           AIRBUS
    ## 653   N361VA           AIRBUS
    ## 654   N361VA           AIRBUS
    ## 655   N36469           BOEING
    ## 656   N36469           BOEING
    ## 657   N36469           BOEING
    ## 658   N36469           BOEING
    ## 659   N36469           BOEING
    ## 660   N36469           BOEING
    ## 661   N36469           BOEING
    ## 662   N36469           BOEING
    ## 663   N36469           BOEING
    ## 664   N36469           BOEING
    ## 665   N36469           BOEING
    ## 666   N36469           BOEING
    ## 667   N36469           BOEING
    ## 668   N36469           BOEING
    ## 669   N36469           BOEING
    ## 670   N36469           BOEING
    ## 671   N36469           BOEING
    ## 672   N36469           BOEING
    ## 673   N36469           BOEING
    ## 674   N36469           BOEING
    ## 675   N36469           BOEING
    ## 676   N36469           BOEING
    ## 677   N36469           BOEING
    ## 678   N36469           BOEING
    ## 679   N36469           BOEING
    ## 680   N36469           BOEING
    ## 681   N36469           BOEING
    ## 682   N36469           BOEING
    ## 683   N36469           BOEING
    ## 684   N36469           BOEING
    ## 685   N36469           BOEING
    ## 686   N36469           BOEING
    ## 687   N36469           BOEING
    ## 688   N36469           BOEING
    ## 689   N36469           BOEING
    ## 690   N36469           BOEING
    ## 691   N36469           BOEING
    ## 692   N36469           BOEING
    ## 693   N36469           BOEING
    ## 694   N36469           BOEING
    ## 695   N36469           BOEING
    ## 696   N36469           BOEING
    ## 697   N36469           BOEING
    ## 698   N36469           BOEING
    ## 699   N36469           BOEING
    ## 700   N36469           BOEING
    ## 701   N36469           BOEING
    ## 702   N36469           BOEING
    ## 703   N36469           BOEING
    ## 704   N36469           BOEING
    ## 705   N36469           BOEING
    ## 706   N36469           BOEING
    ## 707   N36469           BOEING
    ## 708   N36469           BOEING
    ## 709   N36469           BOEING
    ## 710   N36469           BOEING
    ## 711   N36469           BOEING
    ## 712   N36469           BOEING
    ## 713   N36469           BOEING
    ## 714   N36469           BOEING
    ## 715   N36472           BOEING
    ## 716   N36472           BOEING
    ## 717   N36472           BOEING
    ## 718   N36472           BOEING
    ## 719   N36472           BOEING
    ## 720   N36472           BOEING
    ## 721   N36472           BOEING
    ## 722   N36472           BOEING
    ## 723   N36472           BOEING
    ## 724   N36472           BOEING
    ## 725   N36472           BOEING
    ## 726   N36472           BOEING
    ## 727   N36472           BOEING
    ## 728   N36472           BOEING
    ## 729   N36472           BOEING
    ## 730   N36472           BOEING
    ## 731   N36472           BOEING
    ## 732   N36472           BOEING
    ## 733   N36472           BOEING
    ## 734   N36472           BOEING
    ## 735   N36472           BOEING
    ## 736   N36472           BOEING
    ## 737   N36472           BOEING
    ## 738   N36472           BOEING
    ## 739   N36472           BOEING
    ## 740   N36472           BOEING
    ## 741   N36472           BOEING
    ## 742   N36472           BOEING
    ## 743   N36472           BOEING
    ## 744   N36472           BOEING
    ## 745   N36472           BOEING
    ## 746   N36472           BOEING
    ## 747   N36472           BOEING
    ## 748   N36472           BOEING
    ## 749   N36472           BOEING
    ## 750   N36472           BOEING
    ## 751   N36472           BOEING
    ## 752   N36472           BOEING
    ## 753   N36472           BOEING
    ## 754   N36472           BOEING
    ## 755   N36472           BOEING
    ## 756   N36472           BOEING
    ## 757   N36472           BOEING
    ## 758   N36472           BOEING
    ## 759   N36472           BOEING
    ## 760   N36472           BOEING
    ## 761   N36472           BOEING
    ## 762   N36472           BOEING
    ## 763   N36472           BOEING
    ## 764   N36472           BOEING
    ## 765   N36472           BOEING
    ## 766   N36472           BOEING
    ## 767   N36472           BOEING
    ## 768   N36472           BOEING
    ## 769   N36472           BOEING
    ## 770   N36472           BOEING
    ## 771   N36472           BOEING
    ## 772   N36472           BOEING
    ## 773   N36472           BOEING
    ## 774   N36472           BOEING
    ## 775   N36476           BOEING
    ## 776   N36476           BOEING
    ## 777   N36476           BOEING
    ## 778   N36476           BOEING
    ## 779   N36476           BOEING
    ## 780   N36476           BOEING
    ## 781   N36476           BOEING
    ## 782   N36476           BOEING
    ## 783   N36476           BOEING
    ## 784   N36476           BOEING
    ## 785   N36476           BOEING
    ## 786   N36476           BOEING
    ## 787   N36476           BOEING
    ## 788   N36476           BOEING
    ## 789   N36476           BOEING
    ## 790   N36476           BOEING
    ## 791   N36476           BOEING
    ## 792   N36476           BOEING
    ## 793   N36476           BOEING
    ## 794   N36476           BOEING
    ## 795   N36476           BOEING
    ## 796   N36476           BOEING
    ## 797   N36476           BOEING
    ## 798   N36476           BOEING
    ## 799   N36476           BOEING
    ## 800   N36476           BOEING
    ## 801   N36476           BOEING
    ## 802   N36476           BOEING
    ## 803   N36476           BOEING
    ## 804   N36476           BOEING
    ## 805   N36476           BOEING
    ## 806   N36476           BOEING
    ## 807   N36476           BOEING
    ## 808   N36476           BOEING
    ## 809   N36476           BOEING
    ## 810   N36476           BOEING
    ## 811   N36476           BOEING
    ## 812   N368JB          EMBRAER
    ## 813   N368JB          EMBRAER
    ## 814   N368JB          EMBRAER
    ## 815   N368JB          EMBRAER
    ## 816   N368JB          EMBRAER
    ## 817   N368JB          EMBRAER
    ## 818   N368JB          EMBRAER
    ## 819   N368JB          EMBRAER
    ## 820   N368JB          EMBRAER
    ## 821   N368JB          EMBRAER
    ## 822   N368JB          EMBRAER
    ## 823   N368JB          EMBRAER
    ## 824   N368JB          EMBRAER
    ## 825   N368JB          EMBRAER
    ## 826   N368JB          EMBRAER
    ## 827   N368JB          EMBRAER
    ## 828   N368JB          EMBRAER
    ## 829   N368JB          EMBRAER
    ## 830   N368JB          EMBRAER
    ## 831   N368JB          EMBRAER
    ## 832   N368JB          EMBRAER
    ## 833   N368JB          EMBRAER
    ## 834   N368JB          EMBRAER
    ## 835   N368JB          EMBRAER
    ## 836   N368JB          EMBRAER
    ## 837   N368JB          EMBRAER
    ## 838   N368JB          EMBRAER
    ## 839   N368JB          EMBRAER
    ## 840   N368JB          EMBRAER
    ## 841   N368JB          EMBRAER
    ## 842   N368JB          EMBRAER
    ## 843   N368JB          EMBRAER
    ## 844   N368JB          EMBRAER
    ## 845   N368JB          EMBRAER
    ## 846   N368JB          EMBRAER
    ## 847   N368JB          EMBRAER
    ## 848   N368JB          EMBRAER
    ## 849   N368JB          EMBRAER
    ## 850   N368JB          EMBRAER
    ## 851   N368JB          EMBRAER
    ## 852   N368JB          EMBRAER
    ## 853   N368JB          EMBRAER
    ## 854   N368JB          EMBRAER
    ## 855   N368JB          EMBRAER
    ## 856   N368JB          EMBRAER
    ## 857   N368JB          EMBRAER
    ## 858   N368JB          EMBRAER
    ## 859   N368JB          EMBRAER
    ## 860   N368JB          EMBRAER
    ## 861   N368JB          EMBRAER
    ## 862   N368JB          EMBRAER
    ## 863   N368JB          EMBRAER
    ## 864   N368JB          EMBRAER
    ## 865   N368JB          EMBRAER
    ## 866   N368JB          EMBRAER
    ## 867   N368JB          EMBRAER
    ## 868   N368JB          EMBRAER
    ## 869   N368JB          EMBRAER
    ## 870   N368JB          EMBRAER
    ## 871   N373JB          EMBRAER
    ## 872   N373JB          EMBRAER
    ## 873   N373JB          EMBRAER
    ## 874   N373JB          EMBRAER
    ## 875   N373JB          EMBRAER
    ## 876   N373JB          EMBRAER
    ## 877   N373JB          EMBRAER
    ## 878   N373JB          EMBRAER
    ## 879   N373JB          EMBRAER
    ## 880   N373JB          EMBRAER
    ## 881   N373JB          EMBRAER
    ## 882   N373JB          EMBRAER
    ## 883   N373JB          EMBRAER
    ## 884   N373JB          EMBRAER
    ## 885   N373JB          EMBRAER
    ## 886   N373JB          EMBRAER
    ## 887   N373JB          EMBRAER
    ## 888   N373JB          EMBRAER
    ## 889   N373JB          EMBRAER
    ## 890   N373JB          EMBRAER
    ## 891   N373JB          EMBRAER
    ## 892   N373JB          EMBRAER
    ## 893   N373JB          EMBRAER
    ## 894   N373JB          EMBRAER
    ## 895   N373JB          EMBRAER
    ## 896   N373JB          EMBRAER
    ## 897   N373JB          EMBRAER
    ## 898   N373JB          EMBRAER
    ## 899   N373JB          EMBRAER
    ## 900   N373JB          EMBRAER
    ## 901   N373JB          EMBRAER
    ## 902   N373JB          EMBRAER
    ## 903   N373JB          EMBRAER
    ## 904   N373JB          EMBRAER
    ## 905   N373JB          EMBRAER
    ## 906   N373JB          EMBRAER
    ## 907   N373JB          EMBRAER
    ## 908   N373JB          EMBRAER
    ## 909   N373JB          EMBRAER
    ## 910   N373JB          EMBRAER
    ## 911   N373JB          EMBRAER
    ## 912   N373JB          EMBRAER
    ## 913   N373JB          EMBRAER
    ## 914   N373JB          EMBRAER
    ## 915   N373JB          EMBRAER
    ## 916   N373JB          EMBRAER
    ## 917   N373JB          EMBRAER
    ## 918   N373JB          EMBRAER
    ## 919   N373JB          EMBRAER
    ## 920   N373JB          EMBRAER
    ## 921   N373JB          EMBRAER
    ## 922   N373JB          EMBRAER
    ## 923   N373JB          EMBRAER
    ## 924   N373JB          EMBRAER
    ## 925   N373JB          EMBRAER
    ## 926   N373JB          EMBRAER
    ## 927   N373JB          EMBRAER
    ## 928   N373JB          EMBRAER
    ## 929   N373JB          EMBRAER
    ## 930   N373JB          EMBRAER
    ## 931   N373JB          EMBRAER
    ## 932   N373JB          EMBRAER
    ## 933   N373JB          EMBRAER
    ## 934   N373JB          EMBRAER
    ## 935   N373JB          EMBRAER
    ## 936   N373JB          EMBRAER
    ## 937   N37465           BOEING
    ## 938   N37465           BOEING
    ## 939   N37465           BOEING
    ## 940   N37465           BOEING
    ## 941   N37465           BOEING
    ## 942   N37465           BOEING
    ## 943   N37465           BOEING
    ## 944   N37465           BOEING
    ## 945   N37465           BOEING
    ## 946   N37465           BOEING
    ## 947   N37465           BOEING
    ## 948   N37465           BOEING
    ## 949   N37465           BOEING
    ## 950   N37465           BOEING
    ## 951   N37465           BOEING
    ## 952   N37465           BOEING
    ## 953   N37465           BOEING
    ## 954   N37465           BOEING
    ## 955   N37465           BOEING
    ## 956   N37465           BOEING
    ## 957   N37465           BOEING
    ## 958   N37465           BOEING
    ## 959   N37465           BOEING
    ## 960   N37465           BOEING
    ## 961   N37465           BOEING
    ## 962   N37465           BOEING
    ## 963   N37465           BOEING
    ## 964   N37465           BOEING
    ## 965   N37465           BOEING
    ## 966   N37465           BOEING
    ## 967   N37465           BOEING
    ## 968   N37465           BOEING
    ## 969   N37465           BOEING
    ## 970   N37465           BOEING
    ## 971   N37465           BOEING
    ## 972   N37465           BOEING
    ## 973   N37465           BOEING
    ## 974   N37465           BOEING
    ## 975   N37465           BOEING
    ## 976   N37465           BOEING
    ## 977   N37465           BOEING
    ## 978   N37465           BOEING
    ## 979   N37465           BOEING
    ## 980   N37465           BOEING
    ## 981   N37465           BOEING
    ## 982   N37465           BOEING
    ## 983   N37465           BOEING
    ## 984   N37465           BOEING
    ## 985   N37465           BOEING
    ## 986   N37465           BOEING
    ## 987   N37465           BOEING
    ## 988   N37465           BOEING
    ## 989   N37465           BOEING
    ## 990   N37465           BOEING
    ## 991   N37465           BOEING
    ## 992   N37465           BOEING
    ## 993   N37465           BOEING
    ## 994   N37465           BOEING
    ## 995   N37465           BOEING
    ## 996   N37465           BOEING
    ## 997   N37465           BOEING
    ## 998   N37465           BOEING
    ## 999   N37465           BOEING
    ## 1000  N37465           BOEING
    ## 1001  N37465           BOEING
    ## 1002  N37465           BOEING
    ## 1003  N37466           BOEING
    ## 1004  N37466           BOEING
    ## 1005  N37466           BOEING
    ## 1006  N37466           BOEING
    ## 1007  N37466           BOEING
    ## 1008  N37466           BOEING
    ## 1009  N37466           BOEING
    ## 1010  N37466           BOEING
    ## 1011  N37466           BOEING
    ## 1012  N37466           BOEING
    ## 1013  N37466           BOEING
    ## 1014  N37466           BOEING
    ## 1015  N37466           BOEING
    ## 1016  N37466           BOEING
    ## 1017  N37466           BOEING
    ## 1018  N37466           BOEING
    ## 1019  N37466           BOEING
    ## 1020  N37466           BOEING
    ## 1021  N37466           BOEING
    ## 1022  N37466           BOEING
    ## 1023  N37466           BOEING
    ## 1024  N37466           BOEING
    ## 1025  N37466           BOEING
    ## 1026  N37466           BOEING
    ## 1027  N37466           BOEING
    ## 1028  N37466           BOEING
    ## 1029  N37466           BOEING
    ## 1030  N37466           BOEING
    ## 1031  N37466           BOEING
    ## 1032  N37466           BOEING
    ## 1033  N37466           BOEING
    ## 1034  N37466           BOEING
    ## 1035  N37466           BOEING
    ## 1036  N37466           BOEING
    ## 1037  N37466           BOEING
    ## 1038  N37466           BOEING
    ## 1039  N37466           BOEING
    ## 1040  N37466           BOEING
    ## 1041  N37466           BOEING
    ## 1042  N37466           BOEING
    ## 1043  N37466           BOEING
    ## 1044  N37466           BOEING
    ## 1045  N37466           BOEING
    ## 1046  N37466           BOEING
    ## 1047  N37466           BOEING
    ## 1048  N37466           BOEING
    ## 1049  N37466           BOEING
    ## 1050  N37466           BOEING
    ## 1051  N37466           BOEING
    ## 1052  N37466           BOEING
    ## 1053  N37466           BOEING
    ## 1054  N37466           BOEING
    ## 1055  N37466           BOEING
    ## 1056  N37466           BOEING
    ## 1057  N37466           BOEING
    ## 1058  N37466           BOEING
    ## 1059  N37466           BOEING
    ## 1060  N37466           BOEING
    ## 1061  N37466           BOEING
    ## 1062  N37466           BOEING
    ## 1063  N37466           BOEING
    ## 1064  N37468           BOEING
    ## 1065  N37468           BOEING
    ## 1066  N37468           BOEING
    ## 1067  N37468           BOEING
    ## 1068  N37468           BOEING
    ## 1069  N37468           BOEING
    ## 1070  N37468           BOEING
    ## 1071  N37468           BOEING
    ## 1072  N37468           BOEING
    ## 1073  N37468           BOEING
    ## 1074  N37468           BOEING
    ## 1075  N37468           BOEING
    ## 1076  N37468           BOEING
    ## 1077  N37468           BOEING
    ## 1078  N37468           BOEING
    ## 1079  N37468           BOEING
    ## 1080  N37468           BOEING
    ## 1081  N37468           BOEING
    ## 1082  N37468           BOEING
    ## 1083  N37468           BOEING
    ## 1084  N37468           BOEING
    ## 1085  N37468           BOEING
    ## 1086  N37468           BOEING
    ## 1087  N37468           BOEING
    ## 1088  N37468           BOEING
    ## 1089  N37468           BOEING
    ## 1090  N37468           BOEING
    ## 1091  N37468           BOEING
    ## 1092  N37468           BOEING
    ## 1093  N37468           BOEING
    ## 1094  N37468           BOEING
    ## 1095  N37468           BOEING
    ## 1096  N37468           BOEING
    ## 1097  N37468           BOEING
    ## 1098  N37468           BOEING
    ## 1099  N37468           BOEING
    ## 1100  N37468           BOEING
    ## 1101  N37468           BOEING
    ## 1102  N37468           BOEING
    ## 1103  N37468           BOEING
    ## 1104  N37468           BOEING
    ## 1105  N37468           BOEING
    ## 1106  N37468           BOEING
    ## 1107  N37468           BOEING
    ## 1108  N37468           BOEING
    ## 1109  N37468           BOEING
    ## 1110  N37468           BOEING
    ## 1111  N37468           BOEING
    ## 1112  N37468           BOEING
    ## 1113  N37468           BOEING
    ## 1114  N37468           BOEING
    ## 1115  N37468           BOEING
    ## 1116  N37468           BOEING
    ## 1117  N37468           BOEING
    ## 1118  N37468           BOEING
    ## 1119  N37468           BOEING
    ## 1120  N37468           BOEING
    ## 1121  N37468           BOEING
    ## 1122  N37468           BOEING
    ## 1123  N37468           BOEING
    ## 1124  N37468           BOEING
    ## 1125  N37470           BOEING
    ## 1126  N37470           BOEING
    ## 1127  N37470           BOEING
    ## 1128  N37470           BOEING
    ## 1129  N37470           BOEING
    ## 1130  N37470           BOEING
    ## 1131  N37470           BOEING
    ## 1132  N37470           BOEING
    ## 1133  N37470           BOEING
    ## 1134  N37470           BOEING
    ## 1135  N37470           BOEING
    ## 1136  N37470           BOEING
    ## 1137  N37470           BOEING
    ## 1138  N37470           BOEING
    ## 1139  N37470           BOEING
    ## 1140  N37470           BOEING
    ## 1141  N37470           BOEING
    ## 1142  N37470           BOEING
    ## 1143  N37470           BOEING
    ## 1144  N37470           BOEING
    ## 1145  N37470           BOEING
    ## 1146  N37470           BOEING
    ## 1147  N37470           BOEING
    ## 1148  N37470           BOEING
    ## 1149  N37470           BOEING
    ## 1150  N37470           BOEING
    ## 1151  N37470           BOEING
    ## 1152  N37470           BOEING
    ## 1153  N37470           BOEING
    ## 1154  N37470           BOEING
    ## 1155  N37470           BOEING
    ## 1156  N37470           BOEING
    ## 1157  N37470           BOEING
    ## 1158  N37470           BOEING
    ## 1159  N37470           BOEING
    ## 1160  N37470           BOEING
    ## 1161  N37470           BOEING
    ## 1162  N37470           BOEING
    ## 1163  N37470           BOEING
    ## 1164  N37470           BOEING
    ## 1165  N37470           BOEING
    ## 1166  N37470           BOEING
    ## 1167  N37470           BOEING
    ## 1168  N37470           BOEING
    ## 1169  N37470           BOEING
    ## 1170  N37470           BOEING
    ## 1171  N37470           BOEING
    ## 1172  N37470           BOEING
    ## 1173  N37471           BOEING
    ## 1174  N37471           BOEING
    ## 1175  N37471           BOEING
    ## 1176  N37471           BOEING
    ## 1177  N37471           BOEING
    ## 1178  N37471           BOEING
    ## 1179  N37471           BOEING
    ## 1180  N37471           BOEING
    ## 1181  N37471           BOEING
    ## 1182  N37471           BOEING
    ## 1183  N37471           BOEING
    ## 1184  N37471           BOEING
    ## 1185  N37471           BOEING
    ## 1186  N37471           BOEING
    ## 1187  N37471           BOEING
    ## 1188  N37471           BOEING
    ## 1189  N37471           BOEING
    ## 1190  N37471           BOEING
    ## 1191  N37471           BOEING
    ## 1192  N37471           BOEING
    ## 1193  N37471           BOEING
    ## 1194  N37471           BOEING
    ## 1195  N37471           BOEING
    ## 1196  N37471           BOEING
    ## 1197  N37471           BOEING
    ## 1198  N37471           BOEING
    ## 1199  N37471           BOEING
    ## 1200  N37471           BOEING
    ## 1201  N37471           BOEING
    ## 1202  N37471           BOEING
    ## 1203  N37471           BOEING
    ## 1204  N37471           BOEING
    ## 1205  N37471           BOEING
    ## 1206  N37471           BOEING
    ## 1207  N37471           BOEING
    ## 1208  N37471           BOEING
    ## 1209  N37471           BOEING
    ## 1210  N37471           BOEING
    ## 1211  N37471           BOEING
    ## 1212  N37471           BOEING
    ## 1213  N37471           BOEING
    ## 1214  N37471           BOEING
    ## 1215  N37471           BOEING
    ## 1216  N37471           BOEING
    ## 1217  N37471           BOEING
    ## 1218  N37471           BOEING
    ## 1219  N37471           BOEING
    ## 1220  N37471           BOEING
    ## 1221  N37471           BOEING
    ## 1222  N37471           BOEING
    ## 1223  N37471           BOEING
    ## 1224  N37471           BOEING
    ## 1225  N37471           BOEING
    ## 1226  N37471           BOEING
    ## 1227  N37471           BOEING
    ## 1228  N37471           BOEING
    ## 1229  N37471           BOEING
    ## 1230  N37471           BOEING
    ## 1231  N37471           BOEING
    ## 1232  N37471           BOEING
    ## 1233  N37471           BOEING
    ## 1234  N37471           BOEING
    ## 1235  N37471           BOEING
    ## 1236  N37471           BOEING
    ## 1237  N37474           BOEING
    ## 1238  N37474           BOEING
    ## 1239  N37474           BOEING
    ## 1240  N37474           BOEING
    ## 1241  N37474           BOEING
    ## 1242  N37474           BOEING
    ## 1243  N37474           BOEING
    ## 1244  N37474           BOEING
    ## 1245  N37474           BOEING
    ## 1246  N37474           BOEING
    ## 1247  N37474           BOEING
    ## 1248  N37474           BOEING
    ## 1249  N37474           BOEING
    ## 1250  N37474           BOEING
    ## 1251  N37474           BOEING
    ## 1252  N37474           BOEING
    ## 1253  N37474           BOEING
    ## 1254  N37474           BOEING
    ## 1255  N37474           BOEING
    ## 1256  N37474           BOEING
    ## 1257  N37474           BOEING
    ## 1258  N37474           BOEING
    ## 1259  N37474           BOEING
    ## 1260  N37474           BOEING
    ## 1261  N37474           BOEING
    ## 1262  N37474           BOEING
    ## 1263  N37474           BOEING
    ## 1264  N37474           BOEING
    ## 1265  N37474           BOEING
    ## 1266  N37474           BOEING
    ## 1267  N37474           BOEING
    ## 1268  N37474           BOEING
    ## 1269  N37474           BOEING
    ## 1270  N37474           BOEING
    ## 1271  N37474           BOEING
    ## 1272  N37474           BOEING
    ## 1273  N37474           BOEING
    ## 1274  N374JB          EMBRAER
    ## 1275  N374JB          EMBRAER
    ## 1276  N374JB          EMBRAER
    ## 1277  N374JB          EMBRAER
    ## 1278  N374JB          EMBRAER
    ## 1279  N374JB          EMBRAER
    ## 1280  N374JB          EMBRAER
    ## 1281  N374JB          EMBRAER
    ## 1282  N374JB          EMBRAER
    ## 1283  N374JB          EMBRAER
    ## 1284  N374JB          EMBRAER
    ## 1285  N374JB          EMBRAER
    ## 1286  N374JB          EMBRAER
    ## 1287  N374JB          EMBRAER
    ## 1288  N374JB          EMBRAER
    ## 1289  N374JB          EMBRAER
    ## 1290  N374JB          EMBRAER
    ## 1291  N374JB          EMBRAER
    ## 1292  N374JB          EMBRAER
    ## 1293  N374JB          EMBRAER
    ## 1294  N374JB          EMBRAER
    ## 1295  N374JB          EMBRAER
    ## 1296  N374JB          EMBRAER
    ## 1297  N374JB          EMBRAER
    ## 1298  N374JB          EMBRAER
    ## 1299  N374JB          EMBRAER
    ## 1300  N374JB          EMBRAER
    ## 1301  N374JB          EMBRAER
    ## 1302  N374JB          EMBRAER
    ## 1303  N374JB          EMBRAER
    ## 1304  N374JB          EMBRAER
    ## 1305  N374JB          EMBRAER
    ## 1306  N374JB          EMBRAER
    ## 1307  N374JB          EMBRAER
    ## 1308  N374JB          EMBRAER
    ## 1309  N374JB          EMBRAER
    ## 1310  N374JB          EMBRAER
    ## 1311  N374JB          EMBRAER
    ## 1312  N374JB          EMBRAER
    ## 1313  N374JB          EMBRAER
    ## 1314  N374JB          EMBRAER
    ## 1315  N374JB          EMBRAER
    ## 1316  N374JB          EMBRAER
    ## 1317  N374JB          EMBRAER
    ## 1318  N374JB          EMBRAER
    ## 1319  N374JB          EMBRAER
    ## 1320  N374JB          EMBRAER
    ## 1321  N374JB          EMBRAER
    ## 1322  N374JB          EMBRAER
    ## 1323  N374JB          EMBRAER
    ## 1324  N374JB          EMBRAER
    ## 1325  N374JB          EMBRAER
    ## 1326  N374JB          EMBRAER
    ## 1327  N374JB          EMBRAER
    ## 1328  N374JB          EMBRAER
    ## 1329  N374JB          EMBRAER
    ## 1330  N374JB          EMBRAER
    ## 1331  N374JB          EMBRAER
    ## 1332  N374JB          EMBRAER
    ## 1333  N374JB          EMBRAER
    ## 1334  N374JB          EMBRAER
    ## 1335  N374JB          EMBRAER
    ## 1336  N374JB          EMBRAER
    ## 1337  N374JB          EMBRAER
    ## 1338  N374JB          EMBRAER
    ## 1339  N374JB          EMBRAER
    ## 1340  N374JB          EMBRAER
    ## 1341  N374JB          EMBRAER
    ## 1342  N374JB          EMBRAER
    ## 1343  N374JB          EMBRAER
    ## 1344  N374JB          EMBRAER
    ## 1345  N374JB          EMBRAER
    ## 1346  N374JB          EMBRAER
    ## 1347  N374JB          EMBRAER
    ## 1348  N374JB          EMBRAER
    ## 1349  N374JB          EMBRAER
    ## 1350  N375JB          EMBRAER
    ## 1351  N375JB          EMBRAER
    ## 1352  N375JB          EMBRAER
    ## 1353  N375JB          EMBRAER
    ## 1354  N375JB          EMBRAER
    ## 1355  N375JB          EMBRAER
    ## 1356  N375JB          EMBRAER
    ## 1357  N375JB          EMBRAER
    ## 1358  N375JB          EMBRAER
    ## 1359  N375JB          EMBRAER
    ## 1360  N375JB          EMBRAER
    ## 1361  N375JB          EMBRAER
    ## 1362  N375JB          EMBRAER
    ## 1363  N375JB          EMBRAER
    ## 1364  N38467           BOEING
    ## 1365  N38467           BOEING
    ## 1366  N38467           BOEING
    ## 1367  N38467           BOEING
    ## 1368  N38467           BOEING
    ## 1369  N38467           BOEING
    ## 1370  N38467           BOEING
    ## 1371  N38467           BOEING
    ## 1372  N38467           BOEING
    ## 1373  N38467           BOEING
    ## 1374  N38467           BOEING
    ## 1375  N38467           BOEING
    ## 1376  N38467           BOEING
    ## 1377  N38467           BOEING
    ## 1378  N38467           BOEING
    ## 1379  N38467           BOEING
    ## 1380  N38467           BOEING
    ## 1381  N38467           BOEING
    ## 1382  N38467           BOEING
    ## 1383  N38467           BOEING
    ## 1384  N38467           BOEING
    ## 1385  N38467           BOEING
    ## 1386  N38467           BOEING
    ## 1387  N38467           BOEING
    ## 1388  N38467           BOEING
    ## 1389  N38467           BOEING
    ## 1390  N38467           BOEING
    ## 1391  N38467           BOEING
    ## 1392  N38467           BOEING
    ## 1393  N38467           BOEING
    ## 1394  N38467           BOEING
    ## 1395  N38467           BOEING
    ## 1396  N38467           BOEING
    ## 1397  N38467           BOEING
    ## 1398  N38467           BOEING
    ## 1399  N38467           BOEING
    ## 1400  N38467           BOEING
    ## 1401  N38467           BOEING
    ## 1402  N38467           BOEING
    ## 1403  N38467           BOEING
    ## 1404  N38467           BOEING
    ## 1405  N38467           BOEING
    ## 1406  N38467           BOEING
    ## 1407  N38467           BOEING
    ## 1408  N38467           BOEING
    ## 1409  N38473           BOEING
    ## 1410  N38473           BOEING
    ## 1411  N38473           BOEING
    ## 1412  N38473           BOEING
    ## 1413  N38473           BOEING
    ## 1414  N38473           BOEING
    ## 1415  N38473           BOEING
    ## 1416  N38473           BOEING
    ## 1417  N38473           BOEING
    ## 1418  N38473           BOEING
    ## 1419  N38473           BOEING
    ## 1420  N38473           BOEING
    ## 1421  N38473           BOEING
    ## 1422  N38473           BOEING
    ## 1423  N38473           BOEING
    ## 1424  N38473           BOEING
    ## 1425  N38473           BOEING
    ## 1426  N38473           BOEING
    ## 1427  N38473           BOEING
    ## 1428  N38473           BOEING
    ## 1429  N38473           BOEING
    ## 1430  N38473           BOEING
    ## 1431  N38473           BOEING
    ## 1432  N38473           BOEING
    ## 1433  N38473           BOEING
    ## 1434  N38473           BOEING
    ## 1435  N38473           BOEING
    ## 1436  N38473           BOEING
    ## 1437  N38473           BOEING
    ## 1438  N38473           BOEING
    ## 1439  N38473           BOEING
    ## 1440  N38473           BOEING
    ## 1441  N38473           BOEING
    ## 1442  N38473           BOEING
    ## 1443  N38473           BOEING
    ## 1444  N38473           BOEING
    ## 1445  N38473           BOEING
    ## 1446  N38473           BOEING
    ## 1447  N390HA           AIRBUS
    ## 1448  N390HA           AIRBUS
    ## 1449  N391HA           AIRBUS
    ## 1450  N391HA           AIRBUS
    ## 1451  N391HA           AIRBUS
    ## 1452  N392HA           AIRBUS
    ## 1453  N392HA           AIRBUS
    ## 1454  N393HA           AIRBUS
    ## 1455  N393HA           AIRBUS
    ## 1456  N39475           BOEING
    ## 1457  N39475           BOEING
    ## 1458  N39475           BOEING
    ## 1459  N39475           BOEING
    ## 1460  N39475           BOEING
    ## 1461  N39475           BOEING
    ## 1462  N39475           BOEING
    ## 1463  N39475           BOEING
    ## 1464  N39475           BOEING
    ## 1465  N39475           BOEING
    ## 1466  N39475           BOEING
    ## 1467  N39475           BOEING
    ## 1468  N39475           BOEING
    ## 1469  N39475           BOEING
    ## 1470  N39475           BOEING
    ## 1471  N39475           BOEING
    ## 1472  N39475           BOEING
    ## 1473  N39475           BOEING
    ## 1474  N39475           BOEING
    ## 1475  N39475           BOEING
    ## 1476  N39475           BOEING
    ## 1477  N39475           BOEING
    ## 1478  N39475           BOEING
    ## 1479  N39475           BOEING
    ## 1480  N39475           BOEING
    ## 1481  N39475           BOEING
    ## 1482  N39475           BOEING
    ## 1483  N39475           BOEING
    ## 1484  N39475           BOEING
    ## 1485  N39475           BOEING
    ## 1486  N39475           BOEING
    ## 1487  N39475           BOEING
    ## 1488  N39475           BOEING
    ## 1489  N39475           BOEING
    ## 1490  N39475           BOEING
    ## 1491  N39475           BOEING
    ## 1492  N39475           BOEING
    ## 1493  N39475           BOEING
    ## 1494  N39475           BOEING
    ## 1495  N39475           BOEING
    ## 1496  N39475           BOEING
    ## 1497  N395HA           AIRBUS
    ## 1498  N395HA           AIRBUS
    ## 1499  N409AS           BOEING
    ## 1500  N409AS           BOEING
    ## 1501  N409AS           BOEING
    ## 1502  N409AS           BOEING
    ## 1503  N409AS           BOEING
    ## 1504  N409AS           BOEING
    ## 1505  N409AS           BOEING
    ## 1506  N409AS           BOEING
    ## 1507  N409AS           BOEING
    ## 1508  N409AS           BOEING
    ## 1509  N409AS           BOEING
    ## 1510  N409AS           BOEING
    ## 1511  N413AS           BOEING
    ## 1512  N413AS           BOEING
    ## 1513  N413AS           BOEING
    ## 1514  N413AS           BOEING
    ## 1515  N413AS           BOEING
    ## 1516  N413AS           BOEING
    ## 1517  N413AS           BOEING
    ## 1518  N413AS           BOEING
    ## 1519  N413AS           BOEING
    ## 1520  N413AS           BOEING
    ## 1521  N413AS           BOEING
    ## 1522  N413AS           BOEING
    ## 1523  N419AS           BOEING
    ## 1524  N419AS           BOEING
    ## 1525  N419AS           BOEING
    ## 1526  N419AS           BOEING
    ## 1527  N419AS           BOEING
    ## 1528  N419AS           BOEING
    ## 1529  N419AS           BOEING
    ## 1530  N419AS           BOEING
    ## 1531  N419AS           BOEING
    ## 1532  N419AS           BOEING
    ## 1533  N419AS           BOEING
    ## 1534  N423AS           BOEING
    ## 1535  N423AS           BOEING
    ## 1536  N423AS           BOEING
    ## 1537  N423AS           BOEING
    ## 1538  N423AS           BOEING
    ## 1539  N423AS           BOEING
    ## 1540  N423AS           BOEING
    ## 1541  N423AS           BOEING
    ## 1542  N431AS           BOEING
    ## 1543  N433AS           BOEING
    ## 1544  N433AS           BOEING
    ## 1545  N440AS           BOEING
    ## 1546  N440AS           BOEING
    ## 1547  N440AS           BOEING
    ## 1548  N440AS           BOEING
    ## 1549  N440AS           BOEING
    ## 1550  N442AS           BOEING
    ## 1551  N442AS           BOEING
    ## 1552  N567UW           AIRBUS
    ## 1553  N567UW           AIRBUS
    ## 1554  N567UW           AIRBUS
    ## 1555  N567UW           AIRBUS
    ## 1556  N567UW           AIRBUS
    ## 1557  N567UW           AIRBUS
    ## 1558  N567UW           AIRBUS
    ## 1559  N567UW           AIRBUS
    ## 1560  N567UW           AIRBUS
    ## 1561  N567UW           AIRBUS
    ## 1562  N568UW           AIRBUS
    ## 1563  N568UW           AIRBUS
    ## 1564  N568UW           AIRBUS
    ## 1565  N569UW           AIRBUS
    ## 1566  N569UW           AIRBUS
    ## 1567  N569UW           AIRBUS
    ## 1568  N569UW           AIRBUS
    ## 1569  N569UW           AIRBUS
    ## 1570  N570UW           AIRBUS
    ## 1571  N570UW           AIRBUS
    ## 1572  N570UW           AIRBUS
    ## 1573  N571UW           AIRBUS
    ## 1574  N571UW           AIRBUS
    ## 1575  N571UW           AIRBUS
    ## 1576  N571UW           AIRBUS
    ## 1577  N571UW           AIRBUS
    ## 1578  N572UW AIRBUS INDUSTRIE
    ## 1579  N64809           BOEING
    ## 1580  N64809           BOEING
    ## 1581  N64809           BOEING
    ## 1582  N64809           BOEING
    ## 1583  N66803           BOEING
    ## 1584  N66803           BOEING
    ## 1585  N66803           BOEING
    ## 1586  N66803           BOEING
    ## 1587  N66803           BOEING
    ## 1588  N66803           BOEING
    ## 1589  N66803           BOEING
    ## 1590  N66808           BOEING
    ## 1591  N66808           BOEING
    ## 1592  N66808           BOEING
    ## 1593  N66808           BOEING
    ## 1594  N66808           BOEING
    ## 1595  N66808           BOEING
    ## 1596  N66808           BOEING
    ## 1597  N66808           BOEING
    ## 1598  N66808           BOEING
    ## 1599  N66808           BOEING
    ## 1600  N66808           BOEING
    ## 1601  N66808           BOEING
    ## 1602  N66808           BOEING
    ## 1603  N66808           BOEING
    ## 1604  N66808           BOEING
    ## 1605  N66808           BOEING
    ## 1606  N68801           BOEING
    ## 1607  N68801           BOEING
    ## 1608  N68801           BOEING
    ## 1609  N68801           BOEING
    ## 1610  N68801           BOEING
    ## 1611  N68801           BOEING
    ## 1612  N68801           BOEING
    ## 1613  N68801           BOEING
    ## 1614  N68801           BOEING
    ## 1615  N68801           BOEING
    ## 1616  N68801           BOEING
    ## 1617  N68801           BOEING
    ## 1618  N68801           BOEING
    ## 1619  N68802           BOEING
    ## 1620  N68802           BOEING
    ## 1621  N68802           BOEING
    ## 1622  N68802           BOEING
    ## 1623  N68802           BOEING
    ## 1624  N68802           BOEING
    ## 1625  N68802           BOEING
    ## 1626  N68802           BOEING
    ## 1627  N68802           BOEING
    ## 1628  N68802           BOEING
    ## 1629  N68805           BOEING
    ## 1630  N68805           BOEING
    ## 1631  N68805           BOEING
    ## 1632  N68805           BOEING
    ## 1633  N68805           BOEING
    ## 1634  N68805           BOEING
    ## 1635  N68805           BOEING
    ## 1636  N68805           BOEING
    ## 1637  N68805           BOEING
    ## 1638  N68805           BOEING
    ## 1639  N68805           BOEING
    ## 1640  N68805           BOEING
    ## 1641  N68805           BOEING
    ## 1642  N68807           BOEING
    ## 1643  N68807           BOEING
    ## 1644  N68807           BOEING
    ## 1645  N68807           BOEING
    ## 1646  N68807           BOEING
    ## 1647  N69804           BOEING
    ## 1648  N69804           BOEING
    ## 1649  N69804           BOEING
    ## 1650  N69804           BOEING
    ## 1651  N69804           BOEING
    ## 1652  N69804           BOEING
    ## 1653  N69804           BOEING
    ## 1654  N69804           BOEING
    ## 1655  N69804           BOEING
    ## 1656  N69804           BOEING
    ## 1657  N69804           BOEING
    ## 1658  N69804           BOEING
    ## 1659  N69804           BOEING
    ## 1660  N69804           BOEING
    ## 1661  N69804           BOEING
    ## 1662  N69804           BOEING
    ## 1663  N69806           BOEING
    ## 1664  N69806           BOEING
    ## 1665  N69806           BOEING
    ## 1666  N69806           BOEING
    ## 1667  N69806           BOEING
    ## 1668  N69806           BOEING
    ## 1669  N69806           BOEING
    ## 1670  N827JB           AIRBUS
    ## 1671  N827JB           AIRBUS
    ## 1672  N827JB           AIRBUS
    ## 1673  N827JB           AIRBUS
    ## 1674  N827JB           AIRBUS
    ## 1675  N827JB           AIRBUS
    ## 1676  N827JB           AIRBUS
    ## 1677  N827JB           AIRBUS
    ## 1678  N827JB           AIRBUS
    ## 1679  N827JB           AIRBUS
    ## 1680  N827JB           AIRBUS
    ## 1681  N827JB           AIRBUS
    ## 1682  N827JB           AIRBUS
    ## 1683  N827JB           AIRBUS
    ## 1684  N827JB           AIRBUS
    ## 1685  N827JB           AIRBUS
    ## 1686  N827JB           AIRBUS
    ## 1687  N827JB           AIRBUS
    ## 1688  N827JB           AIRBUS
    ## 1689  N827JB           AIRBUS
    ## 1690  N827JB           AIRBUS
    ## 1691  N827JB           AIRBUS
    ## 1692  N827JB           AIRBUS
    ## 1693  N827JB           AIRBUS
    ## 1694  N827JB           AIRBUS
    ## 1695  N827JB           AIRBUS
    ## 1696  N827JB           AIRBUS
    ## 1697  N827JB           AIRBUS
    ## 1698  N827JB           AIRBUS
    ## 1699  N827JB           AIRBUS
    ## 1700  N827JB           AIRBUS
    ## 1701  N827JB           AIRBUS
    ## 1702  N827JB           AIRBUS
    ## 1703  N827JB           AIRBUS
    ## 1704  N827JB           AIRBUS
    ## 1705  N827JB           AIRBUS
    ## 1706  N827JB           AIRBUS
    ## 1707  N827JB           AIRBUS
    ## 1708  N827JB           AIRBUS
    ## 1709  N827JB           AIRBUS
    ## 1710  N827JB           AIRBUS
    ## 1711  N827JB           AIRBUS
    ## 1712  N827JB           AIRBUS
    ## 1713  N827JB           AIRBUS
    ## 1714  N827JB           AIRBUS
    ## 1715  N827JB           AIRBUS
    ## 1716  N827JB           AIRBUS
    ## 1717  N828JB           AIRBUS
    ## 1718  N828JB           AIRBUS
    ## 1719  N828JB           AIRBUS
    ## 1720  N828JB           AIRBUS
    ## 1721  N828JB           AIRBUS
    ## 1722  N828JB           AIRBUS
    ## 1723  N828JB           AIRBUS
    ## 1724  N828JB           AIRBUS
    ## 1725  N828JB           AIRBUS
    ## 1726  N828JB           AIRBUS
    ## 1727  N828JB           AIRBUS
    ## 1728  N828JB           AIRBUS
    ## 1729  N828JB           AIRBUS
    ## 1730  N834JB           AIRBUS
    ## 1731  N834JB           AIRBUS
    ## 1732  N834JB           AIRBUS
    ## 1733  N834JB           AIRBUS
    ## 1734  N834JB           AIRBUS
    ## 1735  N834JB           AIRBUS
    ## 1736  N834JB           AIRBUS
    ## 1737  N834JB           AIRBUS
    ## 1738  N834JB           AIRBUS
    ## 1739  N834JB           AIRBUS
    ## 1740  N834JB           AIRBUS
    ## 1741  N834JB           AIRBUS
    ## 1742  N834JB           AIRBUS
    ## 1743  N834JB           AIRBUS
    ## 1744  N834JB           AIRBUS
    ## 1745  N834JB           AIRBUS
    ## 1746  N834JB           AIRBUS
    ## 1747  N8607M           BOEING
    ## 1748  N8607M           BOEING
    ## 1749  N8607M           BOEING
    ## 1750  N8607M           BOEING
    ## 1751  N8607M           BOEING
    ## 1752  N8607M           BOEING
    ## 1753  N8608N           BOEING
    ## 1754  N8608N           BOEING
    ## 1755  N8608N           BOEING
    ## 1756  N8608N           BOEING
    ## 1757  N8608N           BOEING
    ## 1758  N8608N           BOEING
    ## 1759  N8608N           BOEING
    ## 1760  N8609A           BOEING
    ## 1761  N8609A           BOEING
    ## 1762  N8609A           BOEING
    ## 1763  N8609A           BOEING
    ## 1764  N8610A           BOEING
    ## 1765  N8610A           BOEING
    ## 1766  N8610A           BOEING
    ## 1767  N8610A           BOEING
    ## 1768  N8611F           BOEING
    ## 1769  N8611F           BOEING
    ## 1770  N8611F           BOEING
    ## 1771  N8611F           BOEING
    ## 1772  N8611F           BOEING
    ## 1773  N8612K           BOEING
    ## 1774  N8613K           BOEING
    ## 1775  N8613K           BOEING
    ## 1776  N8613K           BOEING
    ## 1777  N8613K           BOEING
    ## 1778  N8614M           BOEING
    ## 1779  N8614M           BOEING
    ## 1780  N8614M           BOEING
    ## 1781  N8615E           BOEING
    ## 1782  N8615E           BOEING
    ## 1783  N8616C           BOEING
    ## 1784  N8616C           BOEING
    ## 1785  N8616C           BOEING
    ## 1786  N8616C           BOEING
    ## 1787  N8616C           BOEING
    ## 1788  N8616C           BOEING
    ## 1789  N8616C           BOEING
    ## 1790  N8617E           BOEING
    ## 1791  N8618N           BOEING
    ## 1792  N8619F           BOEING
    ## 1793  N8620H           BOEING
    ## 1794  N8621A           BOEING
    ## 1795  N903JB           AIRBUS
    ## 1796  N903JB           AIRBUS
    ## 1797  N903JB           AIRBUS
    ## 1798  N903JB           AIRBUS
    ## 1799  N903JB           AIRBUS
    ## 1800  N903JB           AIRBUS
    ## 1801  N903JB           AIRBUS
    ## 1802  N903JB           AIRBUS
    ## 1803  N903JB           AIRBUS
    ## 1804  N903JB           AIRBUS
    ## 1805  N903JB           AIRBUS
    ## 1806  N903JB           AIRBUS
    ## 1807  N903JB           AIRBUS
    ## 1808  N907JB AIRBUS INDUSTRIE
    ## 1809  N907JB AIRBUS INDUSTRIE
    ## 1810  N907JB AIRBUS INDUSTRIE
    ## 1811  N907JB AIRBUS INDUSTRIE
    ## 1812  N907JB AIRBUS INDUSTRIE
    ## 1813  N907JB AIRBUS INDUSTRIE
    ## 1814  N907JB AIRBUS INDUSTRIE
    ## 1815  N907JB AIRBUS INDUSTRIE
    ## 1816  N907JB AIRBUS INDUSTRIE
    ## 1817  N907JB AIRBUS INDUSTRIE
    ## 1818  N907JB AIRBUS INDUSTRIE
    ## 1819  N907JB AIRBUS INDUSTRIE
    ## 1820  N907JB AIRBUS INDUSTRIE
    ## 1821  N913JB           AIRBUS
    ## 1822  N913JB           AIRBUS
    ## 1823  N913JB           AIRBUS
    ## 1824  N913JB           AIRBUS
    ## 1825  N913JB           AIRBUS
    ## 1826  N913JB           AIRBUS
    ## 1827  N913JB           AIRBUS
    ## 1828  N913JB           AIRBUS
    ## 1829  N913JB           AIRBUS
    ## 1830  N913JB           AIRBUS
    ## 1831  N913JB           AIRBUS

    df<-df%>%count(manufacturer,sort=TRUE)
    df%>%head(1)

    ##   manufacturer   n
    ## 1       BOEING 864
