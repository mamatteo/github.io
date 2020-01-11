---
layout: mypost
title:  "Data visualization con ggplot2"
date:   2020-01-11
categories: R
permalink: /:categories/:title
---

In questo articolo, impareremo a visualizzare dati attraverso la libreria `ggplot2`, una delle librerie di `R` più versatile ed elegante.

Prerequisiti
============
Il pacchetto `ggplot2`fa parte della libreria [tidyverse][tidyverselink] e ne rappresenta una delle componenti chiave di tale libreria. Per scoprire come utilizzare questo pacchetto ci sarà utile caricare da subito una serie di oggetti utili al nostro scopo.

Eseguiamo quindi il seguente frammento di codice in un ambiente come RStudio.


{% highlight R %}
library(tidyverse)
#> Loading tidyverse: ggplot2
#> Loading tidyverse: tibble
#> Loading tidyverse: tidyr
#> Loading tidyverse: readr
#> Loading tidyverse: purr
{% endhighlight %}

A questo punto...

[tidyverselink]: https://www.tidyverse.org/
