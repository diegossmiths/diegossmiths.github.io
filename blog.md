---
layout: default
title: Blog
author: Diego Schild Smiths
description: Índice do blog Uma viagem pelo meu jardim
keywords: blog, pessoal, diego, schild, smiths
permalink: blog/
---

# Blog

Aqui, neste pequeno lugar, é onde escrevo e compartilho minhas ideias. Caso desejes conversar, sinta-se à vontade para enviar um e-mail (o endereço está no ícone de envelope no rodapé da página). Sinta-se à vontade e pise na grama. =]


---

{% assign posts = site.posts | sort: "date" | reverse %}

{% for post in posts %}
  {% unless post.hidden %}
    {% assign date = post.date %}

### [{{ post.title }}]({{ post.url }}) **{{ date | date: '%F' }}**

#### {{ post.description }}

[Leia mais]({{ post.url }}){: class="leia-mais"}

  {% endunless %}
{% endfor %}

