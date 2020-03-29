---
layout: mypost
title:  "Il grado dei nodi di una rete: l'importanza delle connessioni"
date:   2020-03-26
categories: informatica
permalink: /:categories/:title
---

<p class="abstract">Una proprietà chiave dei nodi di una rete è detta "grado". In questo articolo, dopo aver enunciato la definizione di grado di un nodo, verranno illustrate diverse situazioni in cui questo concetto gioca un ruolo importante. L'intento finale è quello di capire l'importanza delle connessioni tra nodi.</p>

Il grado di un nodo
-----------------------

Il <font color="#008cff">grado</font> (_degree_) di un nodo è il numero di archi che il nodo possiede.

Rispetto al grafo d'esempio riportato nella figura che segue, possiamo affermare che il grado del nodo <font color="#008cff">N3</font> è pari a 4, il grado del nodo <font color="#008cff">N6</font> è pari a 3 e il grado del nodo <font color="#008cff">N4</font> è pari a 2.

<div style="text-align: center"><img src="/media/images/degree1.svg" /></div>

Formalmente, per un grafo indiretto di _n_ nodi, il grado di ciascun nodo può essere calcolato a partire dalla sua matrice di adiacenza, così come espresso dalla formula seguente:

$$k_{i} = \sum_{j=1}^n A_{i, j}$$  

dove $$k_{i}$$ indica il grado del nodo _i_. Avremo per cui che $$k_{3}$$ = 4, $$k_{6}$$ = 3 e $$k_{4}$$ = 2.

Il grado è un parametro che quantifica il numero di collegamenti che ciascun nodo possiede in una determinata rete.

È come se chiedessimo ad un nostro amico "_hai dei fratelli o delle sorelle?_". La sua risposta stabilisce implicitamente il suo grado, che sarà pari a 0 nel caso in cui il nostro amico è figlio unico, 1 se ha un fratello o una sorella, 2 se ha più di un fratello o una sorella e così via.

Se continuiamo a studiare grafi indiretti, è possibile osservare un ulteriore fenomeno che a fare con il grado dei nodi.

Ogni arco altro non è che un segmento da un _nodo a_ ad un _nodo b_. Ogni vertice di questo segmento è detto <font color="#008cff">estremità</font>.

Ciascun arco di un grafo indiretto possiede due estremità equivalenti (in altri termini: non vi è un verso stabilito da una freccia).

In un grafo di _m_ archi allora, esisteranno in totale  _2m_ estremità, come è possibile constatare dalla figura che segue, dove le estremità di ciascun arco sono state evidenziate in giallo.

<div style="text-align: center"><img src="/media/images/endsedges.svg" /></div>
<br>
Da qui una prima semplice intuzione:

<font color="#008cff"> > il numero di estremità di un grafo indiretto corrisponde alla somma dei gradi di tutti i nodi.</font>

<br>
Ricordando che $$k_{i}$$ rappresenta il grado del nodo _i_-esimo, possiamo formalizzare il concetto intuitivo sopra descritto con la seguente formula:

$$2m = \sum_{i=1}^n k_{i}$$

Dalla formula appena riportata possiamo ricavare una nuova formula (equivalente alla precedente):

$$m = \frac{1}{2} \sum_{i=1}^n k_{i} = \frac{1}{2} \sum_{i, j} A_{i, j}$$

che formalizza così una seconda importante intuzione:

<font color="#008cff"> > il numero di archi in una rete indiretta può essere espresso come somma dei gradi dei nodi, diviso 2.</font>

<br>
L'utilizzo del fattore $$\frac{1}{2}$$ ci permette di evitare di contare due volte lo stesso arco

<br><br>

Il grado medio dei nodi
-----------------------

In un grafo indiretto
=========================
A questo punto, sulla scia delle semplici formule appena descritte, è possibile calcolare il <font color="#008cff">grado medio (<i>mean degree</i>) <i>c</i></font> di un nodo in un grafo indiretto:

$$c = \frac{1}{n} \sum_{i=1}^n k_{i}$$

Se sostituiamo la formula $$\sum_{i=1}^n k_{i}$$ con _2m_, otteniamo una relazione che ci sarà utile più avanti:

$$c_{out} = \frac{2m}{n} \ \ | \ grado \ medio \ rete \ indiretta $$

Definiamo così il grado medio dei nodi di una rete in funzione del rapporto tra le estremità del grafo (_2m_) ed il numero totali di nodi (_n_).

In un grafo diretto
=========================
Finora, abbiamo considerato esclusivamente grafi indiretti, ma è possibile misurare il grado dei nodi anche su **grafi diretti**, a patto di distinguere il <font color="#008cff">grado degli archi entranti</font> $$k_{i}^{in}$$ dal <font color="#008cff">grado degli archi uscenti</font> $$k_{i}^{out}$$.

Il grado totale di un nodo appartenente ad un grafo diretto sarà pari a

$$k_{tot} = k_{i}^{in} + k_{i}^{out}$$

da cui

$$k_{tot} = \sum_{i=1}^N k_{i}^{in} + \sum_{i=1}^N k_{i}^{out}$$

a patto di non voler distinguere gli archi entranti da quelli uscenti.

Il <font color="#008cff">numero totale di archi in una rete diretta</font> è dato da:

$$m = \sum_{i=1}^N k_{i}^{in} = \sum_{i=1}^N k_{i}^{out}$$

Il grado medio dei nodi di una rete diretta è dato invece dalla formula seguente:

$$c^{in} = \frac{1}{N} \sum_{i=1}^N k_{i}^{in} = c_{out} = \frac{1}{N} \sum_{i=1}^N k_{i}^{out} \ \ | \ grado \ medio \ rete \ diretta $$

<br><br>

Degree distribution
-----------------------

La <font color="#008cff">distribuzione dei gradi</font> (_degree distribution_) di una rete è la probabilità $$p_{k}$$, per cui, scegliendo in maniera casuale un nodo _i_ della rete, esso possiede esattamente un grado _k_.

$$p_{k} \ \ | \ degree \ distribution $$

La probabilità $$p_{k}$$ va normalizzata in modo che

$$ \sum_{k=1}^\infty p_{k} = 1$$

In una rete con _n_ nodi, la distribuzione dei gradi è data dall'istogramma normalizzato della relazione

$$ p_{k} = \frac{N_{k}}{N} $$

dove $$N_{k}$$ è il numero di nodi con grado _k_, mentre $$N$$ è il numero di nodi totali .

La _degree distribution_ è un concetto molto importante nello studio delle reti. Essa ci sarà utile quando parleremo ad esempio di _[scale-free networks][scalefreelink]_ e di altri concetti legati alle dinamiche di sviluppo di alcuni fenomeni su reti reali. Lo studio, ad esempio, della diffusione di un'epidemia, necessita (anche) di questo valore.

<br><br>

Studiare il grado dei nodi su semplici reti reali
-----------------------
Ora che abbiamo descritto formalmente il concetto di _grado_ di un nodo, proveremo a visualizzare dei semplici casi reali tramite i quali prendere confidenza con i concetti sopra esposti.

I nostri amici su Facebook
=========================

Immaginiamo di costruire il grafo dei nostri amici di Facebook. Cominceremo disegnando il nodo che ci rappresenta, per poi aggiungere tanti archi quanti gli amici che possediamo sul social network. Inoltre, immaginiamo di conoscere anche gli amici dei nostri amici, potendo così ampliare il grafo in questione.

Il grado del nodo <font color="#008cff">Matteo</font> è pari a 4 (la linea tratteggiata indica solamente la possibilità di aggiungere altri nodi). In questo caso esemplificativo, il grado di ciascun nodo rappresenta il numero di amici che ogni individuo possiede su Facebook.

 <div style="text-align: center"><img src="/media/images/socialgraph.svg" /></div>

 Nella rete dei nostri amici di Facebook, la cosa più semplice da affermare è che il grado di ciascun nodo è direttamente proporzionale all'importanza del nodo considerato. In altre parole: più amici possiede un individuo su Facebook, più quell'individuo è importante, a patto di essere d'accordo sul concetto di "importanza".

 Da un altro punto di vista, potremmo affermare che più il nostro numero di amici su Facebook è alto (e quindi il nostro grado), più faremo fatica a tenere monitorate le bachece di tutti i nostri contatti (immaginando di avere migliaia e migliaia di amici).

La metropolitana di Londra
=========================

Consideriamo ora un piccolo estratto del grafo che rappresenta la linea metropolitana di Londra.

<div style="text-align: center"><img src="/media/images/metroLondon1.svg" /></div>

In questo secondo caso, più il grado di un nodo è alto, più saremo in grado, da quel nodo, di raggiungere posti diversi. D'altra parte, le stazioni più importanti di una rete metropolitana corrispondono alle stazioni da cui è possibile raggiungere un elevato numero di nuove destinazioni.

In una rete metropolitana, le fermate che puntiamo a raggiungere hanno sempre due caratteristiche (una esplicita e una forse inconscia):

- puntiamo sempre a raggiungere la fermata più vicina a luogo che dobbiamo raggiungere (_caratteristica esplicita_ e aggiungerei anche ovvia, a meno di non voler gironzolare per la metropolitana a caso);

- quando siamo costretti a cambiare linea metropolitana, lo facciamo sempre grazie a delle stazioni con un elevato numero di nuove linee che si sviluppano da esse (e quindi con un elevato grado). Questa è la _caratteristica inconscia_, perché guida in maniera inconscia la scelta del nostro itinerario.

Naturalmente, se partendo dalla fermata X di una rete metropolitana dobbiamo raggiungere la fermata Y, la prima cosa in assoluto più importante da verificare, è che esista un cammino tra X e Y. Nel caso di uno spostamento in metropolitana, ci auspichiamo, solitamente, che questo cammino sia anche il più breve.

Nella figura che segue sono riportati i collegamenti disponibili dalla stazione di _Oxford Circus_, sulla sinistra, e di _Liverpool Street_, sulla destra.

<div style="text-align: center"><img src="/media/images/metroLondon2.svg" /></div>

Una rete scolastica
=========================

Consideriamo infine quest'ultimo esempio di _network_.

Nella figura che segue è riportato un estratto di una possibile rete di persone che lavorano in una scuola. I diversi nodi della rete sono collegati da archi che rappresentano la relazione _"lavora con"_.

Questa rete è fatta da 18 nodi. Ciascun nodo rappresenta le generiche persone <font color="#008cff">P1</font>, <font color="#008cff">P2</font>, <font color="#008cff">P3</font>, ..., <font color="#008cff">P18</font>. Queste 18 persone fanno tutte parte del personale scolastico, ma non tutte hanno lo stesso ruolo e pertanto, verosimilmente, ciascuno di loro avrà contatti con un numero diverso di altri individui.

Analizziamo un po' di relazioni, prendendo come riferimento la rete riportata di seguito.

<div style="text-align: center"><img src="/media/images/spread0.svg" /></div>

Il nodo <font color="#008cff">P13</font>, ad esempio, lavora direttamente con il nodo <font color="#008cff">P12</font>.

Il nodo <font color="#008cff">P4</font> invece, lavora a stretto contatto con il nodo <font color="#008cff">P11</font>, <font color="#008cff">P1</font> e <font color="#008cff">P2</font>.

Il nodo <font color="#008cff">P16</font> lavora con <font color="#008cff">P3</font>.

Il nodo <font color="#008cff">P3</font> infine, è evidentemente la persona che ha contatti con il maggior numero di individui.

Potremmo immaginare che il nodo <font color="#008cff">P13</font> sia il dirigente scolastico della scuola, <font color="#008cff">P12</font> il vice preside e <font color="#008cff">P11</font> il responsabile della segreteria.

Cominciamo allora a distinguere dei _cluster_ (dei raggruppamenti):

- il <font color="#ff0066">cluster della dirigenza</font> sarà formato dai nodi P13 e P12, preside e vice-preside.
- il <font color="#99cc00">cluster della segreteria</font> sarà formato dal responsabile della segreteria, il nodo P11, e dei suoi colleghi collaboratori, i nodi P4, P1 e P2.
- il <font color="#00ccff">cluster della classe</font> sarà formato dall'insegnante, il nodo P3, e da tutti i suoi alunni (i nodi P5, P14, P15, P16, P6, P7, P8, P19, P18, P9, P17, P10).

<div style="text-align: center"><img src="/media/images/schoolcluster.svg" /></div>

A questo punto come ci torna utile il concetto di grado dei nodi?

Il prossimo paragrafo ci aiuterà a condurre un'analisi un po' più complessa delle precedenti, che si servirà dei _cluster_ appena identificati e di una componente non banale nell'analisi delle reti: il tempo.

Di seguito vedremo come il grado di un nodo e il tempo che passa, giocano un ruolo fondamentale nella dinamica di reti come quella in esame.

L'influenza a scuola
=========================
Ora, immaginiamo che il nodo P13 si ammali di influenza. Quante persone potrà contagiare, rispetto alla sua rete di colleghi di lavoro? La risposta va cercata nel grado di quel nodo. Poiché P13 ha grado uno, esso potrà contagiare al più una persona.

<div style="text-align: center"><img src="/media/images/spread1.svg" /></div>

Quante persone potrà invece contagiare il nodo P4, se si ammalasse di influenza? Contiamo gli archi di P4: <P4, P11>, <P4, P2>, <P4, P1>. Il grado di P4 è pari a 3 e dunque saranno 3 le persone che P4 potrebbe potenzialmente contagiare.

<div style="text-align: center"><img src="/media/images/spread2.svg" /></div>

Infine, se si ammala di influenza il nodo P3, quante persone potrà potenzialmente contagiare nella sua rete di contatti con i colleghi? Il grado di P3 ammonta a 12. Sono dodici infatti, le persone che P3 potrebbe contagiare, recandosi al lavoro con l'influenza.

<div style="text-align: center"><img src="/media/images/highdegree.svg" /></div>

Negli esempi riportati fino a qui, abbiamo focalizzato esclusivamente delle fotografie delle reti prese in esame. Spesso però le reti devono modellare dei contesti in evoluzione, dinamici.

La rete analizzata poco fa potrebbe essere studiata anche in relazione alla componente temporale _t_.

Nell'esempio che segue, notiamo che al tempo _t0_ il nodo P13 ha l'influenza (il colore rosso indica la prorpietà "avere l'influenza").

<div style="text-align: center"><img src="/media/images/timein.svg" /></div>

Al tempo _t8_ invece, le persone influenzate sono molto di più. Questo perché tra il nodo p13 e il nodo p3 (i due estremi considerati), vi è almeno un cammino che li collega, rendendo possibile la trasmissione del virus influenzale.

Si noti l'arco tratteggiato che collega P1 a P3. Quell'arco giocherà un ruolo cruciale nella diffusione dell'influenza. Sapreste dire il perché?

<div style="text-align: center"><img src="/media/images/timeout.svg" /></div>

[scalefreelink]: https://it.wikipedia.org/wiki/Rete_a_invarianza_di_scala
