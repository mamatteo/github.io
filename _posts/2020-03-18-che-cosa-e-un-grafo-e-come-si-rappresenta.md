---
layout: mypost
title:  "Che cos'è un grafo e come rappresentarlo"
date:   2020-01-09
categories: informatica
permalink: /:categories/:title
---

<p class="abstract">In questo articolo verranno illustrati i concetti di base della teoria dei grafi, la branca della matematica che si occupa dello studio delle reti (dette anche grafi per l'appunto). Dopo aver dato la definizone di grafo vedremo come possiamo rappresentarli e quali sono i concetti chiave per comprendere questioni più complesse. Concluderemo questo articolo con alcune note sull'importanza della teoria dei grafi nel mondo reale e nella vita di tutti i giorni.</p>

Cosa sono i grafi
-----------------------

La [<font color="#b3d313">teoria dei grafi</font>][graphtheorylink] è una branca della matematica e dell'informatica che si occupa di studiare degli oggetti chiamati _grafi_.

Un grafo _G_ è definito dalla coppia di insiemi _V_ dei <font color="#b3d313">nodi</font> (_vertices_ in inglese), ed _E_ degli <font color="#b3d313">archi</font> (_edges_ in inglese).

$$G = (V, E)$$

I nodi di un grafo servono a rappresentare le _entità_ del dominio in esame, mentre gli archi rappresenteranno le _relazioni_ che intercorrono tra le diverse entità coinvolte. In questo senso, un grafo rappresenta un modello astratto per descrivere tutti quei contesti in cui siamo in grado di individuare delle entità (città, squadre di calcio, persone, etc.), connesse tra loro da determinate relazioni (strade, partite, rapporti affettivi).

I matematici, utilizzano la lettera _n_ per denotare il numero dei nodi di un grafo, e la lettera _m_ per denotare invece il numero di archi. Dato un grafo G = (V, E) quindi, possiamo denotare la cardinalità di V con _n_ e la cardinalità di E con _m_.

I grafi sono quindi utili strumenti per modellare contesti "di relazione". Viceversa, laddove non vi sono delle relazioni evidenti tra i soggetti coinvolti, i grafi probabilmente non rappresentano lo strumento di modellazione più adatto.

Il modo più semplice per collegare due nodi, comporta che tra essi vi sia uno ed un solo arco e quindi una ed una sola relazione. Nulla però vieta che questi due nodi siano collegati da più di un arco. In questo caso parleremo di <font color="#b3d313">multiarchi</font> (_multiedges_).

Come mostrato nella figura seguente, un multiarco è utile quando vogliamo rappresentare più informazioni contemporaneamente. Nell'esempio riportato in figura, tra il nodo N1 e il nodo N2 è stato messo in evidenza un primo arco che esprime la distanza che intercorre tra i due nodi e un secondo arco che esprime la capacità del collegamento.

Immaginiamo ad esempio che i due nodi rappresentino due appartamenti diversi di uno stesso condominio, e che gli archi rappresentino le condutture idrauliche. Ci interessa quindi conoscere la distanza dei due appartamenti (primo arco) e la capacità del tubo che li collega (secondo arco).

<div style="text-align: center"><img src="/media/images/graph3.svg" /></div>

<br>
Un altro concetto chiave della teoria dei grafi riguarda la <font color="#b3d313">direzione degli archi</font>. Diremo che un arco è <font color="#b3d313">indiretto</font>, se esiste un arco tra il nodo N1 e il nodo N2 percorribile da N1 a N2 e viceversa in maniera del tutto equivalente. Diremo invece che un arco è <font color="#b3d313">diretto</font>, se esiste un arco tra il nodo N1 e il N2 percorribile solo in un senso (da N1 a N2 oppure da N2 a N1).

Nella figura seguente viene mostrato un esempio di arco diretto. Un arco diretto è riconoscibile dalla freccia posta in una delle sue due estremità.

<div style="text-align: center"><img src="/media/images/graph4.svg" /></div>

Un <font color="#b3d313">grafo orientato</font> è un grafo in cui tutti i suoi archi sono diretti. <br>
Un <font color="#b3d313">grafo non orientato</font> è un grafo in cui tutti i suoi archi sono indiretti.

<br>
Spesso un sinonimo di grafo è <font color="#b3d313">rete</font> (_network_). Lo studio dei grafi è anche detto studio delle reti o [_network science_][nslink]. Le reti non vengono studiate solo dalla matematica, ma anche dalla fisica, dall'economia, dalla chimica e dalla sociologia.

<br>


Come si rappresenta un grafo
------------------------------------

Disegnare i grafi
==================

Una delle potenzialità dei grafi, e la semplicità con cui li possiamo rappresentare. Alcuni esempi riportati di seguito aiuteranno il lettore a prendere confidenza con questi oggetti matematici.

<div style="text-align: center"><img src="/media/images/graph1.svg" /></div>

Il grafo della figura è composto dall'insieme dei seguenti nodi:

$$V = \{N1, N2, N3, N4, N5, N6\}$$

e dal seguente insieme di archi:

$$E = \{A1, A2, A3, A4, A5, A6\}$$

"Leggere" un grafo solitamente è semplice (a patto che il grafo sia piccolo, cioè formato da pochi nodi).

In riferimento al grafo riportato in figura, ad esempio, possiamo affermare che il nodo N1 è collegato al nodo N2 mediante l'arco A1. Allo stesso modo il nodo N5 è collegato al nodo N4 mediante l'arco A4.

Non è necessario che ci sia _esattamente un arco_ tra due nodi per far sì che quei due nodi siano effettivamente "collegati". Il nodo N6, ad esempio, è sicuramente collegato al nodo N4 mediante l'arco A5 e al nodo N5 mediante l'arco A3. Ma il nodo N6 è collegato anche al nodo N3, mediante gli archi A5 e A6 oppure al nodo N1, mediante gli archi A5, A6, A7 e A1.

Forse ti sarai accorto che esistono anche altre strade che collegano il nodo N6 al nodo N1. In generale esistono _k_ strade che collegano due nodi in un grafo (con _k_ che va da 0 ad un numero finito _t_).

Diversi algoritmi studiati dall'informatica operano sia sul numero di strade che collegano una data coppia di nodi sia sul numero di archi che collegano due nodi.

<hr>
<br>
Ridisegniamo ora il grafo precedente calandolo ad un contesto reale. Immaginiamo di voler disegnare il grafo di sei città italiane, diciamo Venezia, Milano, Torino, Bologna, Roma e Palermo. Queste città rappresentano le nostre entità, pertanto ogni nodo del nostro grafo rappresenterà una di queste sei città. La relazione invece che vogliamo evidenziare è la lunghezza della strada che separa ciascuna coppia di città. Gli archi in questo senso ci vengono in aiuto.

Il grafo in esame è riportato nella figura che segue:

<div style="text-align: center"><img src="/media/images/graph2.svg" /></div>

Nella figura qui sopra, in accordo con la definizione data all'inizio, è facile riconoscere l'insieme dei nodi

$$V = \{Venezia, Milano, Torino, Bologna, Roma, Palermo\}$$

e l'insieme degli archi

$$E = \{141, 279, 571, 154, 1270, 1423, 924\}$$

Questo ultimo esempio ci aiuta a capire in che modo un modello astratto come quello dei grafi può rappresentare in maniera semplice ma efficace alcuni scenari reali.

<br>

Le matrici di adiacenza
========================

Esistono anche dei modi più compatti per rappresentare i grafi. Uno dei modi più tradizionali prevede di utilizzare la cosiddetta <font color="#b3d313">matrice di adiacenza</font> (_adjacency matrix_). Una matrice di adiacenza non è altro che un modo compatto per esprimere le relazioni esistenti tra i vari nodi considerati. Ciascuna cella della matrice sarà valorizzata con il valore 1 se tra i due nodi considerati vi è un arco che li collega, 0 altrimenti.

Di seguito è riporata la matrice di adiacenza del grafo delle città disegnato nel paragrafo precedente.

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
Attraverso la lettura della matrice di adiacenza abbiamo la possibilità di scoprire (e volendo di contare), il numero di archi che possiede ciascun nodo considerato. La lettura della prima riga della matrice, ad esempio, ci informa che il nodo Venezia possiede dei collegamenti con le città di Milano, Bologna e Palermo, corrispondenti alle tre celle valorizzate ad 1.

<br>

Dizionario elementare
------------------------------------
Di seguito verranno riportate alcune definizioni di base dei grafi. Queste definizioni saranno utili a capire via via concetti più complessi.

<br>
**CAMMINO** | Chiameremo <font color="#b3d313">cammino</font> (_path_), una squenza ordinata di archi.

$$cammino = (a_{1}, \dots, a_{m})$$

In riferimento alla figura riportata di seguito, possiamo affermare che tra il nodo N6 e il nodo N2 esiste il cammino formato dagli archi <A6, A7, A1>.

<div style="text-align: center"><img src="/media/images/path.svg" /></div>

Nota:
- tra due nodi può esistere più di un cammino (riesci a trovare 3 cammini diversi che collegano il nodo N1 al nodo N4?);
- spesso per l'informatica è utile individuare, soprattutto su reti complesse, il cammino più breve ([cammino minimo][pathmin]) che collega due nodi della rete. Esistono problemi famosi riferiti a questa idea, come lo _[shortest path problem][spplink]_;
- una coppia di nodi in una rete potrebbe anche non essere collegata da alcun cammino.

<br>
**CICLO** | Parleremo di <font color="#b3d313">ciclo</font> (_loop_), tutte le volte in cui dovremmo riferirci ad un cammino che partendo da un determinato nodo, dopo un numero _m_ di archi ritorna allo stesso nodo dal quale siamo partiti.

$$ciclo = (a_{1}, a_{2}, a_{3}, \dots, a_{1})$$

Nel grafo della figura seguente esiste un ciclo che partendo dal nodo N1 ritorna al nodo N1. Il ciclo in questione è formato dagli archi <A1, A2, A3, A4, A5, A6, A7>. Questo cammino non è l'unico ciclo che insiste sul nodo N1 e non è nemmeno il più breve. Nella figura è stato volutamente evidenziato di rosso l'arco A7, che denota la possibilità di chiudere un ciclo su N1 con un cammino molto più breve del precedente (il cammino <A1, A2, A7>).

<div style="text-align: center"><img src="/media/images/loops.svg" /></div>

<br>
**CONNETTIVITÀ** | Dato un grafo G = (V, E) due vertici v, u $$\in$$ V si dicono <font color="#b3d313">connessi</font> se esiste un cammino con estremi v e u. Se tale cammino non esiste, v e u sono detti <font color="#b3d313">sconnessi</font>.

Di conseguenza, un grafo G = (V, E) è detto connesso se, per ogni coppia di vertici (u, v) $$\in$$ V, esiste un cammino che collega u a v. Nel grafo riportato di seguito, comunque scegliamo due nodi esisterà sempre un cammino che li collega. Il grafo che segue è un esempio di <font color="#b3d313">grafo connesso</font>.

<div style="text-align: center"><img src="/media/images/connectedgraph.svg" /></div>

Se però eliminiamo gli archi evidenziati in arancione, ecco che sconnettiamo il grafo. Il grafo che segue è un esempio di <font color="#b3d313">grafo sconnesso</font>.

<div style="text-align: center"><img src="/media/images/disconnectedgraph.svg" /></div>

Nel grafo riportato qui sopra, non è possibile raggiungere il nodo N11 da un nodo diverso dal nodo N10, così come non è possibile raggiungere i nodi N7, N8 e N9 a partire da un qualsiasi nodo diverso da questi tre.

L'operazione di eliminazione di uno o più archi da un grafo è detta operazione di <font color="#b3d313">taglio</font>.

Anche in questo caso esistono molti algoritmi interessanti che si occupano di questa questione. Uno dei problemi più noti in questo ambito prende il nome di _[minimum cut problem][mincutlink]_.

<br>
**RETI PESATE** | In molti contesti reali, gli archi possono essere corredati da un determinato peso, che determina "quanto vale" la relazione che l'arco esprime. Ci sono quindi delle situazioni in cui è utile esprimere la forza, il peso o in generale il valore degli archi rappresentati.

Le reti i cui archi possiedono un peso sono dette <font color="#b3d313">reti pesate</font> (_weighted networks_). Nella figura che segue è riportato un esempio di rete pesata. Ogni arco è etichettato con un numero reale che ne determina il peso. In relazione a questo tipo di reti, potrebbe essere interessante chiederci qual è il cammino di peso minore o maggiore che collega due nodi, inteso come la somma dei pesi di tutti gli archi che collegano il primo nodo al secondo.

<div style="text-align: center"><img src="/media/images/weighnet.svg" /></div>


<br>

Grafi particolari
-----------------------

Gli alberi
========================

Una particolare tipologia di grafi è detta <font color="#b3d313">alberi</font>.

Gli alberi sono grafi indiretti, privi di cicli e connessi. Di seguito è riportato un esempio di albero.

<div style="text-align: center"><img src="/media/images/tree1.svg" /></div>

Dal punto di vista topologico, un albero può essere disegnato in molti modi diversi, ovvero distribuendo i suoi nodi in maniera diversa nello spazio. A volte però, si rivela più utile rappresentarlo in maniera, per così dire, "più ordinata":

<div style="text-align: center"><img src="/media/images/tree2.svg" /></div>

Gli alberi sono spesso rappresentati a partire dalla loro radice. La radice di un "albero informatico", a differenza di un albero vero e proprio, è situata in cima all'albero e non a terra. Il nodo privo di nodi genitori è detto <font color="#b3d313">nodo radice</font> (_root node_). Nella figura seguente è stato colorato di blu il nodo radice N1. I nodi finali di quest'albero (ovvero i nodi che non possiedono nodi figli), sono detti <font color="#b3d313">foglie</font> (_leaf_) dell'albero.

<div style="text-align: center"><img src="/media/images/roottree.svg" /></div>

Gli alberi sono oggetti matematici ancora più semplici dei grafi, eppure godono di alcune interessanti proprietà, elencate di seguito:

- poiché in un albero non esistono cicli, esiste un solo cammino tra ogni coppia di nodi;
- un albero di _n_ nodi, possiede sempre esattamente _n - 1_ archi;

Lasciamo al lettore dimostrare e convincersi di queste proprietà.


Perché la teoria dei grafi è importante
------------------------------------------------------
Nella vita reale, esistono moltissimi contesti rappresentabili come una rete. Internet, intesa come l'insieme di computer connessi fra loro, è la rete per eccellenza, ma solo perché è utilizzata da un numero elevatissimo di persone in tutto il mondo. Esistono però molti altri ambiti nei quali sono presenti delle reti, anche di fondamentale importanza per l'essere umano. Il cervello è modellabile come una rete, dove i nodi sono rappresentati dai neuroni e gli archi dalle sinapsi. Ma anche le persone che incontriamo ogni giorno, in famiglia o al lavoro, formano assieme a noi una gigantesca rete umana.

Con l'avvento delle tecnologie digitali, le reti non hanno fatto altro che aumentare in tutto il mondo. Non solo: le reti esistenti sono cresciute a dismisura, permttendoci di affermare che oggi siamo tutti interconnessi.

L'avvento della rete internet, non ha solo collegato ciascuno di noi ad altre persone, ma ha coinvolto anche gli oggetti, dagli smartphone ai frigoriferi, che oggi fanno ormai parte di una sorta di rete globale.

La teoria dei grafi è quella branca della matematica che si occupa di studiare queste reti, e pertanto, risulta importante avere degli strumenti rigorosi per analizzare e misurare l'impatto che queste reti hanno tanto su singoli nodi che la compongono, quanto sull'intero sistema.

[mincutlink]: https://en.wikipedia.org/wiki/Minimum_cut
[pathmin]: https://it.wikipedia.org/wiki/Cammino_minimo
[spplink]: https://en.wikipedia.org/wiki/Shortest_path_problem
[graphtheorylink]: https://en.wikipedia.org/wiki/Graph_theory
[nslink]: https://en.wikipedia.org/wiki/Network_science
