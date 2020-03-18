---
layout: mypost
title:  "Che cos'è un grafo e come rappresentarlo"
date:   2020-01-09
categories: informatica
permalink: /:categories/:title
---

La [teoria dei grafi][graphtheorylink], è una branca della matematica e dell'informatica che si occupa di studiare degli oggetti chiamati per l'appunto _grafi_.

Un grafo _G_ è una coppia di insiemi, e più precisamente è la coppia formata dall'insieme _V_ dei nodi (_vertices_ in inglese), e dall'insieme _E_ degli archi (_edges_ in inglese).

$$G = (V, E)$$

Un grafo rappresenta un modello astratto per descrivere un determinato contesto reale. In generale, si utilizzano i nodi per rappresentare le _entità_ del dominio analizzato, mentre gli archi rappresenteranno le _relazioni_ che intercorrono tra le diverse entità coinvolte.

Alla luce di questa premesse, è importante ricordare che i grafi sono strumenti adatti a modellare dei contesti "di relazione". Viceversa, laddove non vi sono delle relazioni evidenti tra i soggetti coinvolti, i grafi probabilmente non rappresentano lo strumento di modellazione più adatto.

Una delle potenzialità dei grafi, e la facilità con cui li possiamo rappresentare. Alcuni esempi riportati di seguito aiuteranno il lettore a prendere confidenza con questi oggetti matematici.

![graph1](/media/images/graph1.png)

Nella figura sono stati messi in evidenza i nodi (N1, N2, N3, N4, N5 e N6) e gli archi (A1, A2, A3, A4, A5 e A6). "Leggere" un grafo è semplice (quando il grafo è piccolo come quello nell'esempio). Nel grafo in figura ad esempio, leggiamo che il nodo N1 è collegato al nodo N2, mediante l'arco A1. Allo stesso modo il nodo N5 è collegato al nodo N4 dall'arco A4. Un collegamento tra nodi, avviene per mezzo di uno o più archi che ci permettono di raggiungere i due nodi in una o nell'altra direzione. Non è necessario che ci sia _esattamente_ un arco tra due nodi per definire quei due nodi "collegati". Il nodo N6, ad eempio, è sicuramente collegato al nodo N4 mediante l'arco A5, e al nodo N5 mediante l'arco A3. Ma il nodo N6 è collegato anche al nodo N3, mediante gli archi A5 e A6 oppure al nodo N1, mediante gli archi A5, A6, A7 e A1.


[graphtheorylink]: https://en.wikipedia.org/wiki/Graph_theory
