---
layout: mypost
title:  "Data visualization con ggplot2"
date:   2020-01-11
categories: R
permalink: /:categories/:title
---

In questo articolo, impareremo a visualizzare dati attraverso la libreria `ggplot2`, una delle librerie di `R` più versatili ed eleganti.

Prerequisiti
============
Il pacchetto `ggplot2`fa parte della libreria [tidyverse][tidyverselink] e ne rappresenta una delle componenti chiave. Per utilizzare in maniera efficace le funzioni che utilizzeremo in questo tutorial, è utile eseguire il seguente codice nell'ambiente di sviluppo che decidiamo di utilizzare (il consiglio è quello di usare [RStudio][rstudiolink]).

{% highlight ruby %}
library(tidyverse)
#> Loading tidyverse: ggplot2
#> Loading tidyverse: tibble
#> Loading tidyverse: tidyr
#> Loading tidyverse: readr
#> Loading tidyverse: purr
#> Loading tidyverse: dplyr
#> Conflicts with tidy packages -------
#> filter(): dplyr, stats
#> lag(): dplyr, stats
{% endhighlight %}

Con il solo caricamento della libreria `tidyverse` abbiamo già a nostra disposizione una buona quantità di strumenti utili alla maggior parte delle analisi dati che ci capiterà di dover fare. L'esecuzione del comando ci informa anche delle funzioni di `tidyverse` che vanno in conflitto con le funzioni standard di R. 


[tidyverselink]: https://www.tidyverse.org/
[rstudiolink]: https://rstudio.com/
