---
layout: mypost
title:  "Gradi, componenti e connettività di una rete"
date:   2020-03-26
categories: informatica
permalink: /:categories/:title
---

<p class="abstract">Dopo aver appreso i concetti chiave della teoria dei grafi, proveremo ora ad addentrarci in alcuni aspetti strutturali delle reti, così da essere in grado non solo di rappresentarle ma anche di analizzarle e studiarle.</p>

Gradi di un nodo
-----------------------

I <font color="#008cff">gradi</font> (_degree_) di un nodo sono il numero di archi che il nodo possiede. Rispetto al grafo d'esempio riportato nella figura che segue, possiamo affermare che il grado del nodo N3 è pari a 3, il grado del nodo N6 è pari a 5 e il grado del nodo N1 è pari a 2.

<div style="text-align: center"><img src="/media/images/degree1.svg" /></div>

Formalmente, per un grafo indiretto di _n_ nodi, il grado di ciascun nodo può essere calcolato a partire dalla sua matrice di adiacenza, così come espresso dalla formula che segue:

$$k_{i} = \sum_{j=1}^n A_{i, j}$$  

dove $$k_{i}$$ indica il grado del nodo _i_.

Se continuiamo a considerare grafi indiretti, allora possiamo osservare anche che ciascun arco di questi grafi possiede due estremità equivalenti. Se un grafo possiede _m_ archi, allora in totale esisteranno _2m_ estremità. Le estremità di ciascun arco sono state evidenziate in giallo di seguito.

<div style="text-align: center"><img src="/media/images/endsedges.svg" /></div>

Il numero di estremità di un grafo indiretto corrisponde anche alla somma dei gradi di tutti i vertici. Sia sempre $$k_{i}$$ il grado del nodo _i_; possiamo allora formalizzare questo concetto con la seguente formula:

$$2m = \sum_{i=1}^n k_{i}$$

oppure, con la formula equivalente:

$$m = \frac{1}{2} \sum_{i=1}^n k_{i} = \frac{1}{2} \sum_{i, j} A_{i, j}$$

A questo punto, sulla scia delle semplici formule appena descritte, è possibile calcolare il grado medio (_mean degree_) _c_ di un nodo in un grafo indiretto:

$$c = \frac{1}{n} \sum_{i=1}^n k_{i}$$

Se sostituiamo $$\frac{1}{n} \sum_{i=1}^n k_{i}$$ con _2m_ otteniamo una relazione che ci sarà utile più avanti:

$$c = \frac{2m}{n}$$
