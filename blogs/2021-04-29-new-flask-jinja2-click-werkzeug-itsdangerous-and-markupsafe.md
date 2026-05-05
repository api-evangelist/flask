---
title: "New Flask, Jinja2, Click, Werkzeug, ItsDangerous, and MarkupSafe major release candidates"
url: "https://palletsprojects.com/blog/end-python2-prereleases"
date: "2021-04-29T00:00:00+00:00"
author: "Philip Jones"
feed_url: "https://palletsprojects.com/blog/feed.xml"
---
<p>The Pallets team is pleased to announce that release candidates are
now available for the next major version of each project.</p>
<p>Check out the changelogs for every project to see what's new:</p>
<ul>
<li><a href="https://flask.palletsprojects.com/page/changes#version-2-0-0">Flask 2.0</a></li>
<li><a href="https://jinja.palletsprojects.com/page/changes/#version-3-0-0">Jinja2 3.0</a></li>
<li><a href="https://click.palletsprojects.com/page/changes/#version-8-0">Click 8.0</a></li>
<li><a href="https://werkzeug.palletsprojects.com/page/changes/#version-2-0-0">Werkzeug 2.0</a></li>
<li><a href="https://itsdangerous.palletsprojects.com/page/changes/#version-2-0-0">ItsDangerous 2.0</a></li>
<li><a href="https://markupsafe.palletsprojects.com/page/changes/#version-2-0-0">MarkupSafe 2.0</a></li>
</ul>
<p>Please help us prepare for the final release by testing the prerelease
versions and reporting any issues you have. To upgrade to pre-releases
with pip, use the <code>--pre</code> flag, e.g.:</p>
<pre><code>pip install -U --pre Flask
</code></pre>
<p>These new major versions all drop support for Python 2 and 3.5,
requiring Python 3.6 as the minimum supported version.</p>
<h2 id="release-highlights">Release highlights <a class="header-anchor" href="#release-highlights"><p>¶</p></a></h2>
<p>These are a few highlights, see the changelogs linked above for the
full release details. More detailed posts about each project's
highlights will be made with the final releases.</p>
<ul>
<li>All projects (Jinja coming soon) now provide type hints.</li>
<li>Flask gains limited <code>async</code>/<code>await</code> support.</li>
<li>Flask supports nested blueprints.</li>
<li>Flask tells the browser to cache static files more intelligently, so
changes to CSS or images show up immediately.</li>
<li>Flask introduces short form route decorators, such as <code>@app.post()</code>
as a shortcut for <code>@app.route(methods=[&quot;POST&quot;])</code>.</li>
<li>Click's shell completion system has been rewritten.</li>
<li>Click will now prompt for values where they are omitted.</li>
<li>Werkzeug now provides <code>send_file</code> and <code>send_from_directory</code> helpers.</li>
<li>Werkzeug's test client always returns a <code>Response</code> object.</li>
<li>Werkzeug's multipart parsing performance increases by a factor of 15.</li>
</ul>
<h2 id="release-date">Release date <a class="header-anchor" href="#release-date"><p>¶</p></a></h2>
<p>The Pallets team is aiming to release on or before PyCon 2021, i.e. a
target release date of the 11th of May 2021.</p>
