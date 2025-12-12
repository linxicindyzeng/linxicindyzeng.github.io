---
layout: page
title: Projects
permalink: /projects/
description:
nav: true
nav_order: 1
display_categories: [Work in Progress, Working Paper, Course Notes]
horizontal: false
---

<!-- pages/projects.md -->
<div class="publications">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="year" style="text-align:left; color: var(--global-text-color); border-top: 1px solid var(--global-text-color); padding-top: 1rem; margin-top: 2rem; margin-bottom: 0.75rem;">
    {{ category }}
  </h2>
  {%- assign categorized_projects = site.projects | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "date" | reverse %}
  
  {%- for project in sorted_projects -%}
  <div style="margin-bottom: 1.5rem; padding-left: 0;">
    <p style="margin-bottom: 0.25rem;">
      {%- if project.redirect -%}
      <a href="{{ project.redirect }}" style="color: var(--global-theme-color); text-decoration: none;">{{ project.title }}</a>
      {%- else -%}
      <a href="{{ project.url | relative_url }}" style="color: var(--global-theme-color); text-decoration: none;">{{ project.title }}</a>
      {%- endif -%}
    </p>
    <p style="margin-bottom: 0.25rem; color: var(--global-text-color);">
      {{ project.description }}
    </p>
    <p style="margin-bottom: 0.25rem; color: var(--global-text-color-light); font-size: 0.9rem;">
      {%- if project.date -%}
      Last updated: {{ project.date | date: "%B %Y" }}
      {%- endif -%}
    </p>
    {%- assign has_links = false -%}
    {%- if project.pdf or project.github or project.website -%}
      {%- assign has_links = true -%}
    {%- endif -%}
    {%- if has_links -%}
    <p style="margin-top: 0.25rem; margin-bottom: 0;">
      {%- if project.pdf -%}
      <a href="{{ project.pdf | relative_url }}" style="color: var(--global-theme-color); text-decoration: none;">PDF</a>{%- if project.github or project.website %} | {%- endif -%}
      {%- endif -%}
      {%- if project.github -%}
      <a href="{{ project.github }}" style="color: var(--global-theme-color); text-decoration: none;">Code</a>{%- if project.website %} | {%- endif -%}
      {%- endif -%}
      {%- if project.website -%}
      <a href="{{ project.website }}" style="color: var(--global-theme-color); text-decoration: none;">Website</a>
      {%- endif -%}
    </p>
    {%- endif -%}
  </div>
  {%- endfor -%}
  {% endfor %}

{%- else -%}
<!-- Display projects without categories -->
  {%- assign sorted_projects = site.projects | sort: "date" | reverse -%}
  
  {%- for project in sorted_projects -%}
  <div style="margin-bottom: 1.5rem; padding-left: 0;">
    <p style="margin-bottom: 0.25rem;">
      {%- if project.redirect -%}
      <a href="{{ project.redirect }}" style="color: var(--global-theme-color); text-decoration: none;">{{ project.title }}</a>
      {%- else -%}
      <a href="{{ project.url | relative_url }}" style="color: var(--global-theme-color); text-decoration: none;">{{ project.title }}</a>
      {%- endif -%}
    </p>
    <p style="margin-bottom: 0.25rem; color: var(--global-text-color);">
      {{ project.description }}
    </p>
    <p style="margin-bottom: 0.25rem; color: var(--global-text-color-light); font-size: 0.9rem;">
      {%- if project.date -%}
      Last updated: {{ project.date | date: "%B %Y" }}
      {%- endif -%}
    </p>
    {%- assign has_links = false -%}
    {%- if project.pdf or project.github or project.website -%}
      {%- assign has_links = true -%}
    {%- endif -%}
    {%- if has_links -%}
    <p style="margin-top: 0.25rem; margin-bottom: 0;">
      {%- if project.pdf -%}
      <a href="{{ project.pdf | relative_url }}" style="color: var(--global-theme-color); text-decoration: none;">PDF</a>{%- if project.github or project.website %} | {%- endif -%}
      {%- endif -%}
      {%- if project.github -%}
      <a href="{{ project.github }}" style="color: var(--global-theme-color); text-decoration: none;">Code</a>{%- if project.website %} | {%- endif -%}
      {%- endif -%}
      {%- if project.website -%}
      <a href="{{ project.website }}" style="color: var(--global-theme-color); text-decoration: none;">Website</a>
      {%- endif -%}
    </p>
    {%- endif -%}
  </div>
  {%- endfor -%}
{%- endif -%}
</div>
