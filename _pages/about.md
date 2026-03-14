---
permalink: /
title: ""
excerpt: ""
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

{% if site.google_scholar_stats_use_cdn %}
{% assign gsDataBaseUrl = "https://cdn.jsdelivr.net/gh/" | append: site.repository | append: "@" %}
{% else %}
{% assign gsDataBaseUrl = "https://raw.githubusercontent.com/" | append: site.repository | append: "/" %}
{% endif %}
{% assign url = gsDataBaseUrl | append: "google-scholar-stats/gs_data_shieldsio.json" %}

<span class='anchor' id='about-me'></span>

I'm a master student at Huazhong University of Science and Technology, where I am a member of the <a href="https://hustvl.github.io/">HUST Vision Lab</a> under the supervision of <a href="https://xwcv.github.io/">Prof. Xinggang Wang</a>.
My research interests include autonomous driving, MLLMs, and generative models.

Currently, I am a research intern at Horizon Robotics, working in the team led by [Shaoyu Chen](https://scholar.google.com/citations?user=PIeNN2gAAAAJ) and [Qian Zhang](https://scholar.google.com/citations?user=pCY-bikAAAAJ).
My current research focuses on Vision-Language-Action models (VLA) for autonomous driving.

# 🔥 News
{% assign news = site.data.news | sort: "date" | reverse %}
<ul>
{% for n in news %}
  {% if forloop.index <= 5 %}
  <li><em>{{ n.display }}</em>: &nbsp;{{ n.content | markdownify | remove: '<p>' | remove: '</p>' }}</li>
  {% else %}
  <li class='news-extra' style='display:none'><em>{{ n.display }}</em>: &nbsp;{{ n.content | markdownify | remove: '<p>' | remove: '</p>' }}</li>
  {% endif %}
{% endfor %}
</ul>
{% if news.size > 5 %}
<button id="news-more-btn" onclick="var els=document.querySelectorAll('.news-extra'),expanded=els[0].style.display!=='none';els.forEach(el=>el.style.display=expanded?'none':'list-item');this.textContent=expanded?'More \u00bb':'Less \u00ab';" style="background:none;border:none;color:#52adc8;cursor:pointer;padding:0;font-size:1em;">More &raquo;</button>
{% endif %}

# 📝 Publications

{% assign pubs = site.data.publications | sort: "date" | reverse %}

<details open><summary style="cursor: pointer; display: list-item; font-size: 1.25em; font-weight: bold; margin: 0.6em 0; color: #333;">✨ Highlights</summary>
{% for p in pubs %}
{% if p.highlight %}
<div class='paper-box'><div class='paper-box-image'><div>{% if p.badge %}<div class="badge">{{ p.badge }}</div>{% endif %}{% if p.image %}<img src='{{ p.image }}' alt="paper" width="100%">{% endif %}</div></div><div class='paper-box-text' markdown="1">
  [{{ p.title }}]({{ p.paper_url }})

  {{ p.authors | join: ", " }}

  [**PDF**]({{ p.pdf_url }}){% if p.project_url %} \| [**Project**]({{ p.project_url }}){% endif %}{% if p.stars_badge and p.code_url %} \| [![]({{ p.stars_badge }})]({{ p.code_url }}){% endif %}
</div></div>
{% endif %}
{% endfor %}

</details>

<details close>
  <summary style="cursor: pointer; display: list-item; font-size: 1.25em; font-weight: bold; margin: 0.6em 0; color: #333;">
    📄 All Publications
  </summary>
{% for p in pubs %}
<div class='paper-box-light'>
<div class='paper-box-text' markdown="1">
[{{ p.title }}]({{ p.paper_url }})

{{ p.authors | join: ", " }}

{% if p.venue and p.venue != "" %}**{{ p.venue }}** \| {% endif %}[**PDF**]({{ p.pdf_url }}){% if p.project_url %} \| [**Project**]({{ p.project_url }}){% endif %}{% if p.stars_badge and p.code_url %} \| [![]({{ p.stars_badge }})]({{ p.code_url }}){% endif %}
</div>
</div>
{% endfor %}
</details>

# 📖 Educations

- *2024.09 - Now*, Master, School of EIC, Huazhong University of Science and Technology, Wuhan, China, supervised by [Prof. Xinggang Wang](https://xwcv.github.io/).
- *2020.09 - 2024.06*, Bachelor, School of EIC, Huazhong University of Science and Technology, Wuhan, China.

# 💻 Internships
- *2025.01 - Now*, [Horizon Robotics](https://www.horizon.auto), Beijing, China.
