---
layout: index
---

{% for headline in site.data.headlines %}
## <i class="glyphicon glyphicon-hand-right" aria-hidden="true"></i> {{ headline.title }}

{{ headline.content|markdownify }}
{% endfor %}

## <i class="glyphicon glyphicon-hand-right" aria-hidden="true"></i> Aber...

{% for post in site.posts %}
### • [{{ post.title }}]({{ post.url }})
{% endfor %}

## <i class="glyphicon glyphicon-hand-right" aria-hidden="true"></i> Weiter gehen

Hier finden Sie verschiedene Resourcen zum Thema, um die Fragen und
Folgen besser zu verstehen.

### Durch Lesen von Artikel

{% for article in site.data.articles %}
    {% include article_item.html article=article %}
{% endfor %}

### Durch Vorträge zuhören

<ul class="media-list">
{% for video in site.data.videos %}
    {% include video_item.html video=video %}
{% endfor %}
</ul>

### Durch Lesen von Bücher

{% for book in site.data.books %}
#### • {{ book.title }} - _{{ book.authors|join:', ' }}_

{% if book.abstract %}{{ book.abstract|markdownify }}{% endif %}
{% endfor %}


## <i class="glyphicon glyphicon-hand-right" aria-hidden="true"></i> Sich informieren

<ul class="centered-list">
{% for source in site.data.sources %}
    <li>
        <a href="{{ source.url }}">
            <img src="/images/{{ source.image }}" class="img-responsive">
        </a>
    </li>
{% endfor %}
</ul>

## Andere Quellen

{% for source in site.data.other-sources %}
#### • {% if source.url %}[{{ source.title }}]({{ source.url }}){% else %}{{ source.title }}{% endif %} - _{{ source.authors|join:', ' }}_{% if source.language %} (en {{ source.language }}){% endif %}
{% endfor %}

<hr>

<!--p class="text-center">
    Email : <a href="mailto:contact@jenairienacacher.fr">contact@jenairienacacher.fr</a>  — Twitter : <a href="https://twitter.com/rienacacher_fr">@rienacacher_fr</a>
</p-->
