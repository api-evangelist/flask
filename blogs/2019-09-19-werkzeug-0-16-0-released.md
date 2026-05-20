---
title: "Werkzeug 0.16.0 Released"
url: "https://palletsprojects.com/blog/werkzeug-0-16-0-released"
date: "2019-09-19T00:00:00+00:00"
author: "David Lord"
feed_url: "https://palletsprojects.com/blog/feed.xml"
---
Werkzeug 0.16.0 has been released. The only change is that most of the top-level attributes in the werkzeug module are now deprecated, and will be removed in 1.0.0. For example, instead of import werkzeug; werkzeug.url_quote , do from werkzeug.urls import url_quote .
