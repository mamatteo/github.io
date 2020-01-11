---
layout: mypost
title:  "The most important skills of data scientist"
date:   2020-01-09
categories: datascience
permalink: /:categories/:title
---

Nei giorni che hanno preceduto l'inizio dell'anno 2020, ho potuto `leggere` diverse cose che avevo lasciato da parte e ho potuto guardarmi un po' di video interessanti. Tra questi segnalo l'ottimo contributo offerto da [Jose Miguel Cansado][JoseCansado], che in occasione del `TEDx` di Madrid ha tenuto un intervento intitolato ["The most important skills of data scientists"][TedTalk].

Alcune note matematiche:


1. 0 $$\in \mathbb{N}$$
2. se $$a \in \mathbb{N}$$ allora $$S(a) \in \mathbb{N} $$
3. se $$a, b \in \mathbb{N}$$ tali che $$a\neq b$$ allora $$S(a)\neq S(b)$$
4. non esiste alcun $$a \in \mathbb{N}$$ tale che $$0 = S(a)$$
5. se $$A\subseteq \mathbb{N}$$ tale che $$0\in A$$ e $$(a\in A \Rightarrow S(a) \in A)$$ allora $$A =
   \mathbb{N}$$ (*assioma di induzione*)

Tra i passaggi più signficativi riporto alcune frasi finali:

> the most important skill of a data scientist is asking the right question to data. (...) Big data needs big brains. Big data needs the curious brain of an artist to make the difference.


<iframe width="730" height="415" src="https://www.youtube.com/embed/qrhRfPY4F4w" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Davvero interessante:

$$ f(x) = \int_x^{x+1} \ln(t) {\rm d}t $$

per $$x>0$$.

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

[TedTalk]: https://www.youtube.com/watch?v=qrhRfPY4F4w&t=4s
[JoseCansado]: https://www.linkedin.com/in/josemiguelcansado/?originalSubdomain=es
