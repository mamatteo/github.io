---
layout: mypost
title:  "Che cos'è un grafo e come rappresentarlo"
date:   2020-01-09
categories: informatica
permalink: /:categories/:title
---

La [<font color="#eb3b5a">teoria dei grafi</font>][graphtheorylink], è una branca della matematica e dell'informatica che si occupa di studiare degli oggetti chiamati per l'appunto _grafi_.

Un grafo _G_ è una coppia di insiemi, e più precisamente è la coppia formata dall'insieme _V_ dei nodi (_vertices_ in inglese), e dall'insieme _E_ degli archi (_edges_ in inglese).

$$G = (V, E)$$

Un grafo rappresenta un modello astratto per descrivere un determinato contesto reale. In generale, si utilizzano i nodi per rappresentare le _entità_ del dominio analizzato, mentre gli archi rappresenteranno le _relazioni_ che intercorrono tra le diverse entità coinvolte.

Alla luce di questa premesse, è importante ricordare che i grafi sono strumenti adatti a modellare dei contesti "di relazione". Viceversa, laddove non vi sono delle relazioni evidenti tra i soggetti coinvolti, i grafi probabilmente non rappresentano lo strumento di modellazione più adatto.

Una delle potenzialità dei grafi, e la facilità con cui li possiamo rappresentare. Alcuni esempi riportati di seguito aiuteranno il lettore a prendere confidenza con questi oggetti matematici.

![graph1](/media/images/graph1.svg)

Nella figura sono stati messi in evidenza i nodi (N1, N2, N3, N4, N5 e N6) e gli archi (A1, A2, A3, A4, A5 e A6).

"Leggere" un grafo è semplice (quando il grafo è piccolo come quello nell'esempio). Nel grafo in figura ad esempio, leggiamo che il nodo N1 è collegato al nodo N2, mediante l'arco A1. Allo stesso modo il nodo N5 è collegato al nodo N4 dall'arco A4. Un collegamento tra nodi, avviene per mezzo di uno o più archi che ci permettono di raggiungere i due nodi in una o nell'altra direzione. Non è necessario che ci sia _esattamente_ un arco tra due nodi per definire quei due nodi "collegati". Il nodo N6, ad eempio, è sicuramente collegato al nodo N4 mediante l'arco A5, e al nodo N5 mediante l'arco A3. Ma il nodo N6 è collegato anche al nodo N3, mediante gli archi A5 e A6 oppure al nodo N1, mediante gli archi A5, A6, A7 e A1.

Forse ti sarai accorto che esistono anche altre strade che collegano il nodo N6 al nodo N1. In generale, in un grafo, possono esistere _n_ strade che collegano due nodi in un grafo. Diversi algoritmi studiati dall'informatica operano proprio sulle lunghezze delle strade che collegano due o più nodi di un grafo, ma non ne parleremo in questo articolo.

Quel che è importante aver capito fin qui, è che un grafo rappresenta una serie di relazioni tra entità, mediante i suoi nodi e i suoi archi.

Immaginiamo di ridisegnare il grafico precedente, calandolo ad un contesto reale. Immaginiamo di voler disegnare il grafo di sei città italiane, diciamo Venezia, Milano, Torino, Bologna, Roma e Palermo. Queste saranno le nostre entità, pertanto ogni nodo del nostro grafo rappresenterà una di queste sei città. La relazione invece che vogliamo evidenziare, è la lunghezza della strada che separa ciascuna coppia di città. Gli archi in questo senso ci vengono in aiuto.

Il grafo che abbiamo immaginato di disegnare, è riportato nella figura che segue:

![graph2](/media/images/graph2.svg){: .center-image }
<div style="text-align: center"><img src="/media/images/graph2.svg" /></div>

Nella figura qui sopra, in accordo con la definizione data all'inizio, individuiamo l'insieme dei nodi

$$V = \{Venezia, Milano, Torino, Bologna, Roma, Palermo\}$$

e l'insieme degli archi

$$E = \{141, 279, 571, 154, 1270, 1423, 924\}$$



[graphtheorylink]: https://en.wikipedia.org/wiki/Graph_theory
