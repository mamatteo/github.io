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

[M. Newman][Newman] sostiene che l'obbiettivo finale nello studio delle reti è quello di comprendere meglio il comportamento che la rete rappresenta. Ad esempio infatti, studiamo la rete internet per comprendere meglio come e dove si sposta il traffico di rete. Studiamo le reti metaboliche per provare a migliorare le nostre conoscenze sui complessi processi chimici che avvengono nelle cellule.

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

In determinati contesti, ad essere rimossi non sono i nodi, ma gli archi. Si pensi ad esempio ad una rete internet dove a rompersi non è uno o più router ma uno o più cavi di connessione. Dalla fisica ereditiamo due modi diversi di riferirci alla percolazione a seconda dell soggetto che viene rimosso: parleremo di <font color="#f7246a">site percolation</font> se sono stati rimossi dei nodi, mentre parleremo di <font color="#f7246a">bond percolation</font> se sono stati rimossi degli archi.

In questo articolo, ci riferiremo in particolar modo alla _site percolation_, ovvero alla rimozione di vertici. La _bond percolation_ (rimozione di archi), avrà un ruolo determinante nello studio della diffusione delle malattie. Di questo ce ne occuperemo più avanti.

Consideriamo una rete in uci rimuoviamo in maniera casuale (a _random_) alcuni dei suoi vertici. È bene constatare che in molti reti reali, _rimuovere_ un vertice non significa necessariamente eliminarlo fisicamente dalla rete: basta infatti che questo si guasti ed è come se fosse stato fisicamente rimosso.

Parametrizziamo la percolzione con la probabilità $$\phi$$
-----------------------
Indichiamo con $$\phi$$ la probabilità che un vertice sia presente e funzionante all'interno di una rete. Nel gergo della teoria della percolazione si usa definire occupati i vertici di una rete e $$\phi$$ è detta "probabilità di occupazione".

Quindi, $$\phi$$ = 1 indica che tutti i vertici di una determinata rete sono occupati, ovvero che non è stato rimosso alcun vertice. Viceversa $$\phi$$ = 0 indica che nessun vertice è occupato: concluderemo in questo caso che tutti i vertici sono stati rimossi.

<div style="text-align: center"><img src="/media/images/perc03.svg" /></div>

Dalle quattro figure riportate qui sopra è facile vedere come si riduce la probabilità $$\phi$$ man mano che la rete perde nodi. Rispetto alle quattro immagini riportate, due meritano una particolare attenzione. Nella figura _b_ si può osservare come la rimozione dei vertici N1, N2 e N9, non ha alcun effetto sul resto della rete. In altre parole: i nodi funzionanti continuano a poter dialogare fra loro nonsotante abbiano perso la connessione con i tre nodi guasti.  

La figura _c_ illustra invece un caso più grave. La rimozione dalla rete dei nodi N1, N2, N4, N6, N7 e N9 causa una disconessione della rete stessa. In particolare, il nodo N6, guastandosi, scollega il nodo N3 dal resto della rete e impedisce a quest'ultimo di dialogare con i nodi N5 e N8. Anche questi ultimi, inizialmente connessi in via indiretta, si trovano così senza più cammini che li possano mettere in connessione.

Questo semplice esempio ci mette in guardia da un fatto molto importante: **esitono percolazioni più gravi di altre, dove per "più gravi" intendiamo dire che esistono delle rimozioni di vertici che hanno delle dirette conseguenze sui vertici ancora funzionanti di una rete.**

[Newman]: http://www-personal.umich.edu/~mejn/
