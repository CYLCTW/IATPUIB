
# **lab1**

#### **2022-10-19**

## **R Markdown**

    summary(cars)

    ##      speed           dist       
    ##  Min.   : 4.0   Min.   :  2.00  
    ##  1st Qu.:12.0   1st Qu.: 26.00  
    ##  Median :15.0   Median : 36.00  
    ##  Mean   :15.4   Mean   : 42.98  
    ##  3rd Qu.:19.0   3rd Qu.: 56.00  
    ##  Max.   :25.0   Max.   :120.00

## **Настройка**

    library(dplyr)

    ## 
    ## Attaching package: 'dplyr'

    ## The following objects are masked from 'package:stats':
    ## 
    ##     filter, lag

    ## The following objects are masked from 'package:base':
    ## 
    ##     intersect, setdiff, setequal, union

    starwars

    ## # A tibble: 87 × 14
    ##    name        height  mass hair_…¹ skin_…² eye_c…³ birth…⁴ sex   gender homew…⁵
    ##    <chr>        <int> <dbl> <chr>   <chr>   <chr>     <dbl> <chr> <chr>  <chr>  
    ##  1 Luke Skywa…    172    77 blond   fair    blue       19   male  mascu… Tatooi…
    ##  2 C-3PO          167    75 <NA>    gold    yellow    112   none  mascu… Tatooi…
    ##  3 R2-D2           96    32 <NA>    white,… red        33   none  mascu… Naboo  
    ##  4 Darth Vader    202   136 none    white   yellow     41.9 male  mascu… Tatooi…
    ##  5 Leia Organa    150    49 brown   light   brown      19   fema… femin… Aldera…
    ##  6 Owen Lars      178   120 brown,… light   blue       52   male  mascu… Tatooi…
    ##  7 Beru White…    165    75 brown   light   blue       47   fema… femin… Tatooi…
    ##  8 R5-D4           97    32 <NA>    white,… red        NA   none  mascu… Tatooi…
    ##  9 Biggs Dark…    183    84 black   light   brown      24   male  mascu… Tatooi…
    ## 10 Obi-Wan Ke…    182    77 auburn… fair    blue-g…    57   male  mascu… Stewjon
    ## # … with 77 more rows, 4 more variables: species <chr>, films <list>,
    ## #   vehicles <list>, starships <list>, and abbreviated variable names
    ## #   ¹​hair_color, ²​skin_color, ³​eye_color, ⁴​birth_year, ⁵​homeworld

    starwars <- starwars

## **1. Сколько строк в датафрейме?**

    starwars %>% nrow()

    ## [1] 87

## **2. Сколько столбцов в датафрейме?**

    starwars %>% ncol()

    ## [1] 14

## **3. Как просмотреть примерный вид датафрейма?**

    starwars %>% glimpse()

    ## Rows: 87
    ## Columns: 14
    ## $ name       <chr> "Luke Skywalker", "C-3PO", "R2-D2", "Darth Vader", "Leia Or…
    ## $ height     <int> 172, 167, 96, 202, 150, 178, 165, 97, 183, 182, 188, 180, 2…
    ## $ mass       <dbl> 77.0, 75.0, 32.0, 136.0, 49.0, 120.0, 75.0, 32.0, 84.0, 77.…
    ## $ hair_color <chr> "blond", NA, NA, "none", "brown", "brown, grey", "brown", N…
    ## $ skin_color <chr> "fair", "gold", "white, blue", "white", "light", "light", "…
    ## $ eye_color  <chr> "blue", "yellow", "red", "yellow", "brown", "blue", "blue",…
    ## $ birth_year <dbl> 19.0, 112.0, 33.0, 41.9, 19.0, 52.0, 47.0, NA, 24.0, 57.0, …
    ## $ sex        <chr> "male", "none", "none", "male", "female", "male", "female",…
    ## $ gender     <chr> "masculine", "masculine", "masculine", "masculine", "femini…
    ## $ homeworld  <chr> "Tatooine", "Tatooine", "Naboo", "Tatooine", "Alderaan", "T…
    ## $ species    <chr> "Human", "Droid", "Droid", "Human", "Human", "Human", "Huma…
    ## $ films      <list> <"The Empire Strikes Back", "Revenge of the Sith", "Return…
    ## $ vehicles   <list> <"Snowspeeder", "Imperial Speeder Bike">, <>, <>, <>, "Imp…
    ## $ starships  <list> <"X-wing", "Imperial shuttle">, <>, <>, "TIE Advanced x1",…

## **4. Сколько уникальных рас персонажей (species) представлено в данных?**

    unique(starwars$species) %>% length()

    ## [1] 38

## **5. Найти самого высокого персонажа.**

    starwars[which.max(starwars$height),1]

    ## # A tibble: 1 × 1
    ##   name       
    ##   <chr>      
    ## 1 Yarael Poof

## **6. Найти всех персонажей ниже 170**

    starwars[which(starwars$height<170),1]

    ## # A tibble: 23 × 1
    ##    name                 
    ##    <chr>                
    ##  1 C-3PO                
    ##  2 R2-D2                
    ##  3 Leia Organa          
    ##  4 Beru Whitesun lars   
    ##  5 R5-D4                
    ##  6 Yoda                 
    ##  7 Mon Mothma           
    ##  8 Wicket Systri Warrick
    ##  9 Nien Nunb            
    ## 10 Watto                
    ## # … with 13 more rows

## **7. Подсчитать ИМТ (индекс массы тела) для всех персонажей. ИМТ подсчитать по формуле 𝐼 = 𝑚/h\^2**

ℎ2 , где 𝑚 -- масса (weight), а ℎ -- рост (height).

    starwars2<-starwars[,c("name","height","mass")]
    vec<-0
    starwars2$index <- vec
    for(i in 1:nrow(starwars2)) {       # for-loop over columns
      starwars2[i, "index"] = starwars2[ i,"mass"]*10000/(starwars2[i,"height"]*starwars2[i,"height"])
    }
    starwars2

    ## # A tibble: 87 × 4
    ##    name               height  mass index
    ##    <chr>               <int> <dbl> <dbl>
    ##  1 Luke Skywalker        172    77  26.0
    ##  2 C-3PO                 167    75  26.9
    ##  3 R2-D2                  96    32  34.7
    ##  4 Darth Vader           202   136  33.3
    ##  5 Leia Organa           150    49  21.8
    ##  6 Owen Lars             178   120  37.9
    ##  7 Beru Whitesun lars    165    75  27.5
    ##  8 R5-D4                  97    32  34.0
    ##  9 Biggs Darklighter     183    84  25.1
    ## 10 Obi-Wan Kenobi        182    77  23.2
    ## # … with 77 more rows

## **8. Найти 10 самых \"вытянутых\" персонажей. \"Вытянутость\" оценить по отношению массы (mass) к росту**

(height) персонажей.

    starwars2<-starwars
    starwars3<- starwars2[which.max(starwars2$height),]
    starwars2<-starwars2[-c(which.max(starwars2$height)),]
    starwars3[nrow(starwars3) + 1,] = starwars2[which.max(starwars2$height),]
    starwars2<-starwars2[-c(which.max(starwars2$height)),]
    starwars3[nrow(starwars3) + 1,] = starwars2[which.max(starwars2$height),]
    starwars2<-starwars2[-c(which.max(starwars2$height)),]
    starwars3[nrow(starwars3) + 1,] = starwars2[which.max(starwars2$height),]
    starwars2<-starwars2[-c(which.max(starwars2$height)),]
    starwars3[nrow(starwars3) + 1,] = starwars2[which.max(starwars2$height),]
    starwars2<-starwars2[-c(which.max(starwars2$height)),]
    starwars3[nrow(starwars3) + 1,] = starwars2[which.max(starwars2$height),]
    starwars2<-starwars2[-c(which.max(starwars2$height)),]
    starwars3[nrow(starwars3) + 1,] = starwars2[which.max(starwars2$height),]
    starwars2<-starwars2[-c(which.max(starwars2$height)),]
    starwars3[nrow(starwars3) + 1,] = starwars2[which.max(starwars2$height),]
    starwars2<-starwars2[-c(which.max(starwars2$height)),]
    starwars3[nrow(starwars3) + 1,] = starwars2[which.max(starwars2$height),]
    starwars2<-starwars2[-c(which.max(starwars2$height)),]
    starwars3[nrow(starwars3) + 1,] = starwars2[which.max(starwars2$height),]
    starwars2<-starwars2[-c(which.max(starwars2$height)),]
    starwars3

    ## # A tibble: 10 × 14
    ##    name        height  mass hair_…¹ skin_…² eye_c…³ birth…⁴ sex   gender homew…⁵
    ##    <chr>        <int> <dbl> <chr>   <chr>   <chr>     <dbl> <chr> <chr>  <chr>  
    ##  1 Yarael Poof    264    NA none    white   yellow     NA   male  mascu… Quermia
    ##  2 Tarfful        234   136 brown   brown   blue       NA   male  mascu… Kashyy…
    ##  3 Lama Su        229    88 none    grey    black      NA   male  mascu… Kamino 
    ##  4 Chewbacca      228   112 brown   unknown blue      200   male  mascu… Kashyy…
    ##  5 Roos Tarpa…    224    82 none    grey    orange     NA   male  mascu… Naboo  
    ##  6 Grievous       216   159 none    brown,… green,…    NA   male  mascu… Kalee  
    ##  7 Taun We        213    NA none    grey    black      NA   fema… femin… Kamino 
    ##  8 Rugor Nass     206    NA none    green   orange     NA   male  mascu… Naboo  
    ##  9 Tion Medon     206    80 none    grey    black      NA   male  mascu… Utapau 
    ## 10 Darth Vader    202   136 none    white   yellow     41.9 male  mascu… Tatooi…
    ## # … with 4 more variables: species <chr>, films <list>, vehicles <list>,
    ## #   starships <list>, and abbreviated variable names ¹​hair_color, ²​skin_color,
    ## #   ³​eye_color, ⁴​birth_year, ⁵​homeworld

## **9. Найти средний возраст персонажей каждой расы вселенной Звездных войн.**

    starwars %>%
      filter(!(birth_year %in% NA)) %>% 
      filter(!(species %in% NA)) %>%
      group_by(species) %>%
      summarise(mean_age = mean(birth_year)) 

    ## # A tibble: 15 × 2
    ##    species        mean_age
    ##    <chr>             <dbl>
    ##  1 Cerean             92  
    ##  2 Droid              53.3
    ##  3 Ewok                8  
    ##  4 Gungan             52  
    ##  5 Human              53.4
    ##  6 Hutt              600  
    ##  7 Kel Dor            22  
    ##  8 Mirialan           49  
    ##  9 Mon Calamari       41  
    ## 10 Rodian             44  
    ## 11 Trandoshan         53  
    ## 12 Twi'lek            48  
    ## 13 Wookiee           200  
    ## 14 Yoda's species    896  
    ## 15 Zabrak             54

## **10. Найти самый распространенный цвет глаз персонажей вселенной Звездных войн.**

    starwars%>%
    count(eye_color,sort=TRUE)%>%
    head(1)

    ## # A tibble: 1 × 2
    ##   eye_color     n
    ##   <chr>     <int>
    ## 1 brown        21

## **11. Подсчитать среднюю длину имени в каждой расе вселенной Звездных войн.**

    starwars %>%
      filter(!(birth_year %in% NA)) %>% 
      filter(!(species %in% NA)) %>%
      group_by(species) %>%
      summarise(mean_name = mean(nchar(name)))

    ## # A tibble: 15 × 2
    ##    species        mean_name
    ##    <chr>              <dbl>
    ##  1 Cerean              12  
    ##  2 Droid                5  
    ##  3 Ewok                21  
    ##  4 Gungan              13  
    ##  5 Human               12.1
    ##  6 Hutt                21  
    ##  7 Kel Dor              8  
    ##  8 Mirialan            14  
    ##  9 Mon Calamari         6  
    ## 10 Rodian               6  
    ## 11 Trandoshan           5  
    ## 12 Twi'lek             11  
    ## 13 Wookiee              9  
    ## 14 Yoda's species       4  
    ## 15 Zabrak              10
