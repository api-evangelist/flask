---
title: "Werkzeug 0.16.0 Released"
url: "https://palletsprojects.com/blog/werkzeug-0-16-0-released"
date: "2019-09-19T00:00:00+00:00"
author: "David Lord"
feed_url: "https://palletsprojects.com/blog/feed.xml"
---
<p>Werkzeug 0.16.0 has been released. The only change is that most of the
top-level attributes in the <code>werkzeug</code> module are now deprecated, and
will be removed in 1.0.0.</p>
<p>For example, instead of <code>import werkzeug; werkzeug.url_quote</code>, do
<code>from werkzeug.urls import url_quote</code>. If you are using these imports in
your project, a deprecation warning will show the correct import to use.
<code>werkzeug.exceptions</code> and <code>werkzeug.routing</code> should also be imported
instead of accessed, but for technical reasons can’t show a warning.</p>
<p>These imports were supported by patching the <code>werkzeug</code> module to
support lazy imports, but the implementation added complexity, and there
was no clear design reason why some things were available and some
weren't. It also masked some circular dependency issues. IDEs like
PyCharm didn't know those lazy imports existed and were already
correctly using the full imports.</p>
