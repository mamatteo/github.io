---
layout: mypost
title:  "Che cos'è un grafo e come rappresentarlo"
date:   2020-01-09
categories: informatica
permalink: /:categories/:title
---

<p class="abstract">In questo articolo verranno illustrati i concetti di base della teoria dei grafi, la branca della matematica che si occupa dello studio delle reti (dette anche grafi per l'appunto). Dopo aver dato la definizone di grafo vedremo che esistono diversi modi per rappresentarli. Concluderemo questo articolo con alcune note sull'importanza della teoria dei grafi nel mondo reale e nella vita di tutti i giorni.</p>

Cosa sono i grafi
-----------------------

La [<font color="#b3d313">teoria dei grafi</font>][graphtheorylink] è una branca della matematica e dell'informatica che si occupa di studiare degli oggetti chiamati per l'appunto _grafi_.

Un grafo _G_ è una coppia di insiemi, e più precisamente è la coppia formata dall'insieme _V_ dei <font color="#b3d313">nodi</font> (_vertices_ in inglese), e dall'insieme _E_ degli <font color="#b3d313">archi</font> (_edges_ in inglese).

$$G = (V, E)$$

Un grafo rappresenta un modello astratto per descrivere un determinato contesto reale. In generale, si utilizzano i nodi per rappresentare le _entità_ del dominio analizzato, mentre gli archi rappresenteranno le _relazioni_ che intercorrono tra le diverse entità coinvolte. È consuetudine, in matematica, utilizzare la lettera _n_ per denotare il numero dei nodi di un grafo, e la lettera _m_ per denotare invece il numero di archi.

Alla luce di questa premesse, è importante ricordare che i grafi sono strumenti adatti a modellare dei contesti "di relazione". Viceversa, laddove non vi sono delle relazioni evidenti tra i soggetti coinvolti, i grafi probabilmente non rappresentano lo strumento di modellazione più adatto.

Solitamente, presi due nodi di un grafo questi sono collegati da uno ed un solo arco. Tuttavia nulla vieta che questi due nodi siano collegati da più di un arco. In questo caso parleremo di <font color="#b3d313">multiarchi</font> (o _multiedges_). Come mostrato nella figura seguente, un multi arco potrebbe rivelarsi utile quando vogliamo rappresentare più informazioni contemporaneamente. Nell'esempio, tra i nodi N1 e N2, abbiamo messo in evidenza un arco che potrebbe esprimere la distanza che intercorre tra i due nodi, e un arco che esprime la capacità del collegamento. Immaginiamo ad esempio che i due nodi rappresentino due appartamenti diversi di uno stesso condominio, e che gli archi rappresentino le condutture idrauliche. Ci interessa quindi conoscere la distanza dei due appartamenti (primo arco) e la capacità in litri del tubo che  li collega (secondo arco).

<div style="text-align: center"><img src="/media/images/graph3.svg" /></div>

<br>
Un ulteriore concetto chiave della teoria dei grafi riguarda la direzione degli archi. Se esiste un arco tra il nodo N1 e il nodo N2, diremo che <font color="#b3d313">l'arco è indiretto</font> se è possibile percorrere l'arco da il nodo N1 al nodo N2 e viceversa. Altrimenti, diremo che <font color="#b3d313">l'arco che li collega è diretto</font>, se esiste un'unica direzione in cui è possibile percorrere l'arco. Nella figura che segue è mostrato un esempio di arco diretto. Un arco diretto, in un grafo, si esprime indicando una freccia in una delle sue due estremità.

<div style="text-align: center"><img src="/media/images/graph4.svg" /></div>

<br>
Spesso un sinonimo di grafo è <font color="#b3d313">rete</font> (_network_). Lo studio dei grafi è anche detto studio delle reti o [_network science_][nslink]. Le reti non vengono studiate solo dalla matematica, ma anche dalla fisica, dall'economia, dalla chimica e dalla sociologia.

<br>

Dizionario elementare
------------------------------------

Chiameremo <font color="#b3d313">cammino</font> (_path_), una squenza ordinata di archi. Un cammino si esprime sempre in riferimento a due nodi. Pertanto, in riferimento alla figura riportata di seguito, potremmo dire che tra il nodo N6 e il nodo N2, esiste il cammino formato dagli archi A6, A7 e A1.

Nota:
- tra due nodi può esistere più di un cammino (riesci a trovare 3 cammini diversi che collegano il nodo N1 al nodo N4?);
- spesso per l'informatica è utile individuare, soprattutto su reti complesse, il cammino più breve ([cammino minimo][pathmin]) che collega due nodi della rete. Esistono problemi famosi riferiti a questa idea, come lo [shortest path problem][spplink];
- tra due nodi di una rete potrebbe anche non esserci alcun cammino che li collega.

<div style="text-align: center"><img src="/media/images/path.svg" /></div>

<br>
Parleremo di <font color="#b3d313">ciclo</font> (_loop_), tutte le volte in cui dovremmo riferirci ad un cammino che partendo da un determinato nodo, ritorna dopo un numero _m_ di archi allo stesso nodo dal quale siamo partiti.

<div style="text-align: center"><img src="/media/images/loops.svg" /></div>


Come si rappresenta un grafo
------------------------------------

Disegnare i grafi
==================

Una delle potenzialità dei grafi, e la facilità con cui li possiamo rappresentare. Alcuni esempi riportati di seguito aiuteranno il lettore a prendere confidenza con questi oggetti matematici.

<div style="text-align: center"><img src="/media/images/graph1.svg" /></div>

Nella figura sono stati messi in evidenza i nodi

$$V = \{N1, N2, N3, N4, N5, N6\}$$

e l'insieme degli archi

$$E = \{A1, A2, A3, A4, A5, A6\}$$

"Leggere" un grafo è semplice (quando il grafo è piccolo come quello nell'esempio).

Nel grafo in figura ad esempio, si nota che il nodo N1 è collegato al nodo N2, mediante l'arco A1. Allo stesso modo il nodo N5 è collegato al nodo N4 dall'arco A4. Un collegamento tra nodi, avviene per mezzo di uno o più archi che ci permettono, partendo da uno dei due nodi considerati, di raggiungere l'altro, o viceversa. Non è necessario che ci sia _esattamente_ un arco tra due nodi per definire quei due nodi "collegati". Il nodo N6, ad eempio, è sicuramente collegato al nodo N4 mediante l'arco A5, e al nodo N5 mediante l'arco A3. Ma il nodo N6 è collegato anche al nodo N3, mediante gli archi A5 e A6 oppure al nodo N1, mediante gli archi A5, A6, A7 e A1.

Forse ti sarai accorto che esistono anche altre strade che collegano il nodo N6 al nodo N1. In generale, in un grafo, possono esistere _n_ strade che collegano due nodi in un grafo. Diversi algoritmi studiati dall'informatica operano proprio sulle lunghezze delle strade che collegano due o più nodi di un grafo, ma non ne parleremo in questo articolo.

Quel che è importante aver capito fin qui, è che un grafo rappresenta una serie di relazioni tra entità, mediante i suoi nodi e i suoi archi.

Ridisegniamo ora il grafo precedente, calandolo ad un contesto reale. Immaginiamo di voler disegnare il grafo di sei città italiane, diciamo Venezia, Milano, Torino, Bologna, Roma e Palermo. Queste città rappresentano le nostre entità, pertanto ogni nodo del nostro grafo rappresenterà una di queste sei città. La relazione invece che vogliamo evidenziare, è la lunghezza della strada che separa ciascuna coppia di città. Gli archi in questo senso ci vengono in aiuto.

Il grafo che abbiamo immaginato di disegnare, è riportato nella figura che segue:

<div style="text-align: center"><img src="/media/images/graph2.svg" /></div>

Nella figura qui sopra, in accordo con la definizione data all'inizio, è facile riconoscere l'insieme dei nodi, così formato

$$V = \{Venezia, Milano, Torino, Bologna, Roma, Palermo\}$$

e l'insieme degli archi

$$E = \{141, 279, 571, 154, 1270, 1423, 924\}$$

<br>

Le matrici di adiacenza
========================

Esistono altri modi per rappresentare i grafi. Uno dei modi più tradizionali prevede di utilizzare la cosiddetta <font color="#b3d313">matrice di adiacenza</font> (_adjacency matrix_). Una matrice di adiacenza non è altro che un modo compatto per esprimere le relazioni (gli archi) esistenti tra i vari nodi considerati. Ciascuna cella della matrice sarà valorizzata con il valore 1 se tra i due nodi considerati vi è un arco che li collega, 0 altrimenti.

<br>

$$
\begin{pmatrix}
/ & Venezia & Milano & Torino & Bologna & Roma & Palermo \\
Venezia & 0 & 1 & 0 & 1 & 0 & 1 \\
Milano & 1 & 0 & 1 & 0 & 1 & 0 \\
Torino & 0 & 1 & 0 & 0 & 0 & 0 \\
Bologna & 1 & 0 & 0 & 0 & 0 & 1 \\
Roma & 0 & 1 & 0 & 0 & 0 & 1 \\
Palermo & 1 & 0 & 0 & 1 & 1 & 0 \\
\end{pmatrix}
$$

<br>
Attraverso la lettura della matrice di adiacenza abbiamo la possibilità di scoprire (e volendo di contare), il numero di archi che possiede ciascun nodo considerato. La lettura della prima riga della matrice, ad esempio, ci dice che il nodo "Venezia", possiede tre collegamenti: "Milano", "Bologna" e "Palermo", corrispondenti alle tre celle valorizzate ad 1.

<br>

Gli alberi
========================

Una particolare tipologia di grafi è detta <font color="#b3d313">alberi</font>. Gli alberi sono grafi (solitamente) indiretti, privi di cicli (_loops_) e connessi.



Perché la teoria dei grafi è importante
------------------------------------------------------

| Grafo        | Nodi       | Archi               |
|--------------|------------|---------------------|
| Internet     | Computer   | Cavi di connessione |
| Web          | Pagine web | Hyperlink           |
| Rete neurale | Neuroni    | Sinapsi             |


[pathmin]: https://it.wikipedia.org/wiki/Cammino_minimo
[spplink]: https://en.wikipedia.org/wiki/Shortest_path_problem
[graphtheorylink]: https://en.wikipedia.org/wiki/Graph_theory
[nslink]: https://en.wikipedia.org/wiki/Network_science
