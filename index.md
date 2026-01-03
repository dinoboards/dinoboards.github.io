---
layout: default
---


# Dinoboards Retro Computer Kits

I have designed and developed a number of retro computer kits, based on technology from the 1980s.  They are designed around the RC2014 and RCBus platforms.

There are 2 main sets of kits:

* **Yellow MSX Series** - a series of RC2014/RCBus compatible modules, when connected together allow for a full working reproduction of an original MSX Computer
* **Green Machine Series** - a new series under development based around the eZ80 CPU - the *enhanced Z80* CPU from Zilog


<style>
.journal-highlights {
}
.journal-highlights ul {
  margin: 0 0 1em 0;
  padding: 0;
  list-style: none;
  margin-left: 4em;
  font-family: monospace;
}
.journal-highlights li {
  margin: 0;
  padding: 0 0 0.1em 0;
  display: flex;
  align-items: baseline;
  gap: 0.7em;
}
.journal-highlights .journal-date {
  color: #888;
  font-size: 0.98em;
  min-width: 6.2em;
  display: inline-block;
  text-align: left;
}
.journal-highlights .rss-link {
  transition: color 0.2s, text-decoration 0.2s;
  /* text-decoration: none; */
}
</style>

<div class="journal-highlights">

<p>Follow along with my journey of developing these kits. (<a href="{{ site.baseurl }}/feed.xml" target="_blank" class="rss-link">Atom/RSS Feed Link</a>)</p>

<ul>
{% for post in site.posts limit:3 %}
<li>
  <a href="{{post.url}}"><span class="journal-date">{{ post.date | date: "%Y-%m-%d" }} </span>{{ post.title }}
  </a>
</li>
{% endfor %}
</ul>
</div>

Also checkout my mastodon account for updates and demo videos: <a href="https://mastodon.social/@dinotron/with_replies"  target="_new" style="">
          <img src="{{ site.baseurl }}/assets/mastodon-logo.svg" style="position: relative; top:4px; height: 1em" />&nbsp;mastodon.social/@dinotron
        </a>

<hr/>
# Green Machine Series

The *Green Machine Series* is a series that is still under development, with the *eZ80 for RC* the first kit in the set.  The series goal is to offer as much compatibility as possible with existing RC2014/RCBus module.  With new modules planned to utilise and explore all the capabilities of Zilog's Z80 compatible CPU.

A FAQ for the green series is being constructed.  You can read it here [Green Series FAQ](./green-faq)

<a href="/green"><img src="{{ site.baseurl }}/assets/green-profile.jpg" alt="Yellow MSX" width="45%"></a>

<a href="/green">Click here to see all the kits available in this series</a>c


<hr/>

# Yellow MSX Series

These are a series of boards developed to achieve MSX+ compatibility.

The idea is that you can build each board one at a time, test it and play with it under RomWBW - and then once you have the set - load up some MSX games!

A working/bootable MSX system can be constructed in various configurations.  You can have all *Yellow* series modules, or use a mixture of Yellow and stock RC2014 modules.

<a href="/yellow"><img src="{{ site.baseurl }}/assets/slot-extension/profile-powered.jpg" alt="Yellow MSX" width="50%"></a>

<a href="/yellow">Click here to see all the kits available in this series</a>


<hr/>

# Green Stegosaur MSX Series

The Stegosaur Green series are a set of newly designed modules.  Their design is very similar to the Yellow MSX series, with some improvements and simplifications.  The main visual difference being their PCBs heights reduced from 8cm down to a more conventional 5.5cm height.

For specifics on the differences, review the module page section titled : "Key difference with Yellow MSX"

<a href="/stegosaur"><img src="{{ site.baseurl }}/stegosaur/v9958/images/v9958-profile.jpg" width="50%"/></a>

<a href="/stegosaur">Click here to see all the first kit available in this series</a>

