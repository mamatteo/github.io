---
layout: mypost
title:  "Il grado dei nodi di una rete: l'importanza delle connessioni"
date:   2020-03-30
categories: informatica
permalink: /:categories/:title
---

<p class="abstract">Il grado di un nodo è una proprietà fondamentale della teoria delle reti. In questo articolo, dopo aver enunciato alcune definizioni formali, veranno presentate diverse situazioni in cui questo concetto gioca un ruolo importante. L'intento finale è quello di capire in che modo le conessioni tra nodi giocano un ruolo importante sia a livello locale, sia a livello globale.</p>

<i><font color="#f03434">Prima di cominciare</font><br>
Se già conosci le fondamenta teoriche della teoria dei grafi, prosegui pure la lettura. Probabilmente ti imbatterai in altri concetti a te già noti, oppure ne impareri di nuovi.
Se invece conosci poco o nulla della teoria dei grafi, ti suggerisco di cominciare dall'articolo ["Cos'è un grafo e come rappresentarlo"][mamatteonetsci1], che introduce i concetti propedeutici alla comprensione di questo articolo.</i>
<hr>

<br>

Il grado di un nodo
-----------------------

Il <font color="#008cff">grado</font> (_degree_) di un nodo è il numero di archi che il nodo possiede.

Nel grafo riportato in figura, il grado del nodo <font color="#008cff">N3</font> è pari a 4, il grado del nodo <font color="#008cff">N6</font> è pari a 3 e il grado del nodo <font color="#008cff">N4</font> è pari a 2.

<div style="text-align: center"><img src="/media/images/degree1.svg" /></div>

Formalmente, per un grafo indiretto di _n_ nodi, il grado di ciascun nodo può essere calcolato a partire dalla sua matrice di adiacenza, così come espresso dalla formula seguente:

$$k_{i} = \sum_{j=1}^n A_{i, j}$$  

dove $$k_{i}$$ indica il grado del nodo _i_. Per cui, rispetto al grafo della figura precedente, abbiamo che $$k_{3}$$ = 4, $$k_{6}$$ = 3 e $$k_{4}$$ = 2.

Se chiedessimo ad un nostro amico "_hai dei fratelli o delle sorelle?_", la sua risposta stabilirebbe il suo grado, che sarà pari a 0 nel caso in cui il nostro amico è figlio unico, 1 se ha un fratello o una sorella, 2 se ha più di un fratello o una sorella e così via.

Nei grafi indiretti come quelli che stiamo analizzando, il verso degli archi non è importante. Ogni arco, non è altro che un segmento da un _nodo a_ ad un _nodo b_. Ogni vertice di questo segmento è detto <font color="#008cff">estremità</font>.

In un grafo di _m_ archi esisteranno in totale  _2m_ estremità, come è possibile constatare dalla figura che segue, dove le estremità di ogni arco sono state evidenziate in giallo.

<div style="text-align: center"><img src="/media/images/endsedges.svg" /></div>
<br>
Da qui una prima semplice intuzione:

<font color="#008cff"> > il numero di estremità di un grafo indiretto corrisponde alla somma dei gradi di tutti i nodi del grafo.</font>

<br>
Ricordando che $$k_{i}$$ rappresenta il grado del nodo _i_-esimo, possiamo formalizzare il concetto appena descritto con la seguente formula:

$$2m = \sum_{i=1}^n k_{i}$$

Dalla formula appena riportata possiamo ricavare una nuova formula (equivalente alla precedente):

$$m = \frac{1}{2} \sum_{i=1}^n k_{i} = \frac{1}{2} \sum_{i, j} A_{i, j}$$

che formalizza così una seconda importante intuzione:

<font color="#008cff"> > il numero di archi in una rete indiretta può essere espresso come somma dei gradi dei nodi del grafo diviso 2.</font>

<br>
L'utilizzo del fattore $$\frac{1}{2}$$ ci permette di evitare di contare due volte lo stesso arco.

<br>

Il grado medio dei nodi
-----------------------

In un grafo indiretto
=========================
Sulla scia delle semplici formule appena descritte è possibile calcolare il <font color="#008cff">grado medio (<i>mean degree</i>) <i>c</i></font> di un nodo in un grafo indiretto con la seguente formula:

$$c = \frac{1}{n} \sum_{i=1}^n k_{i}$$

Se sostituiamo la formula $$\sum_{i=1}^n k_{i}$$ con _2m_, otteniamo una relazione che ci sarà utile più avanti:

$$c_{out} = \frac{2m}{n} \ \ | \ grado \ medio \ rete \ indiretta $$

Definiamo così il grado medio dei nodi di una rete in funzione del rapporto tra le estremità del grafo (_2m_) ed il numero totali di nodi (_n_).

In un grafo diretto
=========================
In un grafo diretto, è importante distinguere il <font color="#008cff">grado degli archi entranti</font> $$k_{i}^{in}$$ dal <font color="#008cff">grado degli archi uscenti</font> $$k_{i}^{out}$$.

Il grado totale di un nodo _i_ sarà data dalla somma dei suoi archi entranti più la somma dei sui archi uscenti. Per cui:

$$k_{tot} = k_{i}^{in} + k_{i}^{out}$$

da cui

$$k_{tot} = \sum_{i=1}^n k_{i}^{in} + \sum_{i=1}^n k_{i}^{out}$$

Il <font color="#008cff">numero totale di archi in una rete diretta</font> invece, è dato da:

$$m = \sum_{i=1}^n k_{i}^{in} = \sum_{i=1}^n k_{i}^{out}$$

da cui si ricava la formula del grado medio dei nodi in una rete diretta:

$$c^{in} = \frac{1}{n} \sum_{i=1}^n k_{i}^{in} = c_{out} = \frac{1}{n} \sum_{i=1}^n k_{i}^{out} \ \ | \ grado \ medio \ rete \ diretta $$

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

La _degree distribution_ è un concetto molto importante nello studio delle reti. Essa ci sarà utile quando parleremo ad esempio di _[scale-free networks][scalefreelink]_ e di altri concetti legati alle dinamiche di sviluppo di alcuni fenomeni su reti reali. Lo studio, ad esempio, della diffusione di un'epidemia, necessita anche di questo valore.

<br>

Studiare il grado dei nodi su semplici reti reali
-----------------------
Ora che abbiamo descritto formalmente il concetto di _grado_ di un nodo, proveremo a visualizzare dei semplici casi reali tramite i quali prendere confidenza con i concetti sopra esposti.

I nostri amici su Facebook
=========================

Immaginiamo di costruire il grafo dei nostri amici di Facebook. Cominceremo disegnando il nodo che ci rappresenta, per poi aggiungere tanti archi quanti gli amici che possediamo sul social network. Inoltre, immaginiamo di conoscere anche gli amici dei nostri amici, potendo così ampliare il grafo in questione.

Il grado del nodo <font color="#008cff">Matteo</font> è pari a 4 (la linea tratteggiata indica solamente la possibilità di aggiungere altri nodi). In questo caso esemplificativo, il grado di ciascun nodo rappresenta il numero di amici che ogni individuo possiede su Facebook.

 <div style="text-align: center"><img src="/media/images/socialgraph.svg" /></div>

 Nella rete dei nostri amici di Facebook, la cosa più semplice da affermare è che il grado di ciascun nodo è direttamente proporzionale all'importanza del nodo considerato. In altre parole: più amici possiede un individuo su Facebook, più quell'individuo è importante (sul social network). Dovremmo poi essere concordi sul concetto di "importanza", ma questa è un'altra questione.

 Da un altro punto di vista, potremmo affermare che più il nostro numero di amici su Facebook è alto (e quindi il nostro grado), più faremo fatica a tenere monitorate le bachece di tutti i nostri contatti.

 Le interpretazioni che possiamo dare al grado di un nodo, come vedete, sono diverse.

La metropolitana di Londra
=========================

Consideriamo ora un piccolo estratto del grafo che rappresenta la linea metropolitana di Londra.

<div style="text-align: center"><img src="/media/images/metroLondon1.svg" /></div>

In questo secondo caso, più il grado di un nodo è alto, più saremo capaci, da quel nodo, di raggiungere posti diversi. D'altra parte, le stazioni più importanti di una rete metropolitana corrispondono alle stazioni da cui è possibile raggiungere un elevato numero di nuove destinazioni.

In una rete metropolitana le fermate siamo soliti a raggiungere hanno sempre due caratteristiche (una esplicita e una forse inconscia):

- puntiamo sempre a raggiungere la fermata più vicina a luogo che dobbiamo raggiungere (_caratteristica esplicita_ e aggiungerei anche ovvia, a meno di non voler gironzolare per la metropolitana a caso);

- quando siamo costretti a cambiare linea metropolitana, lo facciamo sempre grazie a delle stazioni con un elevato numero di nuove linee che si sviluppano da esse (e quindi con un elevato grado). Questa è la _caratteristica inconscia_, perché guida in maniera inconscia la scelta del nostro itinerario.

Naturalmente, se partendo dalla fermata X di una rete metropolitana dobbiamo raggiungere la fermata Y, la prima cosa in assoluto più importante da verificare, è che esista un cammino tra X e Y. Nel caso di uno spostamento in metropolitana, ci auspichiamo, solitamente, che questo cammino sia anche il più breve.

Nella figura che segue sono riportati i collegamenti disponibili dalla stazione di _Oxford Circus_, sulla sinistra, e di _Liverpool Street_, sulla destra, due grosse stazioni metropolitane della capitale inglese.

<div style="text-align: center"><img src="/media/images/metroLondon2.svg" /></div>

<br>
## La rete di una scuola

Consideriamo infine quest'ultimo esempio di _network_.

Nella figura che segue è riportato un estratto di una possibile rete di persone che lavorano in una scuola. I diversi nodi della rete sono collegati da archi che rappresentano la relazione _"lavora con"_.

Questa rete è fatta da 18 nodi. Ciascun nodo rappresenta le generiche persone <font color="#008cff">P1</font>, <font color="#008cff">P2</font>, <font color="#008cff">P3</font>, ..., <font color="#008cff">P18</font>. Queste 18 persone fanno tutte parte del personale scolastico, ma non tutte hanno lo stesso ruolo e pertanto, verosimilmente, ciascuna di loro avrà contatti con un numero diverso di altri individui.

Analizziamo un po' di relazioni, prendendo come riferimento la rete riportata di seguito.

<div style="text-align: center"><img src="/media/images/spread0.svg" /></div>

Il nodo <font color="#008cff">P13</font>, ad esempio, lavora direttamente con il nodo <font color="#008cff">P12</font>.

Il nodo <font color="#008cff">P4</font> invece, lavora a stretto contatto con il nodo <font color="#008cff">P11</font>, <font color="#008cff">P1</font> e <font color="#008cff">P2</font>.

Il nodo <font color="#008cff">P16</font> lavora con <font color="#008cff">P3</font>.

Il nodo <font color="#008cff">P3</font> infine, è evidentemente la persona che ha contatti con il maggior numero di individui.

Potremmo a questo punto immaginare che il nodo <font color="#008cff">P13</font> sia il dirigente scolastico della scuola, <font color="#008cff">P12</font> il vice preside e <font color="#008cff">P11</font> il responsabile della segreteria.

Cominciamo allora a distinguere dei _cluster_ (dei raggruppamenti):

- il <font color="#ff0066">cluster della dirigenza</font> sarà formato dai nodi P13 e P12, preside e vice-preside.
- il <font color="#99cc00">cluster della segreteria</font> sarà formato dal responsabile della segreteria, il nodo P11, e dei suoi colleghi collaboratori, i nodi P4, P1 e P2.
- il <font color="#00ccff">cluster della classe</font> sarà formato dall'insegnante, il nodo P3, e da tutti i suoi alunni (i nodi P5, P14, P15, P16, P6, P7, P8, P19, P18, P9, P17, P10).

<div style="text-align: center"><img src="/media/images/schoolcluster.svg" /></div>

Si noti che il membro della segreteria <font color="#99cc00">P1</font> è l'unico che nella rete in figura ha un contatto con l'insegnante <font color="#008cff">P3</font>.

A questo punto come ci torna utile il concetto di grado dei nodi?

Il prossimo paragrafo ci aiuterà a condurre un'analisi un po' più complessa delle precedenti, che si servirà dei _cluster_ appena identificati e del concetto di cammino.

Di seguito vedremo come il grado di un nodo e i cammini tra i vari nodi della rete, giocano un ruolo fondamenale nella dinamica di reti come questa.

<br>
### L'influenza a scuola
#### _Ovvero di come il grado di un singolo nodo ha effetti sull'intero sistema_
<hr>
<br>
Immaginiamo che il nodo <font color="#ff0066">P13 si ammali di influenza</font>. Quante persone potrà contagiare questo nodo rispetto alla sua posizione nella rete? Il grado del nodo P13 ci fornisce la risposta a questa domanda. Poiché P13 possiede grado 1, esso potrà contagiare al più una persona. In altre parole: se P13 ha l'influenza, è probabile che la contragga anche P12, lavorando a stretto contatto con il nodo ammalato.

<div style="text-align: center"><img src="/media/images/spread1.svg" /></div>

Quante persone potrà invece contagiare invce il nodo <font color="#ff0066">P4</font>, se fosse lui ad ammalarsi di influenza?

Contiamo gli archi di P4: <P4, P11>, <P4, P1>, <P4, P2>.

Il grado di P4 è pari a 3 e dunque saranno 3 le persone che P4 potrebbe potenzialmente contagiare.

<div style="text-align: center"><img src="/media/images/spread2.svg" /></div>

Infine, immaginiamo che si ammali di influenza il nodo <font color="#ff0066">P3</font>, l'insegnante della scuola.

Il grado di P3 ammonta a 13.

<div style="text-align: center"><img src="/media/images/highdegree.svg" /></div>

Il dirigente scolastico che ha contatti sempre e solo con il suo vice, avrà una "forza di contagio" pari a 1. Viceversa, l'insegnante che entra in classe accerchiato da una dozzina di alunni, avrà una "forza di contagio" pari a 12.

In questo senso quindi, il grado di un nodo è fondamentale per capire la diffusione di un fenomeno (che sia l'influenza o qualsiasi altra cosa). In particolare, possiamo affermare che più un nodo possiede un grado elevato, più quel nodo avrà un ruolo centrale (di _hub_) all'interno della rete studiata.


In conclusione, questi esempi ci dovrebbero aiutare a comprendere che vi sono casi in cui il grado dei nodi di una rete è sinonimo di prestigio, di notorietà (si pensi alla rete degli amici su Facebook). Altre volte il grado di un nodo è sinonimo di efficienza, di raggiungibilità (si pensi alla rete della metropolitana di Londra). In altri casi ancora, il grado di un nodo è sinonimo di pericolo, di problema (si pensi in quest'ultimo caso alla rete scolastica dove alcuni nodi si ammalano di influenza e si rifletta sul come gli effetti di un'influenza cambiano sul sistema a seconda del/dei grado/i del/dei nodo/i ammalato/i).

<br>
### Il numero di relazioni è importante, ma non è tutto
#### _Il grado di un nodo è fondamentale, ma non è l'unica cosa a cui prestare attenzione_
<hr>
<br>
Nel paragrafo precedente abbiamo stabilito che il grado di un nodo rappresenta la misura con cui un eventuale nodo ammalato può contagiare altri nodi della rete.

In generale, <font color="#008cff">il grado di un nodo quantifica le relazioni che quel nodo possiede all'interno della rete</font>.

Saremmo tentati di concludere, a questo punto, che una volta studiato il grado dei nodi di una rete, il nostro lavoro si possa considerare concluso.

Quindi individuato un utente su Facebook con 5000 amici, dovremmo ritenere questo utente importante, e ininfluenti tutti coloro con un numero di amici minore di 5000.

Oppure individuata la fermata metropolitana con il maggior numero di destinazioni, dovremmo rinunciare a salire in qualsiasi altra fermata.

Infine, potremmo pensare che eliminare il nodo con grado maggiore in una rete di persone, sia sufficiente a debellare la diffusione di un'epidemia contagiosa.

Così non è, in nessuno dei tre casi sopracitati e per diverse questioni. Alcune sono ovvie e sono certo che il lettore ne è perfettamente a conoscenza. Altre sono meno ovvie. Tra queste meno ovvie ve ne sono alcune semplici e altre più complesse.

Cominciamo da quelle più semplici (alcune di quelle complicate verranno affrontate in articoli successivi a questo).

<br>
### Dagli effetti locali agli effetti globali
#### _Ovvero di come anche nodi con grado basso posso scatenare effetti su larga scala_
<hr>
<br>

Un dottore specializzato in "grado dei nodi di una rete" viene chiamato a scuola per una diagnosi su un caso di influenza. L'appuntamento è fissato per le ore $$t_{0}$$.

- _Buongiorno, sono il medico, sono qui per l'influenza;_
- _Benvenuto dottore, guardi, la situazione è questa..._ (si veda la figura sotto)
- _Benissimo. Noto che il vostro dirigente scolastico è influenzato..._
- _Eh sì dottore, questa mattina è arrivato a scuola con un grosso raffreddore..._
- _Con chi lavora il vostro dirigente? Ha dei collaboratori?_
- _Guardi, solamente uno, il vicepreside, che lavora nella scrivania a fianco alla sua._
- _Ho capito. Ecco la mia diagnosi: la situazione è sotto controllo e non è grave. Non vi preoccupate perché nel caso peggiore anche il vostro vicepreside si farà qualche giorno a casa. Sicuramente i vostri alunni e il resto del personale scolastico sono al sicuro._

<div style="text-align: center"><img src="/media/images/timein.svg" /></div>

Il dialogo tra il dottore e un misterioso componente del personale scolastico è volutamente estremizzato, ma vorrebbe far cogliere al lettore la "prospettiva locale" con cui il dottore immaginario ha formulato la sua diagnosi.

Misurare il grado di un nodo è un'<font color="#008cff">operazione locale</font>, poiché la visibilità è limitata esclusivamente al nodo in esame e ai suoi nodi immediatamente vicini (nodi adiacenti).

Questo, in alcuni casi, rappresenta un grosso limite di questa proprietà.

Consideriamo ancora una volta la rete scolastica su cui tanto stiamo ragionando.

Immaginando di richiamare il dottore immaginario al tempo $$t_{8}$$ anziché al tempo $$t_{0}$$, il numero di nodi ammalati sarebbe molto più grande del caso precedente. Questo avviene perché P13 potrebbe aver contagiato P12 (e solo P12), ma P12 a sua volta potrebbe aver contagiato P11 (e solo P11). P11 a sua volta potrebbe aver contagiato P4, che per la prima volta è in grado di contagiare due nodi contemporaneamente (P2 e P1).

Al tempo $$t_{5}$$ la situazione non solo sarebbe molto più grave di quella evidenziata al tempo $$t_{0}$$, ma sarebbbe anche pronta a scatenare un contagio di massa, rendendo l'intera rete scolastica potenzialmente ammalata di influenza.

A tal proposito, prestiamo attenzione all'arco tratteggiato che collega P1 a P3. Quell'arco giocherà un ruolo cruciale nella diffusione dell'influenza. Sapreste dire il perché?

<div style="text-align: center"><img src="/media/images/timeout.svg" /></div>

Se non vi siete persi durante questo scritto, la risposta all'ultima domanda dovrebbe essere abbastanza semplice.

Con questo ultimo esempio si è voluto mostrare come l'esistenza di un solo arco tra due nodi confinati ad un'estremità della rete (l'arco che collega P13 a P12), può avere effetti importanti sull'intero sistema, in virtù dei cammini che esistono tra i nodi di una rete.

Per questo dobbiamo ricordarci che ogni azione che svolgiamo nel nostro piccolo, genera, in misura più o meno singificativa e dopo un certo periodo di tempo, un effetto sull'intero sistema.

In conclusione
-----------------------
- Il grado di un nodo corrisponde al numero di archi di quel nodo.
- Il numero di archi di un nodo rappresenta il numero di relazioni che quel nodo possiede con altri nodi.
- Le relazioni misurate dal grado di un nodo sono "relazioni di prossimità": coinvolgono il nodo esaminato e i nodi immediatamente vicini.
- Il "grado di un nodo" è un proprietà locale delle reti.
- Più il grado di un nodo è alto, più quel nodo è importante (dove "importante" può voler dire tante cose: influente, forte, strategico, efficiente, resiliente, pericoloso, etc.)
- Anche i nodi con poche relazioni possono generare degli effetti sul sistema;
- Quando si vogliono studiare gli effetti sulla rete dei nodi con poche relazioni, occorre concentrarsi sui cammini che collegano nodi distanti tra loro più che sul grado di ogni nodo.
- A volte, è bene adottare una "prospettiva globale" a supporto e completamento della "prospettiva locale."
- La velocità con cui i nodi con poche relazioni possono generare degli effetti sul sistema è direttamente proporzionale alla distanza che questi nodi hanno con i nodi _hub_ della rete.
- Le connessioni sono importanti: sia in riferimento alla quantità di relazioni che ciascun nodo possiede, sia in riferimento ai cammini che da quel nodo, relazione dopo relazione, è possibile percorrere.

[mamatteonetsci1]: https://mamatteo.github.io/informatica/che-cosa-e-un-grafo-e-come-si-rappresenta
[scalefreelink]: https://it.wikipedia.org/wiki/Rete_a_invarianza_di_scala
