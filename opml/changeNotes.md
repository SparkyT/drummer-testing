author: Dave Winer
date: Sat, 06 Nov 2021 20:19:58 GMT
title: Change notes

November 2021
=============

November 6
----------

    * drummer.this.how

        * On a walk today I was going over things I wanted to look at, based on what I’m hearing from [Drummer](http://drummer.scripting.com/) users, and standalone files is high on the list. The thought had been that we’d do it based on the partially done feature in Old School. But then I realized that Old School isn’t the only way to do standalone pages. Look at how the [Drummer docs](http://docserver.scripting.com/drummer/about.opml) work. Why shouldn’t Drummer users have the ability to do docs like that? Indeed. And then I recalled that we have that [for LO2](http://my.this.how/davewiner/howtos.opml), so why not do it for Drummer? Yes. It’s done and it works. :boom:

        * An example, the canonical [states.opml](http://drummer.scripting.com/davewiner/states.opml), viewed through this lens.

            * <http://drummer.this.how/davewiner/states.opml>

        * I just constructed another path to the file as follows:

            * states.opml is a public file in my Drummer directory.

            * I direct the request at a special site on the server in a folder called drummer.this.how.

            * The second part of the URL is my username.

            * And the third part is the name of the OPML file.

            * It’s just a simple [PagePark plug-in](http://pagepark.io/docs/plugins.md), written in JavaScript.

        * It should work for you too!

            * Questions, comments [here](https://github.com/scripting/drummerSupport/issues/105).

    * http.client verb, day 2

        * There’s a new version of the [http.client](http://docserver.scripting.com/?verb=http.client) verb.

        * You can help by running a simple experiment, [explained here](https://github.com/scripting/drummerRFC/issues/6#issuecomment-962468957). It’s definitely something a poet can run, but it’s mostly for plumbers. 😀

        * Before testing please reload your Drummer web app to get the latest changes.

        * For now, the changes are only in web Drummer. I use Electric Drummer myself so you know getting a new release of that is high on my list.

        * Devs: This is very fluid right now, if you see things that are wrong, *now* is the time to speak up. Once it’s frozen, the no-breakage rule kicks in.

        * This is a *central verb*, and the better it is, the more flexible Drummer scripting will be. It’s how Drummer will connect to the web. Everything will go through it. It pays to get this right.

        * This is the [thread](https://github.com/scripting/drummerRFC/issues/6).

November 5
----------

    * New verb: http.client

        * I’ve been working on a big HTTP client verb, that does all the things you’d ever want to do via HTTP.

        * This is a first release. It will get more features over time. And there will be breakage, that’s why I’m putting [the thread](https://github.com/scripting/drummerRFC/issues/6) to discuss this on the RFC site.

        * I want feedback, and reserve the right to make breaking changes as is made very clear on the [DocServer page](http://docserver.scripting.com/?verb=http.client).

    * Tools-for-thought databases thread

        * Kevin Tofel started off an [interesting thread](https://github.com/scripting/drummerRFC/issues/5).

        * I still want all my OPML archives in various [tools-for-thought databases](https://github.com/scripting/drummerRFC/issues/5#issuecomment-961942204).

        * I’m most hopeful wrt LogSeq. But eventually we will have lots of databases (imho) that work well with OPML.

        * And I think even would-be-dominant products like Roam will want to open up, rather than be left out of the party.

        * PS: An important point I don’t want anyone to miss –

            * You can have OPML in JSON. We have a [toolkit](https://www.npmjs.com/package/opml?activeTab=readme) that reads OPML files and returns JavaScript structures. From there, do whatever you want. Save it as JSON. It’s up to you. I wouldn’t have left this stone un-turned-over, so before assuming something like that doesn’t exist, ask.

November 