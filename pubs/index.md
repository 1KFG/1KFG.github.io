---
title: Research
redirect_from: /pubs
---

Boiler

### Search & Filter

{:.center}
<input class="paper_search">

{% include paper-tags.html tags=alltags %}

<p class="center">
  {% for item in site.data.paper-link-types %}
  {% assign type = item[0] %}
  {% include paper-link-button.html type=type %}
  {% endfor %}
</p>

<!-- get paper data from json -->
{% assign papers = site.data.research-output | sort: "date" | reverse %}

<!-- group data by year -->
{% assign byyear = papers | group_by_exp: "post", "post.date | date: '%Y'" | sort: "name" | reverse %}

<!-- loop through year groups -->
{% for yeargroup in byyear %}

{:.paper_search_heading}
## Results

{:.paper_heading}
## {{ yeargroup.name }}

<!-- loop through all papers in this year group -->
{% for paper in yeargroup.items %}

{% include paper-card.html paper=paper %}

{% endfor %}

{% endfor %}

## More

{:.center}
[<i class="fas fa-book-open icon_with_text"></i>More on PubMed](https://pubmed.ncbi.nlm.nih.gov/?term=stajich+jason){:.big_link}
[<i class="fab fa-google icon_with_text"></i>More on Google Scholar](http://scholar.google.com/citations?hl=en&user=t_YIP5UAAAAJ){:.big_link}

The citations on this page were generated automatically from just identifiers using the [Manubot cite utility](https://github.com/manubot/manubot#cite) developed right here in the Greene Lab!

<script src="https://cdnjs.cloudflare.com/ajax/libs/mark.js/8.11.1/mark.min.js"></script>
