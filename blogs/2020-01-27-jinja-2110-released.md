---
title: "Jinja 2.11.0 Released"
url: "https://palletsprojects.com/blog/jinja-2-11-0-released"
date: "2020-01-27T00:00:00+00:00"
author: "David Lord"
feed_url: "https://palletsprojects.com/blog/feed.xml"
---
<p>The Pallets team is pleased to release <a href="https://jinja.palletsprojects.com">Jinja</a> 2.11.0.
<a href="https://jinja.palletsprojects.com/page/changes#version-2-11-0">Read the changelog</a>
for the full list of changes. Some of the bigger changes include:</p>
<ul>
<li>Drop support for Python 2.6, 3.3, and 3.4. This will be the last
version to support Python 2.7 and 3.5.</li>
<li>A new <code>jinja2.ext.debug</code> extension adds a <code>{% debug %}</code> tag to
quickly dump the current template context.</li>
<li>A new <code>ChainableUndefined</code> type allows silently ignoring attribute
access on undefined variables.</li>
<li>Loop context variables like <code>loop.length</code> and <code>loop.nextitem</code> work
better in both sync and async environments.</li>
<li>Improved compile and runtime performance.</li>
</ul>
<h2 id="version-30-coming-soon">Version 3.0 Coming Soon <a class="header-anchor" href="#version-30-coming-soon"><p>¶</p></a></h2>
<p>As outlined in <a href="ending-python2-support">Ending Python 2 Support</a>,
2.11.x will be the last version to support Python 2.7 and 3.5. The next
version will be 3.0 and will support Python 3.6 and newer.</p>
<p>The package name will remain &quot;Jinja2&quot; and imports will remain <code>jinja2</code>.
&quot;Jinja2 3.0&quot; looks a little weird, but given the years of community
momentum behind the name, we concluded it was less disruptive to keep it
as-is.</p>
<h2 id="install-or-upgrade">Install or Upgrade <a class="header-anchor" href="#install-or-upgrade"><p>¶</p></a></h2>
<p>Install from <a href="https://pypi.org/project/Jinja2/">PyPI</a> with pip:</p>
<pre><code>pip install -U Jinja2
</code></pre>
<h2 id="donate-to-support-pallets">Donate to Support Pallets <a class="header-anchor" href="#donate-to-support-pallets"><p>¶</p></a></h2>
<p>The Pallets organization accepts donations as part of the non-profit
Python Software Foundation (PSF). Donations through the PSF support our
efforts to maintain the projects and grow the community.</p>
<p><a href="../donate">Click here to donate. ❤</a></p>
<h2 id="for-enterprise">For Enterprise <a class="header-anchor" href="#for-enterprise"><p>¶</p></a></h2>
<p>The Pallets team and thousands of other packages are working with
Tidelift to deliver commercial support and maintenance for the open
source dependencies you use to build your applications. Save time,
reduce risk, and improve code health, while paying the maintainers of
the exact dependencies you use.</p>
<p><a href="https://tidelift.com/subscription/pkg/pypi-jinja2?utm_source=pypi-jinja2&amp;utm_medium=referral&amp;utm_campaign=enterprise">Learn more.</a></p>
