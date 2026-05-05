---
title: "Introducing the Pallets Community Organization (Pallets-Eco)"
url: "https://palletsprojects.com/blog/pallets-community-org"
date: "2022-04-03T00:00:00+00:00"
author: "Kara Babcock"
feed_url: "https://palletsprojects.com/blog/feed.xml"
---
<p>Flask and many of the other Pallets projects benefit from having a diverse
ecosystem of user-maintained extensions. However, we recognize that not every
extension creator can maintain an extension indefinitely. Last year, the
Pallets team started
the <a href="https://github.com/pallets-eco/">Pallets Community Organization</a>,
aka Pallets-Eco, on GitHub to provide a
place where the community can work together to maintain the extensions that we
all rely on.</p>
<p>The popular <a href="https://flask-caching.readthedocs.io/">Flask-Caching</a> and
<a href="http://packages.python.org/Flask-OpenID/">Flask-OpenID</a> extensions have
already been moved to Pallets-Eco.</p>
<p>In time, we hope that this organization will ensure the stability of the Pallets
ecosystem and provide a great point of entry for new contributors.</p>
<h2 id="what-belongs-in-pallets-eco">What Belongs in Pallets-Eco? <a class="header-anchor" href="#what-belongs-in-pallets-eco"><p>¶</p></a></h2>
<p>Although we expect that most extensions we take in will be for Flask, the
organization is open to extensions for <em>any</em> of the Pallets projects—Click,
Jinja, Werkzeug, etc.</p>
<p>It's important to note, however, that this is <em>not</em> an official extension
repository. Extensions in this organization are not guaranteed to be up to date
or maintained by the Pallets team. Rather, this is a centralized place for
members of the wider community to help maintain these extensions.</p>
<p>The Pallets Community Organization is not currently accepting non-extension
projects, such as documentation translations. If you are interested in such
projects, <a href="https://discord.gg/pallets">join the Pallets Discord</a> and ask about
the Flask Community Working Group.</p>
<h2 id="how-you-can-transfer-your-extension">How You Can Transfer Your Extension <a class="header-anchor" href="#how-you-can-transfer-your-extension"><p>¶</p></a></h2>
<p>First, <a href="https://discord.gg/pallets">reach out on Discord</a> (in the <code>#pallets-eco</code>
channel) to express your interest. Only the current owner of a repository can
transfer it, so please don't inquire on behalf of extensions you don't own. If
there is an abandoned extension that you want to start maintaining, <em>fork</em> it,
work on it, and then ask about joining Pallets-Eco.</p>
<p>Second, <a href="https://docs.github.com/en/repositories/creating-and-managing-repositories/transferring-a-repository">review the GitHub docs on transferring a repo</a>.
We will work with you to transfer the repo into the Pallets-Eco organization.</p>
<p>Third, you will need to give some of our organization members access to make
releases on PyPI.</p>
<p>Keep in mind that transferring your extension to the Pallets Community
Organization means you're giving up the final say on how your extension
evolves. You will remain as a collaborator on your extension and can continue
to contribute, but other members will have input on pull requests and when
releases are made. If you prefer to keep your extension completely under your
control, then Pallets-Eco is not for you.</p>
<h2 id="help-with-maintenance">Help With Maintenance <a class="header-anchor" href="#help-with-maintenance"><p>¶</p></a></h2>
<p>Whether you're interested in maintaining one extension in particular or just
contributing to the organization overall, we welcome new contributors! This is
a great starting point if you've always wanted to contribute to a Pallets
project but haven't seen an issue you are ready to tackle—most of the issues in
an extension will be smaller in scope and easier to resolve.</p>
<p>All extensions in the Pallets Community Organization follow the same
<a href="https://github.com/pallets/flask/blob/main/CONTRIBUTING.rst">contributing guidelines</a>
as the core
Pallets projects. Different extensions will come to the organization with
different testing coverage and documentation completion. To that end, even if
an extension doesn't have open issues, it's likely you could improve its tests
and/or docs. After you have reviewed the contributing guidelines, fork the
repo, make changes, and open a pull request when you are ready.</p>
<p>Release permissions will be limited to trusted members of the organization
(you could become one in time). If you have questions that don't belong in a
specific extension's issues, ask in <code>#pallets-eco</code> on the Pallets Discord.</p>
