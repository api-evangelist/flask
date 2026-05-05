---
title: "New Major Versions Released! Flask 2.0, Werkzeug 2.0, Jinja 3.0, Click 8.0, ItsDangerous 2.0, and MarkupSafe 2.0"
url: "https://palletsprojects.com/blog/flask-2-0-released"
date: "2021-05-11T00:00:00+00:00"
author: "David Lord"
feed_url: "https://palletsprojects.com/blog/feed.xml"
---
<p>The Pallets team is pleased to announce that the next major versions for
our six core projects have been released!</p>
<p>This represents two years of work by the Pallets team and community,
there are a significant number of changes and exciting new features.
Check out the logs for every project to see what's new. Flask depends on
the five other libraries, be sure to read them all if you're upgrading
Flask.</p>
<ul>
<li><a href="https://flask.palletsprojects.com/page/changes#version-2-0-0">Flask 2.0</a></li>
<li><a href="https://werkzeug.palletsprojects.com/page/changes/#version-2-0-0">Werkzeug 2.0</a></li>
<li><a href="https://jinja.palletsprojects.com/page/changes/#version-3-0-0">Jinja 3.0</a></li>
<li><a href="https://click.palletsprojects.com/page/changes/#version-8-0">Click 8.0</a></li>
<li><a href="https://itsdangerous.palletsprojects.com/page/changes/#version-2-0-0">ItsDangerous 2.0</a></li>
<li><a href="https://markupsafe.palletsprojects.com/page/changes/#version-2-0-0">MarkupSafe 2.0</a></li>
</ul>
<h2 id="installing-and-upgrading">Installing and Upgrading <a class="header-anchor" href="#installing-and-upgrading"><p>¶</p></a></h2>
<p>Install from PyPI with pip. For example, for Flask:</p>
<pre><code>pip install -U Flask
</code></pre>
<p>The projects have all dropped support for Python 2 and 3.5, requiring
Python 3.6 as the minimum supported version. We plan to follow
CPython's supported versions as our supported versions.</p>
<p>Some less common parts of the projects, or parts that we've determined
are better served by external implementations, have been deprecated.
Previously deprecated code has also been removed. Testing tools such as
<a href="https://docs.pytest.org/">pytest</a> enable showing deprecation warnings
automatically, and can turn them into errors so that you can see early
what you may need to change in your project.</p>
<p>While we strive to avoid compatibility issues, there may turn out to be
incompatibilities either directly or through other dependencies your
project uses, such as Flask extensions. Over the next few weeks, the
ecosystem around our projects will continue to update to improve
compatibility as necessary. We encourage you to use tools such as
<a href="https://pypi.org/project/pip-tools/">pip-compile</a> and
<a href="https://dependabot.com/">Dependabot</a> to pin and control upgrades to
your dependencies to avoid unexpected changes.</p>
<h3 id="renaming-the-default-branch">Renaming the Default Branch <a class="header-anchor" href="#renaming-the-default-branch"><p>¶</p></a></h3>
<p>We are joining the PSF, CPython, and Django, among many other projects,
in renaming the default branch of our repositories to &quot;main&quot;. GitHub
makes this transition easy, see <a href="https://docs.github.com/en/github/administering-a-repository/renaming-a-branch">their documentation about how it works
for maintainers and users</a>.</p>
<p>If you have a local copy of the repository you'll need to rename its
branch to &quot;main&quot;.</p>
<pre><code>$ git branch -m master main
$ git fetch origin
$ git branch -u origin/main main
$ git remote set-head origin -a
</code></pre>
<p>If you were installing from a GitHub archive URL such as
<code>https://github.com/pallets/flask/archive/refs/heads/master.zip</code>, you'll
need to rename that link to use &quot;main&quot;.</p>
<h2 id="release-highlights">Release Highlights <a class="header-anchor" href="#release-highlights"><p>¶</p></a></h2>
<p>These are a few of the great new features and changes to be aware of in
the projects. Check out the linked changelogs for the full lists of
changes.</p>
<ul>
<li>All Projects
<ul>
<li>Support Python 3.6 and above only. Removing the compatibility code
makes the code faster, as well as easier to maintain and
contribute to.</li>
<li>Comprehensive type annotations have been added to the code. This
makes type checking your own code more useful, and allows IDEs to
provide better completion and help.</li>
<li>Use tools such as pre-commit, black, flake8, and pyupgrade to
ensure the code and new PRs follow the same style consistently.</li>
</ul>
</li>
<li><a href="https://flask.palletsprojects.com/page/changes#version-2-0-0">Flask 2.0</a>
<ul>
<li>Support async views and other callbacks such as error handlers,
defined with <code>async def</code>. Regular sync views continue to work
unchanged. ASGI features such as web sockets are not supported. We
will continue exploring how to add more support for async.</li>
<li>Blueprints can be nested under other blueprints, allowing a more
layered approach to organizing the application.</li>
<li>Add route decorators for common HTTP API methods. For example,
<code>@app.post(&quot;/login&quot;)</code> is a shortcut for
<code>@app.route(&quot;/login&quot;, methods=[&quot;POST&quot;])</code>.</li>
<li>Better CLI errors when an app could not be loaded. Running the
development server shows errors immediately, they are only deferred
on reloads.</li>
<li>A new <code>Config.from_file</code> function to load config from any file
format.</li>
<li>The <code>flask shell</code> command enables tab completion like the regular
<code>python</code> shell does.</li>
<li>When serving static files, browsers will cache based on content
rather than a 12 hour timer. This means changes to static content
such as CSS styles will be reflected immediately on reload without
needing to clear the cache.</li>
</ul>
</li>
<li><a href="https://werkzeug.palletsprojects.com/page/changes/#version-2-0-0">Werkzeug 2.0</a>
<ul>
<li>Parsing <code>multipart/form-data</code> has been optimized and shows a <em>15x</em>
speedup, especially for large file uploads.</li>
<li>Locals use Python's <code>ContextVar</code> to allow working across async
coroutines instead of only threads.</li>
<li>All request and response code has been merged into single classes
instead of composing multiple mixin classes.</li>
<li>While this is not a public API yet, the <code>Request</code> and <code>Response</code>
classes are becoming sans-io. This will allow us to better support
sync and async use cases in the future.</li>
<li>The test client always returns a <code>Response</code> class that includes a
reference to the original request, environ, and any redirects that
were followed.</li>
<li><code>datetime</code> objects returned by some headers and functions are
timezone-aware.</li>
<li>URL routing understands <code>ws://</code> and <code>wss://</code> schemes and will
route appropriately. While there is no direct support for
websockets, this allows other projects to use Werkzeug's routing.</li>
<li>Move Flask's implementation of <code>send_file</code> and
<code>send_from_directory</code> to Werkzeug.</li>
<li>The debugger no longer uses jQuery, which significantly reduces
the size of the package.</li>
<li>The reloader is smarter about watching or ignoring directories.</li>
<li>The development server avoids showing <code>0.0.0.0</code> and warns about
not running in production.</li>
<li>Colors are shown correctly in the server log on Windows.</li>
</ul>
</li>
<li><a href="https://jinja.palletsprojects.com/page/changes/#version-3-0-0">Jinja 3.0</a>
<ul>
<li>Async environments and rendering no longer requires patching. This
feature will continue to be improved now that async is natively
supported.</li>
<li>Blocks can be marked as <code>required</code>.</li>
<li>Variables set in blocks or loops can be accessed in context
functions, as well as inner scoped blocks. Macros have access to
the current template globals.</li>
<li>Filters and tests used within <code>if</code> blocks and ternary statements
can be undefined at runtime. Tests have been added to check if a
filter or test is available, to allow optionally using them.</li>
<li>I18N supports <code>pgettext</code> and <code>npgettext</code>.</li>
<li><code>NativeEnvironment</code> supports <code>enable_async</code> mode.</li>
</ul>
</li>
<li><a href="https://click.palletsprojects.com/page/changes/#version-8-0">Click 8.0</a>
<ul>
<li>The shell tab completion system has been completely rewritten. It
now allows every command, group, parameter, and type to provide
custom completion, supports sending metadata such as the type to
the shell for better native support, and provides a way to add
support for new shells.</li>
<li><code>style</code> supports 256 and RGB color codes supported by modern
terminals, as well as the strikethrough, italic, and overline
styles.</li>
<li>New class attributes make it easier to customize the core objects.</li>
<li>The context can manage resources that use context managers across
commands. For example, this makes it easier to manage a database
connection.</li>
<li>Options with <code>multiple=True</code> or <code>nargs</code> don't require setting a
<code>default</code>, and properly validate the format of a default if it's
given.</li>
<li>Options can be used as only a flag to use a default value, or
prompt for a value only if the flag is given.</li>
<li>Prompts validate using the option's custom callback in addition to
its type.</li>
<li>Help formatting and short help message generate has been improved.</li>
<li>Command line arguments on Windows support glob patterns like
<code>*.txt</code> and <code>~/config.json</code>, since the Windows terminal does not
support this automatically.</li>
<li>Messages shown to users, such as validation and errors, are marked
as I18N translatable with <code>gettext</code>.</li>
</ul>
</li>
<li><a href="https://itsdangerous.palletsprojects.com/page/changes/#version-2-0-0">ItsDangerous 2.0</a>
<ul>
<li>Added support for key rotation by passing a list of valid keys
instead of a single key.</li>
<li><code>datetime</code> objects are timezone-aware.</li>
</ul>
</li>
<li><a href="https://markupsafe.palletsprojects.com/page/changes/#version-2-0-0">MarkupSafe 2.0</a>
<ul>
<li>Wheels are provided for 33 Python version / OS / architecture
combinations, to make installing with speedups easy. Newly added
are ManyLinux 2014 and OSX Universal 2 wheels.</li>
</ul>
</li>
</ul>
<h2 id="follow-and-get-involved">Follow and Get Involved <a class="header-anchor" href="#follow-and-get-involved"><p>¶</p></a></h2>
<p>Follow our <a href="/blog/feed.xml">blog RSS feed</a>
or our <a href="https://twitter.com/PalletsTeam">Twitter @PalletsTeam</a> to get
future updates. We also have an official Discord server
https://discord.gg/pallets for chatting, asking questions, and
contributing to the projects.</p>
<p>If you're interested in contributing, each project has a guide showing
how to get started with a development environment and the tools we use.
Check out the issue trackers for each project for what to work on.
Use the <em>Watch</em> feature on GitHub see new issues, PRs, and the
discussions we have around them.</p>
<h2 id="donate-to-support-our-work">Donate to Support Our Work <a class="header-anchor" href="#donate-to-support-our-work"><p>¶</p></a></h2>
<p>The Pallets organization accepts donations as part of the non-profit
Python Software Foundation (PSF). Donations through the PSF support our
efforts to maintain the projects and grow the community.</p>
<p><a href="../donate">Click here to donate. ❤</a></p>
<h3 id="for-enterprise">For Enterprise <a class="header-anchor" href="#for-enterprise"><p>¶</p></a></h3>
<p>The Pallets team and thousands of other packages are working with
Tidelift to deliver commercial support and maintenance for the open
source dependencies you use to build your applications. Save time,
reduce risk, and improve code health, while paying the maintainers of
the exact dependencies you use.</p>
<p><a href="https://tidelift.com/subscription/pkg/pypi-flask?utm_source=pypi-flask&amp;utm_medium=referral&amp;utm_campaign=enterprise&amp;utm_term=repo">Learn more.</a></p>
<h2 id="thank-you">Thank You! <a class="header-anchor" href="#thank-you"><p>¶</p></a></h2>
<p>We've made amazing progress, both by working through the backlog of
issues and PRs, as well as growing the team and community. We have so
many more exciting things in store. Look for more updates soon on
community projects such as documentation translations and FlaskCon
Online 2021! Thank you so much for using, supporting, and contributing
to the Pallets projects!</p>
