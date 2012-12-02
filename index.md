---
layout: page
---
{% include JB/setup %}

<div class="posts">
{% for post in site.posts %}
  <h2 class="post_title">
    <span><a class="post-title" href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></span>
  </h2>

  <span class="post_meta">
    {% if post.author %}
      {{ post.author | capitalize }}
      &middot;
    {% endif %}
    {{ post.date | date_to_long_string }}
  </span>

  <div class="post_content">
    {% if post.image %}
      <a class="header_image" href="{{ BASE_PATH }}{{ post.url }}">
        <img alt="{{ post.title }}" src="{{ post.image }}" />
      </a>
    {% endif %}
    {% if post.description and post.description != "" %}
      {{ post.description | markdownify }} 
      <a class="ots_action read_more" href="{{ BASE_PATH }}{{ post.url }}">Read&nbsp;more&nbsp;&#8594;</a>
    {% else %}
      {{ post.content | markdownify }}
    {% endif %}
    <a class="comments_action" href="{{ BASE_PATH }}{{ post.url }}#disqus_thread">Leave a comment!</a>
  </div>
{% endfor %}
</div>