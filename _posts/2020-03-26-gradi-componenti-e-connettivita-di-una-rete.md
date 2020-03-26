---
layout: mypost
title:  "Gradi, componenti e connettività di una rete"
date:   2020-03-26
categories: informatica
permalink: /:categories/:title
---

<p class="abstract">In questo articolo verranno illustrati i concetti di base della teoria dei grafi, la branca della matematica che si occupa dello studio delle reti (dette anche grafi per l'appunto). Dopo aver dato la definizone di grafo vedremo come possiamo rappresentarli e quali sono i concetti chiave per comprendere questioni più complesse. Concluderemo questo articolo con alcune note sull'importanza della teoria dei grafi nel mondo reale e nella vita di tutti i giorni.</p>

Gradi di un nodo
-----------------------

I <font color="#008cff">gradi</font> (_degree_) di un nodo sono il numero di archi che il nodo possiede. Rispetto al grafo d'esempio riportato nella figura che segue, possiamo affermare che il grado del nodo N3 è pari a 3, il grado del nodo N6 è pari a 5 e il grado del nodo N1 è pari a 2.

<div style="text-align: center"><img src="/media/images/degree1.svg" /></div>

Formalmente, per un grafo indiretto di _n_ nodi, il grado di ciascun nodo può essere calcolato a partire dalla sua matrice di adiacenza, così come espresso dalla formula che segue:

$$k_{i} = \sum{j=1}^n A_{i, j}$$  

dove $$k_{i}$4 indica il grado del nodo _i_.
