---
layout: page
permalink: /projects/
title: PROJECTS
description: An overview of the collaborative research projects I have been actively involved in.
nav: true
nav_order: 3
toc:
  sidebar: right
---

<h2 id="ongoing_projects">Ongoing projects</h2>

{% for project in site.data.projects %}
{% if project.ongoing %}

{% if project.url %}
{% assign url = project.url %}
{% else %}
{% capture url %} #{{project.id}} {% endcapture %}
{% endif %}

<div id="{{project.id}}">
  <p>
      <a href="{{url}}" target="_blank" style="text-decoration: none;">
          {% if project.logo != 0 %}
          <img src="{{project.logo}}" style="vertical-align:middle; padding:2px; height: 45px;" border="0">
          {% else %}
          <span style="color:#01BBF3; font-weight: bold;">{{project.title}}</span>
          {% endif %}
      </a>
      <span style="font-weight: bold;">
          &nbsp;&nbsp; {{project.type}}
          &nbsp;|&nbsp; {{project.start_year}} - {{project.end_year}}
          &nbsp;|&nbsp; {{project.nb_partners}} partners
          &nbsp;|&nbsp; {{project.budget}}
      </span>
  </p>
  <p>
      {% if project.description %}
      {{project.description | escape_once}} &nbsp;&nbsp;
      {% else %}
      <i>Available in French only:</i><br/>
      {{project.description_fr | escape_once}} &nbsp;&nbsp;
      {% endif %}

      {% if project.url.size > 4 %}
      <a href="{{project.url}}" target="_blank">Read More &raquo;</a>
      {% endif %}
  </p>
</div>
{% endif %}
{% endfor %}

<h2 id="past_projects">Past projects</h2>

{% for project in site.data.projects %}

{% if project.ongoing == false %}

{% if project.url %}
{% assign url = project.url %}
{% else %}
{% capture url %} #{{project.id}} {% endcapture %}
{% endif %}

<div id="{{project.id}}">
  <p>
      <a href="{{url}}" target="_blank" style="text-decoration: none;">
          {% if project.logo != 0 %}
          <img src="{{project.logo}}" style="vertical-align:middle; padding:2px; height: 45px;" border="0">
          {% else %}
          <span style="color:#01BBF3; font-weight: bold;">{{project.title}}</span>
          {% endif %}
      </a>
      <span style="font-weight: bold;">
          &nbsp;&nbsp; {{project.type}}
          &nbsp;|&nbsp; {{project.start_year}} - {{project.end_year}}
          &nbsp;|&nbsp; {{project.nb_partners}} partners
          &nbsp;|&nbsp; {{project.budget}}
      </span>
  </p>
  <p>
      {% if project.description %}
      {{project.description | escape_once}} &nbsp;&nbsp;
      {% else %}
      <i>Available in French only:</i><br/>
      {{project.description_fr | escape_once}} &nbsp;&nbsp;
      {% endif %}

      {% if project.url.size > 4 %}
      <a href="{{project.url}}" target="_blank">Read More &raquo;</a>
      {% endif %}
  </p>
</div>
{% endif %}
{% endfor %}
