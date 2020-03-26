---
layout: mypost
title:  "Gradi, densità e componenti di una rete"
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

Se sostituiamo a questa formula $$\sum_{i=1}^n k_{i}$$ con _2m_, otteniamo una relazione che ci sarà utile più avanti:

$$c = \frac{2m}{n}$$

in cui leghiamo il grado medio di un nodo al rapporto tra le estremità del grafo (_2m_) sul numero totali di nodi (_n_).

Ora che abbiamo descritto formalmente il concetto di _grado_ di un nodo, proviamo ora a visualizzare dei casi reali dove esplorare la nozione di grado.

Immaginiamo di costruire il grafo dei nostri amici di Facebook. Cominceremo disegnando il nodo che ci rappresenta a cui aggiungeremo tanti archi quanti gli amici che possediamo sul social network. Inoltre, immaginiamo di conoscere anche gli amici dei nostri amici, potendo così ampliare il grafo in questione.

Il grado del nodo "Matteo" è pari a 4 (la linea tratteggiata indica la possibilità di aggiungere altri nodi). In questo caso esemplificativo, il grado di ciascun nodo rappresenta il numero di amici che ogni individuo possiede su Facebook.

 <div style="text-align: center"><img src="/media/images/socialgraph.svg" /></div>

Consideriamo ora un piccolo estratto del grafo che rappresenta la linea metropolitana di Londra.

<div style="text-align: center"><img src="/media/images/metrolondon.svg" /></div>

Cosa ci serve conoscere il grado di ciascun nodo in reti come quelle riportate qui sopra?

Beh, qui viene il bello! Il concetto di grado di un nodo è un concetto semplice (_"il numero di archi di ciascun nodo..._). Calcolare il grado di un nodo è altrettanto semplice: basta contare!

Se la rete è molto grande esistono diversi software che aiutano a contare gli archi dei nodi in maniera molto molto rapida, anche su reti complesse.

La vera sfida è stabilire un criterio con cui valutare il grado di ogni nodo.

Nella rete dei nostri amici di Facebook, la cosa più semplice da affermare è che il grado di ciascun nodo è direttamente proporzionale all'importanza del nodo considerato. In altre parole: più amici abbiamo, più siamo importanti, posto che dobbiamo essere d'accordo sul concetto di "importanza".

Da un altro punto di vista, potremmo affermare che più il nostro grado su Facebook è alto più faremo fatica a tenere monitorate le bachece di tutti i nostri contatti (immaginando di avere migliaia e migliaia di amici).

Rispetto invece alla rete metropolitana di Londra, più il grado di un nodo è alto, più saremo in grado, da quel nodo, di raggiungere posti diversi, e questo nel caso in esame è una conclusione positiva. D'altra parte, le stazioni più importanti di una rete metropolitana corrispondono alle stazioni da cui è possibile un numero elevato di altre stazioni. 
