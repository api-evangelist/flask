---
title: "Werkzeug 1.0.0 Released"
url: "https://palletsprojects.com/blog/werkzeug-1-0-0-released"
date: "2020-02-06T00:00:00+00:00"
author: "David Lord"
feed_url: "https://palletsprojects.com/blog/feed.xml"
---
<p>The Pallets team is pleased to release Werkzeug 1.0. Werkzeug is the
low-level WSGI and HTTP toolkit that powers Flask. It's been almost 13
years since the first commit, and this milestone for the project brings
many fixes and
changes. <a href="https://werkzeug.palletsprojects.com/page/changes/#version-1-0-0">Read the full changelog</a>
to understand what may affect your code when upgrading.</p>
<ul>
<li>Drop support for Python 3.4. This will be the last version to
support Python 2.7 and 3.5.</li>
<li>Remove most top-level attributes provided by the <code>werkzeug</code> module
in favor of direct imports. If you haven't already, use
<a href="werkzeug-0-16-0-released">version 0.16</a> first to see
deprecation warnings while upgrading.</li>
<li>Cookies support the <code>samesite='None'</code> option. Cookies are parsed
as a <code>MultiDict</code> instead of overwriting repeated keys.</li>
<li>The development server supports 2-way TLS, making it easier to
develop applications that inspect client certificates.</li>
<li>When building URLs with host matching, the current host is accounted
for when deciding what rule to build.</li>
<li>When defining and matching URL rules, consecutive slashes are merged
by default to match the behavior of common HTTP servers.</li>
<li>The <code>Accept</code> header preserves order for tags with equal quality and
considers options on each value. The  <code>Accept-Language</code> header can
match the primary tag if the specific value is not present.</li>
<li>Added CORS header attributes to <code>Request</code> and <code>Response</code>.</li>
<li>A URL rule can be marked as a <code>websocket</code>, in which case it will
only match for <code>wss://</code> requests. This allows async web frameworks
to use Werkzeug for routing.</li>
</ul>
<h2 id="version-20-coming-soon">Version 2.0 Coming Soon <a class="header-anchor" href="#version-20-coming-soon"><p>¶</p></a></h2>
<p>As outlined in <a href="ending-python2-support">Ending Python 2 Support</a>,
1.0.x will be the last version to support Python 2.7 and 3.5. The next
version will be 2.0 and will support Python 3.6 and newer.</p>
<h2 id="install-or-upgrade">Install or Upgrade <a class="header-anchor" href="#install-or-upgrade"><p>¶</p></a></h2>
<p>Install from <a href="https://pypi.org/project/Werkzeug/">PyPI</a> with pip:</p>
<pre><code>pip install -U Werkzeug
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
<p><a href="https://tidelift.com/subscription/pkg/pypi-werkzeug?utm_source=pypi-werkzeug&amp;utm_medium=referral&amp;utm_campaign=enterprise">Learn more.</a></p>
