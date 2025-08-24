---
layout: default
title: "Jref Posts"
---

<style>
body {
  background-color: #000000;
  color: #ffffff;
}

.post-card {
  border: 1px solid #333333;
  border-radius: 8px;
  padding: 20px;
  margin-bottom: 20px;
  background-color: rgba(60, 60, 60, 0.7); /* 불투명 회색 */
  box-shadow: 0 2px 5px rgba(0,0,0,0.5);
  transition: transform 0.2s;
}

.post-card:hover {
  transform: translateY(-5px);
  background-color: rgba(80, 80, 80, 0.8); /* 호버 시 약간 더 밝게 */
}

.post-title {
  font-size: 24px;
  color: #ffffff;
  margin: 0;
}

.post-content {
  color: #dddddd;
  line-height: 1.6;
}

.post-meta {
  font-size: 14px;
  color: #aaaaaa;
  margin-top: 15px;
}
</style>

# Jref News

{% for post in site.posts %}
<div class="post-card">
  <div class="post-header">
    <a href="{{ post.url | relative_url }}">
      <h2 class="post-title">{{ post.title }}</h2>
    </a>
  </div>
  <div class="post-content">
    <p>{{ post.content | strip_html | truncatewords: 50 }}</p>
  </div>
  <div class="post-meta">
    <span>{{ post.date | date: "%Y-%m-%d" }}</span>
  </div>
</div>
{% endfor %}