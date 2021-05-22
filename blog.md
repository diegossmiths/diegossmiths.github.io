---
layout: default
title: Blog
author: Diego Schild Smiths
description: Índice do blog Uma viagem pelo meu jardim
keywords: blog, pessoal, diego, schild, smiths
permalink: blog/
---

# Blog

Aqui, neste pequeno lugar, é onde escrevo e compartilho minhas ideias. É aqui onde eu abro meu pequeno jardim e exponho à todas as pessoas. É para uma pequena viagem nesse jardim que eu os convido.


---

## Postagens:

{% assign posts = site.posts | sort: "date" | reverse %}

{% for post in posts %}
  {% unless post.hidden %}
    {% assign date = post.date %}

### [{{ post.title }}]({{ post.url }}) **{{ date | date: '%F' }}**

#### {{ post.description }}

[Leia mais]({{ post.url }}){: class="leia-mais"}

  {% endunless %}
{% endfor %}

