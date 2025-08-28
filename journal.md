---
layout: default
---

# Journal

<style>
.journal-list {
  list-style: none;
  padding: 0;
}

.year-header {
  margin-top: 2em;
  color: #ffcc00;
  border-bottom: 1px solid #444;
}

.journal-entry {
  margin: 1em 0;
  display: flex;
  align-items: baseline;
}

.entry-date {
  flex: 0 0 120px;
  color: #666;
  font-family: monospace;
}

.entry-title {
  flex: 1;
}

.entry-title a {

  text-decoration: none;
}

.entry-title a:hover {
  color: #ffcc00;
}

</style>

This page lists a number of my blog posts regarding the development of the Yellow MSX Series and the Green eZ80 Green modules.

Many of these entries are dual posted on my hackaday site at: [https://hackaday.io/projects/hacker/522193](https://hackaday.io/projects/hacker/522193)

I also sometimes post updates on my mastodon account: <a href="https://mastodon.social/@dinotron/with_replies"  target="_new" style="">
          <img src="{{ site.baseurl }}/assets/mastodon-logo.svg" style="position: relative; top:4px; height: 1em" />&nbsp;mastodon.social/@dinotron
        </a>

{% assign posts = site.posts | sort: 'date' | reverse %}
{% assign currentYear = "" %}

<ul class="journal-list">
{% for post in posts %}
  {% assign postYear = post.date | date: "%Y" %}

  {% if currentYear != postYear %}
    {% assign currentYear = postYear %}
    <h2 class="year-header">{{ currentYear }}</h2>
  {% endif %}

  <li class="journal-entry">
    <span class="entry-date">{{ post.date | date: "%Y-%m-%d" }}</span>
    <span class="entry-title"><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></span>
  </li>
{% endfor %}
</ul>
