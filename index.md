---
layout: principal
---

<main class="home" id="post" role="main" itemprop="mainContentOfPage" itemscope="itemscope" itemtype="http://schema.org/Blog">
    <div id="grid" class="row flex-grid">
    {% assign sorted_pages = site.articles | sort: 'position' %}
    {% for p in sorted_pages %}
        {% include pre-article.html page=p %}
    {% endfor %}
    </div>
</main>
