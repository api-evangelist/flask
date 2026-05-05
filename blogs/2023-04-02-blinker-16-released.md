---
title: "Blinker 1.6 Released"
url: "https://palletsprojects.com/blog/blinker-1-6-released"
date: "2023-04-02T00:00:00+00:00"
author: "P G Jones"
feed_url: "https://palletsprojects.com/blog/feed.xml"
---
<p>Signalling allows for applications to be decoupled by allowing designated
receivers to be informed when an action has taken place (the signal). Flask and
Quart both utilise the excellent <a href="https://github.com/pallets-eco/blinker">Blinker</a>
library to support signals, and it is version 1.6 of this library that has been
released.</p>
<p>This is the second major release of Blinker since maintenance transferred to the
<a href="pallets-community-org">Pallets-eco</a> organisation, and represents a desire to
maintain it for the benefit of Flask, Quart, and indeed Blinker users.</p>
<p>The <a href="https://blinker.readthedocs.io/page/changes/">Changelog</a> for 1.6 is
headlined by a mondernisation of the project structure which should ensure
easier maintenance into the years to come. In addition, we've added:</p>
<ul>
<li>an ability to temporarily mute signals,</li>
<li>support for int senders,</li>
<li>support for async (coroutine) receivers,</li>
<li>and we've type hinted the project.</li>
</ul>
