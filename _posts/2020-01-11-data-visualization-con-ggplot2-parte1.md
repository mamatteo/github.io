---
layout: mypost
title:  "Data visualization con ggplot2 - parte 1"
date:   2020-01-11
categories: R
permalink: /:categories/:title
---

In questo articolo, impareremo a visualizzare dati attraverso la libreria `ggplot2`, una delle librerie di R più versatili ed eleganti.

Il testo che segue è una traduzione del capitolo 1 del mauale [R for Data Science][RForDataScienceLink] di Hadley Wickham e Garret Grolemund, edito dalla O'Reilly. Il libro è parzialmente consultabile anche online, [qui][RForDataScienceLinkOnline].
- [Prerequisiti](#prerequisiti)
- [Primi passi](#primi-passi)
- [Visualizzare i dati](#visualizzare-i-dati)

<hr>

Prerequisiti
============
Il pacchetto `ggplot2` fa parte della libreria [tidyverse][tidyverselink] e ne rappresenta una delle componenti chiave. Per utilizzare in maniera efficace le funzioni che utilizzeremo in questo tutorial, è utile eseguire il seguente codice nell'ambiente di sviluppo che decidiamo di utilizzare (il consiglio è quello di usare [RStudio][rstudiolink], che dovrete scaricare e installare solo dopo aver installato nel vostro computer [R][linguaggioRlink]).

Innazitutto è importante assicurarsi che _tidyverse_ sia installato nel proprio ambiente di sviluppo. In caso contrario si deve procedere ad installarlo tramite il comando:

{% highlight R %}
install.packages(tidyverse)
{% endhighlight %}

che dopo qualche minuto di lavoro restituisce il controllo della console.

Con il comando:

{% highlight R %}
library(tidyverse)
{% endhighlight %}

invece, verrà caricato _tidyverse_ nello spazio di lavoro. Siamo ora pronti a sfruttare le sue funzioni.

{% highlight R %}
── Attaching packages ─────────────
✓ ggplot2 3.2.1     ✓ purrr   0.3.3
✓ tibble  2.1.3     ✓ dplyr   0.8.3
✓ tidyr   1.0.0     ✓ stringr 1.4.0
✓ readr   1.3.1     ✓ forcats 0.4.0
── Conflicts ──────────────────────────
x dplyr::filter() masks stats::filter()
x dplyr::lag()    masks stats::lag()
{% endhighlight %}

Con il solo caricamento della libreria `tidyverse` abbiamo già a nostra disposizione una buona quantità di strumenti utili alla maggior parte delle analisi dati che ci capiterà di dover fare. L'esecuzione del comando ci informa anche delle funzioni di `tidyverse` che vanno in conflitto con le funzioni standard di R.

Nel caso in cui, dopo aver eseguito il comando, il sistema restituisce l'errore "_there is no package called 'tidyverse'_", c'è bisogno allora di installarlo, tramite il comando che segue:

{% highlight R %}
install.packages("tidyverse")
library(tidyverse)
{% endhighlight %}

<hr>

Primi passi
===========
Tramite il primo esempio che facciamo proveremo a risppndere a questa domanda: _è vero che le automobili con un motore grande consumano di più delle automobili con un motore piccolo?_. Molto probabilmente già conosciamo la risposta, ma proveremo a motivarla attraverso un'analisi precisa. Ci chideremo quindi: _qual è la relazione che intercorre tra il motore di un automobile e il consumo di carburante?_

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

Ulteriori dettagli sul datasete `mpg` sono consultabili digitando il comando '?mpg'.

<hr>

Visualizzare i dati
=====================
Per stampare il dataset `mpg`, sarà sufficiente eseguire il seguente frammento di codice.

![graph](/media/images/graph.png)
*Output del primo codice*

[linguaggioRlink]: https://cran.r-project.org/
[RForDataScienceLink]: https://www.oreilly.com/library/view/r-for-data/9781491910382/
[RForDataScienceLinkOnline]: https://r4ds.had.co.nz/
[tidyverselink]: https://www.tidyverse.org/
[rstudiolink]: https://rstudio.com/products/rstudio/download/
