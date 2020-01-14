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
Attaching packages
✓ ggplot2 3.2.1     ✓ purrr   0.3.3
✓ tibble  2.1.3     ✓ dplyr   0.8.3
✓ tidyr   1.0.0     ✓ stringr 1.4.0
✓ readr   1.3.1     ✓ forcats 0.4.0
Conflicts
x dplyr::filter() masks stats::filter()
x dplyr::lag()    masks stats::lag()
{% endhighlight %}

Il caricamento della libreria `tidyverse` carica a cascata una serie di strumenti utili alla maggior parte delle analisi dati che ci capiterà di dover fare. Inoltre, con il caricamento della libreria, veniamo anche informati delle funzioni di `tidyverse` che vanno in conflitto con le funzioni standard di R.

<hr>


Primi passi
===========
Useremo la libreria _tidyverse_ per prendere dimestichezza con le funzioni di visualizzazione offerte da R. Ci serviremo di un dataset predefinito, contenuto in _tidyverse_, che prende il nome di [MPG][datasetmpglink]. Il contenuto di MPG viene così descritto: _the dataset contains fuel economy data from 1999 and 2008 for 38 popular models of car_.

Avremo a che fare quindi con dati riferiti a delle automobili e alle loro caratteristiche.

Proveremo a servirci di alcune visualizzazioni per rispondere a questa domanda: _è vero che le automobili con un motore grande consumano più delle automobili con un motore piccolo?_ Molto probabilmente conosciamo già la risposta, ma proveremo a motivarla attraverso un'analisi precisa. Ci chideremo quindi, qual è la relazione che intercorre tra la dimensione del motore di un automobile e la sua efficienza dal punto di vista dei consumi.

All'interno del pacchetto `ggplot2` che abbiamo caricato, troviamo il dataframe `mpg`, che contiene una serie di dati collezionati dalla _US Envirnoment Protection Agency_. Il dataset raccoglie informazioni su 38 tipologie di automobili. Ci basterà digitare il comando `mpg` per avere una prima rappresentazione del contenuto del dataset.

{% highlight python %}
# A tibble: 234 x 11
   manufacturer model      displ  year   cyl trans      drv     cty   hwy fl    class  
   <chr>        <chr>      <dbl> <int> <int> <chr>      <chr> <int> <int> <chr> <chr>  
 1 audi         a4           1.8  1999     4 auto(l5)   f        18    29 p     compact
 2 audi         a4           1.8  1999     4 manual(m5) f        21    29 p     compact
 3 audi         a4           2    2008     4 manual(m6) f        20    31 p     compact
 4 audi         a4           2    2008     4 auto(av)   f        21    30 p     compact
 5 audi         a4           2.8  1999     6 auto(l5)   f        16    26 p     compact
 6 audi         a4           2.8  1999     6 manual(m5) f        18    26 p     compact
 7 audi         a4           3.1  2008     6 auto(av)   f        18    27 p     compact
 8 audi         a4 quattro   1.8  1999     4 manual(m5) 4        18    26 p     compact
 9 audi         a4 quattro   1.8  1999     4 auto(l5)   4        16    25 p     compact
10 audi         a4 quattro   2    2008     4 manual(m6) 4        20    28 p     compact
{% endhighlight %}

Come si può dedurre dalla tabella che R ci stampa in output, `manufacturer`, `model`, `displ`, `year`, `cyl`, `trans`, `drv`, `cty`, `hwy`, `fl` e `class`, rappresentano le variabili del dataset. Ciascuna rappresenta una caratteritica delle automobili riportate sulle righe.

Quelle di nostro interesse però saranno:

- `displ`: che rappresenta la dimensione del motore di ciascuna auto, in litri.
- `hwy`: che rappresenta invece il consumo di carburante di ciascuna auto.

Ulteriori dettagli sul datasete `mpg` sono consultabili digitando il comando `?mpg`.

Per approfondire ulteriormente come è strutturato il dataset si rimanda all'[analisi esplorativa][datasetmpglink] del dataset `mpg`, condotta da [Shailesh Kumar][KumarBioLink], esperto di data science di Google e di altre grandi ed importanti realtà.

<hr>


Visualizzare i dati
=====================
Possiamo a questo punto stampare il dataset `mpg`. Per farlo sarà sufficiente eseguire il seguente frammento di codice.

{% highlight R %}
ggplot(data = mpg) +
  geom_point(mapping = aes(x = displ, y = hwy)
{% endhighlight %}

![ggplot1](/media/images/ggplot1.png)

Il grafico mostra la relazione negativa che intercorre tra la dimensione del motore di ogni automobile (variabile `displ`) e la sua _fuel efficency_ (variabile `hwy`). Questo risultato lo interpretiamo affermando che ad auto in possesso di un motore grande, corrispondono valori bassi di _fuel efficency_, quindi, queste auto utilizzano più carburante. Viceversa ad automobili dotate di un motore piccolo, corrispondono alti valori di _fuel efficency_, pertanto queste consumano meno carburante.

Abbiamo appena utilizzato `ggplot` per stampare una prima visualizzazione dei dati oggetto del nostro studio. Nel dettaglio:
- il comando `data = mpg` specifica alla funzione quale dataset utilizzare;
- il comando `geom_point` permette di stampare lo scatterplot dei dati;
- il parametro `mapping`, istanziato con `aes(x = displ, y = hwy)`, stabilisce infine quali variabili del dataset vanno inserite nella stampa e come suddividerle lungo gli assi cartesiani.


Decidiamo ora di arricchire la nostra stampa, colorando ogni punto del grafico con un colore. Coloreremo i punti del piano in maniera automatica, in modo che ogni punto venga colorato con il colore della classe di appartenenza. La classe di appartenenza, per quanto riguarda il dataset in esame, rappresenta la tipologia a cui appartiene ciascuna automobile. L'attributo `class` stabilisce la classe di appartenenza.

![ggplot2](/media/images/ggplot2.png)


[KumarBioLink]: https://research.google/people/ShaileshKumar/
[datasetmpglink]: https://rpubs.com/shailesh/mpg-exploration
[linguaggioRlink]: https://cran.r-project.org/
[RForDataScienceLink]: https://www.oreilly.com/library/view/r-for-data/9781491910382/
[RForDataScienceLinkOnline]: https://r4ds.had.co.nz/
[tidyverselink]: https://www.tidyverse.org/
[rstudiolink]: https://rstudio.com/products/rstudio/download/
