---
title: "Click 7.1 Released"
url: "https://palletsprojects.com/blog/click-7-1-released"
date: "2020-03-09T00:00:00+00:00"
author: "David Lord"
feed_url: "https://palletsprojects.com/blog/feed.xml"
---
<p>The Pallets team is pleased to release Click 7.1.</p>
<p><a href="https://click.palletsprojects.com/page/changes/#version-7-1">Read the full changelog</a>
to understand what may affect your code when upgrading.</p>
<ul>
<li>Drop support for Python 3.4. This will be the last version to
support Python 2.7 and 3.5.</li>
<li>Multiple fixes in low-level Windows compatibility code.</li>
<li>Colored output in Jupyter notebooks on Linux and Mac.</li>
<li>Updated Bash and ZSH tab completion support. Add support for Fish.</li>
<li>Better formatting when option help text contains newlines.</li>
</ul>
<p>This also fixes a packaging issue from 7.0 where the project name in the
package metadata was changed to &quot;Click&quot; with an upper case &quot;C&quot;. This has
been reverted, the name is now correctly reported in all lower case, &quot;click&quot;.</p>
<h2 id="version-80-coming-soon">Version 8.0 Coming Soon <a class="header-anchor" href="#version-80-coming-soon"><p>¶</p></a></h2>
<p>As outlined in <a href="ending-python2-support">Ending Python 2 Support</a>,
7.1.x will be the last version to support Python 2.7 and 3.5. The next
version will be 8.0 and will support Python 3.6 and newer.</p>
<h2 id="install-or-upgrade">Install or Upgrade <a class="header-anchor" href="#install-or-upgrade"><p>¶</p></a></h2>
<p>Install from <a href="https://pypi.org/project/click/">PyPI</a> with pip:</p>
<pre><code>pip install -U click
</code></pre>
<h2 id="donate-to-support-pallets">Donate to Support Pallets <a class="header-anchor" href="#donate-to-support-pallets"><p>¶</p></a></h2>
<p>The Pallets organization accepts donations as part of the non-profit
Python Software Foundation (PSF). Donations through the PSF support our
efforts to maintain the projects and grow the community.</p>
<p><a href="../donate">Click here to donate. ❤</a></p>
