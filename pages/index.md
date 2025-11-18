---
title: ""
keywords: metranova homepage
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
{%- comment -%}

#
# THIS SECTION IS DISABLED.
#

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
{%- endcomment -%}


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
<p align="center"><img src="images/metranova_team.jpg" alt="MetrANOVA Team" /></p>
<div align="center"><i>
Members of the MetrANOVA consortium met in Berkeley in October 2024 for a
brainstorming and collaboration session.
</i></div>
<hr/>

{%- comment -%}
-------------------------------------------------------------------------------
			     DESCRIPTION
-------------------------------------------------------------------------------
{%- endcomment -%}

MetrANOVA is a neutral, trusted, and open consortium for Advancing Network
Observation, Visualization, and Analysis. Our primary goal is to advance the
state of research and education (R&E) networking measurement and analysis by
developing and socializing technical capabilities. We offer a toolkit and
patterns, not a hosted service.

This consortium will focus on three types of deliverables:

 - **MetrANOVA network tools**, used in production by several consortium members:
   - A scalable software stack for all sizes of network-based systems, based on
       existing open source tools.
   - Full-featured measurement stack for network metrics, including flow data
     and host and application stats and logs.
   - Proven deployment patterns, including techniques for controlled data sharing
     and transparent testing results.

 - **Join the MetrANOVA partnership** [LINK TO JOIN PAGE]: Help craft the future of
   R&E network measurement, reduce individual costs to stand up essential tools,
   and improve collective situational awareness!

