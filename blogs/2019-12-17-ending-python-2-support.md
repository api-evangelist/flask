---
title: "Ending Python 2 Support"
url: "https://palletsprojects.com/blog/ending-python2-support"
date: "2019-12-17T00:00:00+00:00"
author: "David Lord"
feed_url: "https://palletsprojects.com/blog/feed.xml"
---
<p>Upstream support for Python 2.7 is ending on <a href="https://www.python.org/dev/peps/pep-0373/">January 1, 2020</a>.
Pallets is joining the <a href="https://python3statement.org/">community of open source projects</a>
ending support for Python 2 at that time. Our statement and support plan
are based on <a href="https://docs.pytest.org/en/5.3.2/py27-py34-deprecation.html">PyTest's announcement</a>.</p>
<p>We will be dropping support for Python 2.7 as well as Python 3.5 and
below, as their support windows have ended or will end around the same
time. Future releases of each Pallets project will only support Python
versions still supported upstream, which can be found in the
<a href="https://devguide.python.org/#status-of-python-branches">Python Developer's Guide</a>.</p>
<p>The last version branch of each core project to support Python 2.7
and Python 3.5 are:</p>
<ul>
<li>Flask 1.1.x</li>
<li>Werkzeug 1.0.x</li>
<li>Click 7.x</li>
<li>Jinja 2.11.x</li>
<li>ItsDangerous 1.1.x</li>
<li>MarkupSafe 1.1.x</li>
</ul>
<p>Each project will receive a major version bump to indicate support
for only 3.6+:</p>
<ul>
<li>Flask 2.0</li>
<li>Werkzeug 2.0</li>
<li>Click 8.0</li>
<li>Jinja 3.0</li>
<li>ItsDangerous 2.0</li>
<li>MarkupSafe 2.0</li>
</ul>
<p>Thanks to the <code>python_requires</code> package metadata, Python 2.7 and
3.5 users with a modern pip version will install the last supported
version automatically even if later versions are available.</p>
<p>The team will no longer backport patches for unsupported versions, but
the branches will continue to exist. The team will be happy to
accept patches contributed by the community for any severe security and
usability issues until mid-2020.</p>
<p>We made this decision based on multiple factors. Foremost is ease of
community contribution and maintainer availability. As time goes on,
fewer contributors have used or are familiar with the differences
between Python 2 and 3. Contributors and maintainers must keep track of
an ever growing list of obscure compatibility issues and workarounds,
and cannot use many modern features.</p>
<p>Over the last two years, we've talked to many developers and teams at
conferences and meetups and heard overwhelming support for the move to
Python 3. This is backed up by data collected from our community in a
survey we ran during January 2019, with 92% of respondents already using
or actively upgrading to Python 3. The <a href="https://www.jetbrains.com/research/python-developers-survey-2018/#python-3-adoption">PSF developer survey</a> and
PyPI statistics report similar majorities and show adoption continuing
to increase.</p>
<p>Thank you to everyone in the community for your support, and to everyone
who has made this transition a reality. We look forward to continuing
to develop the Pallets projects with you!</p>
