---
title: ""
keywords: sample homepage
# tags: [ home ]
sidebar: home_sidebar
permalink: index.html
# summary: MetrANOVA is ... TODO
toc: false
comments: false
---
{%- comment -%}
-------------------------------------------------------------------------------
			       RELEASE

This will show a release notice for 45 days after a new release note
is posted.
-------------------------------------------------------------------------------
{%- endcomment -%}
{% assign latest_release = site.releasenotes | last %}
{% capture epoch_now %}{{ "now" | date: '%s' }}{% endcapture %}
{% capture epoch_since %}{{ latest_release.date | date: '%s' }}{% endcapture %}
{% assign days_since = epoch_now | minus: epoch_since | divided_by: 86400 %}
{% if days_since < 14 %}
  {% assign release_message = "New Release" %}
{% elsif days_since < 45 %}
  {% assign release_message = "Recent Release" %}
{% else %}
  {% assign release_message = "Current Release" %}
{% endif %}
{% if days_since < 45 %}
  {% assign releasenote_url = latest_release.url | remove: "/" %}
  <p align="center">{{ release_message }}: <b><a href="{{ releasenote_url }}">{{ latest_release.version }}</a></b></p>
{% endif %}


{%- comment -%}
-------------------------------------------------------------------------------
				 NEWS

This will show a news notice for anything less than 30 days old.
-------------------------------------------------------------------------------
{%- endcomment -%}
{% capture epoch_now %}{{ "now" | date: '%s' }}{% endcapture %}
{% capture epoch_post %}{{ site.posts[0].date | date: '%s' }}{% endcapture %}
{% assign days_since = epoch_now | minus: epoch_post | divided_by: 86400 %}
{% if days_since < 2 %}
  {% assign news_message = "This Just In" %}
{% elsif days_since < 14 %}
  {% assign news_message = "Latest News" %}
{% else %}
  {% assign news_message = "News" %}
{% endif %}
{% if days_since <= 30 %}
  {% assign post_url = site.posts[0].url | remove: "/" %}
  <p align="center">{{ news_message }}: <b><a href="{{ post_url }}">{{ site.posts[0].title }}</a></b></p>
{% endif %}


{%- comment -%}
-------------------------------------------------------------------------------
				 LOGO
-------------------------------------------------------------------------------
{%- endcomment -%}
<p align="center"><img src="images/logos/perfsonar/perfsonar-logo-black-full.svg" /></p>


{% include important.html content="This is a development test for the MetrANOVA web site and should in no way be considered finished." %}


{%- comment -%}
-------------------------------------------------------------------------------
			     DESCRIPTION
-------------------------------------------------------------------------------
{%- endcomment -%}

<p>MetrANOVA is... TODO</p>




