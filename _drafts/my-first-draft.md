---
layout: mypost
title: Comandi sempre utili
---
Alcune comandi utili in Jekyll markdown per rendere meravigliosi gli articoli di questo sito.

Scrivere in LaTeX
===============

1. 0 $$\in \mathbb{N}$$
2. se $$a \in \mathbb{N}$$ allora $$S(a) \in \mathbb{N} $$
3. se $$a, b \in \mathbb{N}$$ tali che $$a\neq b$$ allora $$S(a)\neq S(b)$$
4. non esiste alcun $$a \in \mathbb{N}$$ tale che $$0 = S(a)$$
5. se $$A\subseteq \mathbb{N}$$ tale che $$0\in A$$ e $$(a\in A \Rightarrow S(a) \in A)$$ allora $$A =
   \mathbb{N}$
   $ (*assioma di induzione*)

$$ f(x) = \int_x^{x+1} \ln(t) {\rm d}t $$

per $$x>0$$.



Scrivere codice
===============

{% highlight ruby %}
def print_hi(name)
puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}


Highlights del testo
==================

`leggere`

`funzione1`

<span style="background-color: #fee287">Marked text</span>
<span style="background-color: #7df0c1">Marked text</span>
<span style="background-color: #f26471">Marked text</span>

<p class="grayparagraph">
<font color="#0049B0">Prima di cominciare</font><br>
Se già conosci le fondamenta teoriche della teoria dei grafi, prosegui pure la lettura. Probabilmente ti imbatterai in altri concetti a te già noti, oppure ne impareri di nuovi.
Se invece conosci poco o nulla della teoria dei grafi, può esserti utile cominciare dall'articolo "Cos'è un grafo e come rappresentarlo", che introduce i concetti propedeutici alla comprensione di questo articolo.</p>



Link esterni
==============

[Testo dove inserire il link][Ancora]

[Ancora]: https://www.google.it
