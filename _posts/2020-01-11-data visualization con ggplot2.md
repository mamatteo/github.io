---
layout: mypost
title:  "Data visualization con ggplot2"
date:   2020-01-11
categories: R
permalink: /:categories/:title
---

In questo articolo, impareremo a visualizzare dati attraverso la libreria `ggplot2`, una delle librerie di R più versatili ed eleganti.

Il testo che segue è una traduzione del capitolo 1 del mauale [R for Data Science][RForDataScienceLink] di Hadley Wickham e Garret Grolemund, edito dalla O'Reilly. Il libro è parzialmente consultabile anche online, [qui][RForDataScienceLinkOnline].
- [Prerequisiti](#prerequisiti)
- [Primi passi](#primi-passi)


Prerequisiti
============
Il pacchetto `ggplot2` fa parte della libreria [tidyverse][tidyverselink] e ne rappresenta una delle componenti chiave. Per utilizzare in maniera efficace le funzioni che utilizzeremo in questo tutorial, è utile eseguire il seguente codice nell'ambiente di sviluppo che decidiamo di utilizzare (il consiglio è quello di usare [RStudio][rstudiolink]).

{% highlight R %}
library(tidyverse)
{% endhighlight %}

{% highlight R %}
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

Nel caso in cui, dopo aver eseguito il comando, il sistema restituisce l'errore "_there is no package called 'tidyverse'_", c'è bisogno allora di installarlo, tramite il comando che segue:

{% highlight R %}
install.packages("tidyverse")
library(tidyverse)
{% endhighlight %}

Primi passi
===========
Tramite il primo esempio che facciamo proveremo a risppndere a questa domanda: _è vero che le automobili con un motore grande consumano di più delle automobili con un motore piccolo?_. Molto probabilmente già conosciamo la risposta, ma proveremo a motivarla attraverso un'analisi precisa. Ci chideremo quindi _qual è la relazione che intercorre tra il motore di un automobile e il consumo di carburante?_.

All'interno del pacchetto `ggplot2` che abbiamo caricato, troviamo il dataframe `mpg`, che contiene una serie di dati collezionati dalla _US Envirnoment Protection Agency_. Il dataset raccoglie informazioni su 38 tipologie di automobili. Ci basterà digitare il comando `mpg` per avere una prima rappresentazione del contenuto del dataset.

{% highlight python %}
#> # A tibble: 234 x 11
#>   manufacturer model displ year cyl    trans       drv
#>    <chr> <chr> <dbl> <int> <int>       <chr>       <chr>
#> 1  audi  a4    1:8   1999   4          auto(l5)    f
#> 2  audi  a4    1:8   1999   4          manual(m5)  f
#> 3
#> 4
#> 5
#> 6
#> # ... with 228 more rows, and 4 more variables:
#> # cty <int>, hwy <int>, fl <chr>, class <chr>
{% endhighlight %}

Come si può dedurre dalla tabella che R ci stampa in output, `manufacturer`, `model`, `displ`, `year`, `cyl`, `trans` e `drv`, rappresentano le variabili del dataset. Quelle di nostro interesse saranno:

- `displ`: che rappresenta la dimensione del motore di ciascuna auto, in litri.
- `hwy`: che rappresenta invece il consumo di carburante di ciascuna auto.

Un auto che ha una bassa efficienza nei consumi consumerà più carburante rispetto ad un auto con un'alta efficienza nei consumi, a parità di distanza percorsa.

Ulteriori dettagli sul datasete `mpg` sono consutlabili digitando il comando **?mpg**

![graph](/media/images/graph.png)
*Output del primo codice*

[RForDataScienceLink]: https://www.oreilly.com/library/view/r-for-data/9781491910382/
[RForDataScienceLinkOnline]: https://r4ds.had.co.nz/
[tidyverselink]: https://www.tidyverse.org/
[rstudiolink]: https://rstudio.com/
