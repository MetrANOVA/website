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
TODO: This ends mid-July, 2024.
{%- endcomment -%}
<p align="center">We're looking to better understand the state of
network measurement and monitoring within the research and education
networking community.  Please give us a moment of your time and <a
href="https://forms.gle/zeYAu8Hp1bZFU8hF7">take our user
survey</a>.</p>


{%- comment -%}
-------------------------------------------------------------------------------
				 LOGO
-------------------------------------------------------------------------------
{%- endcomment -%}
<p align="center"><img src="images/logos/metranova/metranova.svg" alt="MetrANOVA Logo" /></p>


{%- comment -%}
-------------------------------------------------------------------------------
			     DESCRIPTION
-------------------------------------------------------------------------------
{%- endcomment -%}

MetrANOVA is a neutral, trusted, and open consortium for **A**dvancing
**N**etwork **O**bservation, **V**isualization, and **A**nalysis. Its
primary goal is to advance the state of Research and Education
Networking(REN) measurement and analysis by developing and socializing
technical capabilities. Success comes from member organizations and
the broader community using these capabilities publicly and privately
within their infrastructure. To avoid competing against stakeholders'
interests, the consortium will focus on developing tools, tactics, and
techniques but will not offer measurement services. However, Member
Organizations and the broader community are encouraged to use these
tools, tactics, and techniques to create appropriate local,
distributed, and federated solutions.

This consortium will focus on three types of deliverables:

 - Develop and share open architectures, technical components, design
   patterns, best practices, and policy recommendations to create
   effective network measurement systems.

 - Educate the research and education community to enable effective
   use of network measurements for operations, engineering, planning,
   and outreach.

 - Provide growth opportunities for students and staff.

The Consortium will consist of both Member Organizations and
Affiliates (individuals or organizations) that are actively
participating in the project.  The set of individual participants who
are contributing to the project are considered Contributors. A tiered
participation model will allow for different levels of resource
allocation and commitment to the project, enabling a broad base of
Contributors. The final decision-making responsibility for the
project’s direction resides with an Executive Committee. The Executive
Committee consists of one individual from each of the participating
Member Organizations.
