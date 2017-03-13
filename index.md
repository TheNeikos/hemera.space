---
layout: "default"
---
<h1>Hemera's Thoughts</h1>
<small>Thoughts, snippets and maybe something interesting</small>

{% assign post_groups = site.posts | group_by_exp:"item", "item.date | date_to_long_string" %}
{{ post_groups | inspect }}
{% for post_group in post_groups %}
<h2>{{post_group.name}}</h2>
<ul class="posts">
    {% for post in post_group.items %}
        <li>
            <a href="{{post.url}}" target="_blank" class="link">[l]</a>
            {{ post.content }}
        </li>
    {% endfor  %}
</ul>
{% endfor %}
