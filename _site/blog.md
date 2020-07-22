# Blog

> Aqui, neste pequeno lugar, é onde escrevo e compartilho minhas ideias. É aqui onde eu abro meu pequeno jardim e exponho a todas as pessoas. É para uma pequena viagem nesse jardim que eu os convido.

<!-- {% assign posts = site.posts | sort: "date" | sort: "updated" | reverse %} -->

{% for post in posts %}
  {% unless post.hidden %}
    {% assign date = post.date %}
    {% if post.updated %}
      {% assign date = post.updated %}
    {% endif %}

### [{{ post.title }}]({{ post.url }}) **{{ date | date: '%F' }}**

{% if post.description %}
#### {{ post.description }}
{% endif %}

{{ post.content | strip_html | truncatewords: 24 }}


[Read more]({{ post.url }}){: class="read-more"}

  {% endunless %}
{% endfor %}

