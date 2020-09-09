---
layout: mypost
title:  "La percolazione delle reti"
date:   2020-09-09
categories: informatica
permalink: /:categories/:title
---

<p class="abstract">Inserire abstract</p>


Dalla struttura di una rete al comportamento che essa rappresenta
-----------------------

M. Newman sostiene che l'obbiettivo finale nello studio delle reti è quello di comprendere meglio il comportamento che la rete rappresenta. Ad esempio infatti, studiamo la rete internet per comprendere meglio come e dove si sposta il traffico di rete. Studiamo le reti metaboliche per provare a migliorare le nostre conoscenze sui complessi processi chimici che avvengono nelle cellule.

Negli articoli precedenti, abbiamo esplorato alcuni concetti _strutturali_ delle reti. Essi rappresentano solo il primo passo dell'analisi che ci prefiggiamo di fare.

Il nostro obbiettivo sarà ora capire come, a partire da alcune considerazioni strutturali delle reti, possiamo risalire al comportamento dell'intero sistema in esame.


La percolazione
-----------------------
Il processo che verrà illustrato in questo post prende il nome di _percolazione_. La percolazione rappresenta uno dei processi su reti più semplici da studiare, e si configura come un ottimo modello di robustezza di una rete nel caso in cui alcune componenti di quest'ultima si guastino.

Immaginiamo di eliminare da una rete una frazione dei suoi vertici e di conseguenza gli archi ad essi collegati. Questo processo è detto <font color="#f7246a">percolazione</font>.

Nella figura che segue alla rete (a) sono stati rimossi una serie di vertici (b). L'eliminazione dei vertici ha eliminato di conseguenza gli archi ad essi collegati.

<div style="text-align: center"><img src="/media/images/perc01.svg" /></div>

Un esempio reale del fenomeno della percolazione riguarda la vaccinazione degli individui contro una malattia contagiosa. Le malattie contagiose prosperano nelle reti molto connesse. Il vaccino in questo senso rappresenta simbolicamente la rimozione di un nodo dalla rete; in questa maniera alla malattia viene impedito di progredire lungo quel cammino.

Guardiamo la figura (a) che segue. Immaginiamo che il nodo N6 sia vaccinato e che, allo stesso tempo, il nodo N1 contagia il nodo N4 e il nodo N4 contagia il nodo N3.

L'effetto del vaccino sul nodo N6 equivale alla rimozione di quel nodo dalla rete. Di conseguenza senza il nodo N6 non esiste l'arco (N3, N6) e il contagio si interrompe. A tal proposito si noti come per solo fatto di aver "rimosso" il nodo N6 dalla rete, anche tutti i nodi ad esso collegati sono automaticamente protetti dalla malattia (b).

<div style="text-align: center"><img src="/media/images/perc02.svg" /></div>

La possibilità di vaccinare una ristretta cerchia di nodi significativi di una rete, talvolta permette di evitare la diffusione della malattia a grandi comunità della rete. Questo concetto è noto come _knock-on effect_ (effetto a catena).

È facile constatare che se per una rete di individui coinvolti in una malattia, la rimozione (tramite la vaccinazione) di uno o più nodi garantisce un beneficio ai nodi coinvolti in quella rete, non si può dire lo stesso, ad esempio, per una rete ferroviaria.

La "rimozione" di una o più stazioni coinvolte in una tratta arreca un danno per i treni che quella tratta la devono percorrere. Ciò che si ottiene sono una serie a cascata di ritardi e rallentamenti che certo non fanno felici i passeggeri.

**La teoria della percolazione si preoccupa di capire come gli effetti a catena dovuti alla rimozione o alla rottura di alcuni nodi, influenzano il comportamento della rete.**

In determinati contesti, ad essere rimossi non sono i nodi, ma gli archi. Si pensi ad esempio ad una rete internet dove a rompersi non è uno o più router ma uno o più cavi di connessione. Dalla fisica ereditiamo due modi diversi di riferirci alla percolazione a seconda dell soggetto che viene rimosso: parleremo di _site percolation_ se sono stati rimossi dei nodi, mentre parleremo di _bond percolation_ se sono stati rimossi degli archi.
