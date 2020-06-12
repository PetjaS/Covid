Tartuntatilastot THL:n Sampo-tietokannasta
================
Sjö, P.
12 6 2020

Tämä koodi hakee THL:n ylläpitämästä Sampo-tietokannasta päivitetyt
tilastot Uudenmaan koronatapauksista

### Aineiston kuvailu

Aineiston tunnusluvut sekä kuvaaja

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##    0.00    1.00   44.00   51.63   86.00  206.00

![](Covid_files/figure-gfm/data%20descriptives-1.png)<!-- -->

Istutetun mallin tulokset

    ## 
    ## Family: gaussian 
    ## Link function: identity 
    ## 
    ## Formula:
    ## Tapauksien_lkm ~ s(nro)
    ## 
    ## Parametric coefficients:
    ##             Estimate Std. Error t value Pr(>|t|)    
    ## (Intercept)   51.628      2.034   25.38   <2e-16 ***
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Approximate significance of smooth terms:
    ##          edf Ref.df    F p-value    
    ## s(nro) 6.527  7.665 65.5  <2e-16 ***
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## R-sq.(adj) =  0.787   Deviance explained = 79.8%
    ## GCV =  599.7  Scale est. = 566.75    n = 137

### Ennustava malli

#### Aineiston autokorrelaatio

![](Covid_files/figure-gfm/unnamed-chunk-2-1.png)<!-- -->

#### Autoregressiivinen malli ja sen ennustus seuraavalle 10 päivälle (95 % luottamusväli)

    ## 
    ## Call:
    ## arima(x = tartunnat$Tapauksien_lkm, order = c(1, 0, 0))
    ## 
    ## Coefficients:
    ##          ar1  intercept
    ##       0.8615    47.3862
    ## s.e.  0.0426    15.4840
    ## 
    ## sigma^2 estimated as 682.2:  log likelihood = -642.06,  aic = 1290.12

    ## $pred
    ## Time Series:
    ## Start = 138 
    ## End = 147 
    ## Frequency = 1 
    ##  [1]  6.565328 12.221034 17.093147 21.290233 24.905815 28.020461 30.703576
    ##  [8] 33.014947 35.006079 36.721342
    ## 
    ## $se
    ## Time Series:
    ## Start = 138 
    ## End = 147 
    ## Frequency = 1 
    ##  [1] 26.11972 34.47504 39.55052 42.93089 45.27661 46.94165 48.14006 49.01046
    ##  [9] 49.64652 50.11332

![](Covid_files/figure-gfm/unnamed-chunk-3-1.png)<!-- -->
