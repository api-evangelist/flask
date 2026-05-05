---
title: "Quart is now a Pallets project"
url: "https://palletsprojects.com/blog/quart-pallets"
date: "2022-07-06T00:00:00+00:00"
author: "P G Jones"
feed_url: "https://palletsprojects.com/blog/feed.xml"
---
<p>Quart, an ASGI re-implementation of the Flask API has joined the
Pallets organization. This means that future development will be under
the Pallets governance by the Pallets maintainers.</p>
<p>Our long term aim is to merge Quart and Flask to bring ASGI support
directly to Flask. This aim has significant technical obstacles, as
outlined in this
<a href="https://pgjones.dev/blog/flask-async-quart-sync-2019/">post</a> or this
<a href="https://youtu.be/bw1qeMoFBmw">talk</a>. However, this change clears
governance obstacles and brings the Quart and Flask maintainers closer
together.</p>
<h1>Introduction to Quart</h1>
<p>Quart was developed from a desire to use asyncio and the async/await
keywords in Flask. Which at the time of Quart's inception was not
possible in Flask nor was it possible to add support. Instead Quart
was developed as a reimplementation of Flask's API using async/await
(learn more from this
<a href="https://www.youtube.com/watch?v=EgpQcLy1kf0">talk</a>). Later Quart
adopted the <a href="https://asgi.readthedocs.io">ASGI</a> standard and is now a
compliant ASGI framework.</p>
<p>The Quart API is a superset's of Flask in that it matches Flask's
whilst including ASGI specific features such as websockets, for
example:</p>
<pre><code class="highlight language-python"><span class="kn">from</span><span class="w"> </span><span class="nn">quart</span><span class="w"> </span><span class="kn">import</span> <span class="n">Quart</span><span class="p">,</span> <span class="n">render_template</span><span class="p">,</span> <span class="n">websocket</span>

<span class="n">app</span> <span class="o">=</span> <span class="n">Quart</span><span class="p">(</span><span class="vm">__name__</span><span class="p">)</span>


<span class="nd">@app</span><span class="o">.</span><span class="n">route</span><span class="p">(</span><span class="s2">&quot;/&quot;</span><span class="p">)</span>
<span class="k">async</span> <span class="k">def</span><span class="w"> </span><span class="nf">hello</span><span class="p">():</span>
    <span class="k">return</span> <span class="k">await</span> <span class="n">render_template</span><span class="p">(</span><span class="s2">&quot;index.html&quot;</span><span class="p">)</span>


<span class="nd">@app</span><span class="o">.</span><span class="n">route</span><span class="p">(</span><span class="s2">&quot;/api&quot;</span><span class="p">)</span>
<span class="k">async</span> <span class="k">def</span><span class="w"> </span><span class="nf">json</span><span class="p">():</span>
    <span class="k">return</span> <span class="p">{</span><span class="s2">&quot;hello&quot;</span><span class="p">:</span> <span class="s2">&quot;world&quot;</span><span class="p">}</span>


<span class="nd">@app</span><span class="o">.</span><span class="n">websocket</span><span class="p">(</span><span class="s2">&quot;/ws&quot;</span><span class="p">)</span>
<span class="k">async</span> <span class="k">def</span><span class="w"> </span><span class="nf">ws</span><span class="p">():</span>
    <span class="k">while</span> <span class="kc">True</span><span class="p">:</span>
        <span class="k">await</span> <span class="n">websocket</span><span class="o">.</span><span class="n">send</span><span class="p">(</span><span class="s2">&quot;hello&quot;</span><span class="p">)</span>
        <span class="k">await</span> <span class="n">websocket</span><span class="o">.</span><span class="n">send_json</span><span class="p">({</span><span class="s2">&quot;hello&quot;</span><span class="p">:</span> <span class="s2">&quot;world&quot;</span><span class="p">})</span>
</code></pre>
<p>You can read more about Quart at
<a href="https://quart.palletsprojects.com">quart.palletsprojects.com</a>
including a guide to
<a href="https://quart.palletsprojects.com/page/how_to_guides/flask_migration.html">migrating</a>
from Flask to Quart.</p>
<h2 id="when-to-use-quart">When to use Quart <a class="header-anchor" href="#when-to-use-quart"><p>¶</p></a></h2>
<p>Quart is an ASGI framework utilising async IO throughout, whereas
Flask is a WSGI framework utilising sync IO. It is therefore best to
use Quart if you intend to use async IO (i.e. async/await libraries)
and Flask if not. Don't worry if you choose the 'wrong' framework
though, as Quart supports sync IO and Flask supports async IO,
although less efficiently.</p>
<h1>What's next</h1>
<p>The large ecosystem of Flask extensions is a real strength but
unfortunately these extensions only work with Flask, and vice versa
for Quart extensions. Therefore we plan to enable extensions to
support both Flask and Quart in the future.</p>
<p>We expect to keep developing features for both Flask and Quart, in
fact a number of features now present in Flask were developed in Quart
or from knowledge gained from Quart. This includes typing, async/await
support (in Flask), faster routing, and more.</p>
<p>With the closer relationship now possible both Flask and Quart should
benefit from new features, shared bug fixes, and more. Please join our
<a href="https://discord.gg/pallets">discord</a> if you'd like to get involved.</p>
