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

November 4
----------

    * A roadmap for getting Drummer importing from LogSeq

        * I asked Sabre23t for examples of LogSeq outlines in Markdown, and he [came back](https://github.com/scripting/drummerRFC/issues/4#issuecomment-960981491) with exactly what I wanted and I didn’t even have to say what I wanted. ;-)

        * He took the canonical [states outline](http://opml.org/examples/states.opml?format=opml), in OPML, imported into LogSeq (which it can do) and exported it as Markdown, and pasted it into a comment on GitHub.

        * I’m bookmarking it, so when I swing around to working on this I’ll have everything I need ready to go.

        * I love how the users of Drummer are reaching out and making it work with all the other cool tools! :-)

    * Gary makes progress with Obsidian

        * He’s [reporting](https://twitter.com/gwthompson/status/1456255879641288704) on Twitter.

November 3
----------

    * Steven Johnson on idea processors

        * He’s a famous author, and is working in the area Drummer is in.

        * Here’s his [tweet](https://twitter.com/stevenbjohnson/status/1455925230556286978) this morning about ThinkTank, first shipped almost 40 years ago.

        * Gulp! :-)

    * GitHub

        * One of the holy grails of integrating Drummer with everything is connecting through GitHub.

        * I have [lots of code](http://scripting.com/2021/11/03/142215.html?title=myGithubProjects) that pushes stuff to GitHub, it’s how I automate my nightly backups, for example. Or the opmltweets project. It’s easy when all I want to do is upload to my own repo. I store the credentials in a config.json file on the server, access the file via Node.js and upload via Node.

        * But the problem comes up if I want to do something that works for Drummer users.

        * Well, Scott Hanson [may have the answer](https://github.com/scripting/drummerRFC/issues/3#issuecomment-958793021) in the form of GitHub Actions, which is something that I really don’t understand. But here’s Scott’s explanation. If you’re a GitHub person, here’s something for you to help with possibly.

November 2
----------

    * Obsidian

        * [Gary Thompson](https://twitter.com/gwthompson/status/1455639391137849346) is writing in Drummer for Obsidian.

    * New Old School build

        * As I spent all last week rewriting a big part of Old School, the details of how that piece of software are swapped into my brain. So I’m going to focus there for a while, to do some things that should be done but require a comfort level that I don’t usually have wrt this fairly complex piece of software.

        * What’s new –

            * Old School returns more data about what files it built.

            * The number of secs it returned previously was not accurate. Now the number of seconds is closer to reality. Old School isn’t quite as fast as it used to appear.

            * It returns the version of Old School. This is helpful for everyone to debug wtf is going on. Sometimes we’re running an old version.

            * It also returns the head-level atts from your OPML file. It’s a way to do a reality check if you’re trying to debug weird behavior. Maybe something was wrong in your head level atts? It’s worth checking out.

        * Updated the [oldSchool.buildBlog](http://docserver.scripting.com/?verb=oldSchool.buildBlog) verb.

            * It now takes an optional boolean parameter saying whether you want the full data Old School returns or not.

###### If it’s false or not provided, the verb returns the URL of the blog, as before (no breakage).

        * The data Old School returns is pretty fantastic if you ask me. ;-)

            * {

###### “baseUrl”: “http://clueless.lucky.wtf/”,

###### “ctSecs”: 1.199,

###### “oldSchoolVersion”: “0.7.9”,

###### “eventLog”: {

####### “pagesPublished”: \[

######## “2021/10/30/174131.html”,

######## “2021/10/30/152252.html”,

######## “2021/10/30.html”,

######## “index.html”,

######## “homepage.html”,

######## “rss.json”,

######## “fb/rss.xml”,

######## “index.json”

######## \],

####### “pingsSent”: \[

######## {

######### “urlServer”: “http://rpc.rsscloud.io:5337/ping”,

######### “urlFeed”: “http://clueless.lucky.wtf/rss.json”

######### },

######## {

######### “urlServer”: “http://rpc.rsscloud.io:5337/ping”,

######### “urlFeed”: “http://clueless.lucky.wtf/fb/rss.xml”

######### }

######## \]

####### },

###### “headLevelAtts”: {

####### “dateCreated”: “Mon, 09 Aug 2021 16:53:40 GMT”,

####### “flPublic”: “true”,

####### “urlPublic”: “http://oldschool.scripting.com/cluelessnewbie/”,

####### “description”: “Searching for clues, so far no luck.”,

####### “urlHeaderImage”: “http://scripting.com/images/2020/10/05/sky.png”,

####### “copyright”: “copyright 2021 Dave Winer”,

####### “titlex”: “I don’t have a clue”,

####### “title”: “No clues”,

####### “urlGlossary”: “http://scripting.com/publicfolder/misc/glossary.opml”,

####### “urlLinkblogJson”: “http://radio3.io/users/davewiner/linkblog.json”,

####### “urlAboutOpml”: “http://drummer.scripting.com/cluelessnewbie/about.opml”,

####### “urlBlogWebsite”: “http://clueless.lucky.wtf/”,

####### “timeZoneOffset”: “-5”,

####### “urlTemplate”: “http://scripting.com/code/drummercms/templates/minimal/index.html”,

####### “ownerTwitterScreenName”: “cluelessnewbie”,

####### “ownerName”: “Clueless Newbie”,

####### “ownerId”: “http://twitter.com/cluelessnewbie”,

####### “urlUpdateSocket”: “ws://drummer.scripting.com:1232/”,

####### “dateModified”: “Sun, 31 Oct 2021 15:07:36 GMT”,

####### “expansionState”: “1,2,8,13,14”,

####### “lastCursor”: “12”,

####### “generator”: “opmlPackage v0.4.9”

####### }

###### }

        * You can see a lot more about what it does on your behalf.

    * string.markdownProcess

        * Here’s the [DocServer page](http://docserver.scripting.com/?verb=string.markdownProcess).

        * I’m interested in processing Markdown in Drummer:

            * Reading outline files that are encoded in Markdown, which is popular in Obsidian and LogSeq.

            * Generating output from the outliner using Markdown syntax.

        * I haven’t yet figured out how to do either of these, thinking about it – looking for ideas.

        * In the meantime I thought it would be a good idea to get easy Markdown support into the language, see what happens.

        * I started a [thread](https://github.com/scripting/drummerRFC/issues/4) for discussion.

    * If you have a project to share..

        * The way to go about it is to post an item to on the [RFC issues](https://github.com/scripting/drummerrfc/issues) page.

        * If people want to see it, they will. The other option, spamming other people’s messages is exactly what we don’t want. It’s the equivalent of the rule at BloggerCon where people weren’t allowed to talk about their own products unless invited to by the discussion leader. In this case the DL is the person who started the RFC. It’s not okay to volunteer a pointer to your project in response to an RFC. You could politely and humbly send an email. But please don’t overdo it. Spam is spam and no likes it.

        * This has to be a hard line, because if it’s not, if this product is able to grow, it will eventually devolve into something like Twitter where almost everyone all the time is trying to be heard. Nothing wrong with that, I love Twitter, but that won’t work for a collegial developer community, as the one this is and will stay.

        * You must know that I’ve been through it all. I’m not particularly open-minded about this stuff. I love it when people put out their ideas, and it gives us away to connect with other products, or other users, or help each other have a more powerful environment to use.

    * Please don’t call your work “Drummer”

        * I chose a unique name for this product. It’s not descriptive.

        * When you call your product Drummer – that’s not fair.

        * Be creative. If your work requires a product name, pick one yourself.

        * Thanks.

November 1
----------

    * freeDiskSpace

        * Not related to Drummer specifically, I had to update my [freeDiskSpace](https://github.com/scripting/freeDiskSpace) Node package and app because there was a breaking change (undocumented apparently) in a package called [node-cmd](https://www.npmjs.com/package/node-cmd).

        * The problem was fixed by figuring out which was the last version of node-cmd that worked, and editing my [dependencies list](https://github.com/scripting/freeDiskSpace/blob/master/package.json#L12) to make sure that was the version we used. The routine that disappeared was the central routine, basically the only thing the package actually did.

        * Is this a way to run a platform?

        * As usual this change came up when I was provisioning a new server, when I was already juggling lots of other details, as if I needed to go rewrite a package of my own that I have allocated zero percent of my consciousness to. :smile:

    * The monthly ritual is complete

        * I carefully [documented](http://scripting.com/2021/11/01/125625.html?title=theMonthlyRitual) the monthly ritual this month because it’s the first time I did it since Drummer shipped.

        * There was a bug. The first time I built the Scripting News home page after deleting the October branch, the month of October was a jumble of days in October, whcih now that I found and fixed the problem make sense.

        * It was a matter of calling the JavaScript function getDay when I meant to call getDate. Otherwise even though the new code that was untested until today, it seems to be correct. The home page of my blog is good, even though the content for October is coming from the cache Old School keeps, not from my outline.

        * If you want to try it, you can – but be sure you have a backup! I was glad I had mine.

        * Here’s the [advisory](http://scripting.com/drummer/blog/2021/10/30/145939.html?title=oldSchoolDustsweeping#a150136) I posted on the 30th.

October 2021
============

October 31
----------

    * Drummer & Gatsby via Papascott

        * An [announcement](https://github.com/scripting/drummerRFC/issues/3) from Scott Hanson that he has Drummer working with Gatsby.

        * Here’s the [post](https://www.papascott.de/archives/2021/10/31/blogging-in-gatsby-with-drummer/) that is the proof of concept.

        * Apparently the software is a Gatsby plugin.

        * Gatsby is an [open source](https://github.com/gatsbyjs/gatsby) static site generator. It’s [also](https://www.crunchbase.com/organization/gatsby-e828) a [company](https://www.gatsbyjs.com/about/). Based in Berkeley, has raised \$46.8 million.

        * Looking for an easy tutorial. I have literally never used it, so i would like to at least be able to talk about it, explain what it is and what this connection means.

        * Glad to have it! Our goal is to connect everything with everything. Outlines in the middle. We rock! 😀

October 30
----------

    * Thesaurus

        * Drummer has a thesaurus.

        * A [video demo](https://www.youtube.com/watch?v=0AId6zUZYko).

        * How to

            * First, do a hard-reload of Drummer to get updates.

            * Create a new headline

            * Set the type to word.

            * Enter a word in the headline.

            * Double-click.

            * A list of synonyms fills in under the headline.

            * You can then double-click on any of them.

            * Think of it as navigating the thesaurus in an outline.

    * Bookmarks demo

        * I came across a [video demo](https://www.youtube.com/watch?v=u4pN9L2ArGs) I did of Bookmarks on September 4, before most people were in the loop on Drummer.

    * Posts must have type attributes

        * In the confusion of last week’s fixes for date stuff, a new rule was introduced that has caused some concern in the blogs and in the support forum. The rule comes in two forms:

            * Use the big + icon to create new posts.

            * Every post must have a type attribute that’s either outline, link or tweet. There may be others as we go.

        * I am sorry for the breakage this has caused. I am a strong advocate of the No Breakage School of software development. But this is early days for Drummer, and not making this a rule from the outset was a mistake I didn’t want to live with going forward. The CMS must have a way of telling that something is a post, and only going by the calendar structure isn’t something I want to depend on.

        * If this is a big problem, we can address it with a script that goes through your outline and finds all subs of days that don;’t have type attributes and put them there. It would not be a hard script to write, and I would be happy to do it, if it’s needed.

        * I’ve started a [thread](https://github.com/scripting/drummerSupport/issues/103) on the support forum for this topic, also for any problems resulting from the big shakeup of this week.

        * *Still diggin!* is still the thing we do. :boom:

    * Old School dust-sweeping

        * This doesn’t concern Drummer users directly, but I thought it deserved a change note.

        * I installed the new version of Old School on the server that builds Scripting News. This predates Drummer by 4.5 years, so it works somewhat differently. It seems to work, I did a bunch of writing and rebuilding this morning. I made a couple of changes in cosmetic areas. The result is [something](http://scripting.com/2021/10/30.html) that looks exactly like it should as far as I can tell.

        * In a change note on the 28th, I [talked](http://scripting.com/drummer/blog/2021/10/28/212107.html?title=thisChangeWasDisruptive#a212312) about how you can delete days off the end of your outline, how this is a necessary feature for Scripting News, where I have been writing in the same OPML file for 4.5 years. It would have become unwieldy long before.

        * Here’s my suggestion for Drummer users considering using this feature, and I think eventually most of you *will* want to use it.

            * Wait until November 1 or 2, after I give the all-clear, when we see if it works on Scripting News, and after I’ve had a chance to fix any resulting problems.

        * I’d rather be the test case on this myself before trying to figure out why something went wrong on one of your systems.

        * This is new code, and it’s better to assume it has problems than just assuming it works as documented. Remember Murphy’s Law and It’s even worse than it appears.

October 29
----------

    * DrummerCms changes

        * Link nodes now work properly.

            * Here’s a [demo](http://clueless.lucky.wtf/2021/10/30.html#a131838).

            * They were lost temporarily in the big shakeup.

        * Fixed a bug where an empty blog would cause server to stop responding.

            * By empty blog –\> no calendar, no typed headlines of type outline, tweet or link.

            * An empty blog [looks](http://oldschool.scripting.com/hsy/) kind of stark. I had never seen one before.

October 28
----------

    * And thanks!

        * For all the help.

        * In all my years making software and working with users, I’ve never worked with so great a group of people. Amazing. I know I’ve said it before but I continue to be impressed! :-)

        * I said in a comment today – developers need support too.

        * And for that I am grateful.

    * We won’t do it this way again

        * I can’t remember the last time a product I made had such a chaotic transition.

        * The first order of business is to stabilize everything, so we’re not dealing with broken blogs or outlines.

        * That’s where my focus will be, but at the same time I want to release new stuff too.

    * This change was disruptive

        * Three things changed re blogs in today’s Old School changes.

            * When rendering a blog, an outline must have one of three types. outline, tweet, link. We may add other types, but headlines must have a *type* attribute with one of these values to be a blog post.

            * Every headline should have a *created* attribute. That value and the value of the *timeZoneOffset* head-level attribute are what we key on to know which day “bucket” a post belongs in.

            * You can delete days of posts at the end of your outline without them disappearing from your blog. This is an essential feature for a blog like Scripting News, that has been in the same OPML file for 4.5 years. I have to be able to remove stuff. I actually completely clear my outline at the beginning of every month after archiving it in the [Scripting-News repo](https://github.com/scripting/Scripting-News/tree/master/blog).

        * Use the big plus icon to create new posts and everything will work well. You can add the the attributes by hand, and I can’t imagine why you’d want to do that. Of course you can add and change atts with scripts. :smile:

    * The main CMS server is now updated

        * And is running the new code.

        * So if you rebuild your blog using the Build My Blog command in the Tools menu, it should work as if it were being built in Experiment 3, except it will be at the real address of your blog.

        * Hopefully it will operate smoothly. Fingers crossed. Hoping for the best, expecting the worst.

        * It’s even worse than it appears.

        * Still diggin!

        * Etc.

    * Experiment 3 appears to be a success

        * It would be helpful if everyone who sees this, whether or not you’re in a Far East timezone, tries to build with the new CMS, just to test it out, so you have used it before it becomes the only option.

        * The previous version is in pretty bad shape, I really want to get the new version installed and get beyond the date problems.

        * Here’s the URL:

            * http://scripting.com/code/testing/experiment3/?name=cluelessnewbie

        * I just tried it as if I were from Los Angeles, and there was a problem. Fixed it, now that and the other areas seem to work.

October 27
----------

    * Experiment 3 is ready for you!

        * Dear international friends!

        * Experiment 3 is ready to go, I hope, I think, I pray. ;-)

        * <http://scripting.com/code/testing/experiment3/?name=cluelessnewbie>

        * When you test it out on your blog, just change “cluelessnewbie” to your username.

        * The first time it builds your blog it might take a few seconds.

        * When it’s ready it will respond with a link to the test version of your blog. The real version, the one your readers see, is not changed by this experiment. This is all happening in a temporary space. Just for this test. No actual blogs were harmed.

        * The thing to do then is to look it over and see if it got the timezone stuff right. And then look for any other errors. There has been a lot of rock and roll in Old School behind the scenes, but from your point of view it should be the same Old School you love (I hope) but without the timezone foolishness.

        * Then, try adding a post, and do it again. Did it work?

        * Then, assuming you live east of New York – India, Malaysia, China, Australia, New Zealand and the like, wait until it’s the 29th where you are and it’s still the 28th here. Of if you’re in Europe and you act pretty fast, you can post something just after midnight or so, and it’ll be a good test because then it will still be the 27th here.

        * What you should see is what you would expect based on where you are.

        * Please keep us apprised of what’s happening by posting a [comment here](https://github.com/scripting/drummerSupport/issues/88#issuecomment-953302207).

    * Progress

        * Well, here’s something that works.

        * My cluelessnewbie blog thinks it’s in New Zealand where it is already the 28th.

        * That’s nice. Now can you build the home page for such a blog?

        * Yes, we [can](http://clueless.lucky.wtf/).

        * And can we build an archive page for such a blog, even though the server is in NY where it is still the 27th? Wellllll…

        * Ohhh [yes](http://clueless.lucky.wtf/2021/10/28.html).

        * Note this is in a test server running locally.

    * Morning Drummer Notes

        * [Anton found](https://github.com/scripting/drummerSupport/issues/82#issuecomment-952450047) a data-losing bug yesterday. Unfortunately I’m head-down right now on getting international blogs working properly, it’s a big job that must be done, or else I would join Anton in figuring out what went wrong in this case.

        * Meanwhile there is still a data-losing problem that was uncovered by [Scott Hanson](https://github.com/scripting/drummerSupport/issues/82) ten days ago, similarly I have not been able to focus on that. But these are big issues.

        * Also yesterday, a [report](https://github.com/scripting/drummerSupport/issues/99#issue-1036509784) from gwthompson that the Delete file command deleted a file when he pressed Cancel. I could not reproduce, and after a time, it stopped misbehaving on his machine. If you can confirm, that would be helpful. As always, steps to reproduce are essential. I might just rewrite the confirmation code, it could use it. Caveat: Only test with files you can afford to lose! :smile:

        * Software maintenance is a lot like working on a car, or a human body. Sometimes parts wear out after years of use. You then have to roll up your sleeves and figure out what happened, and fix it. In software, unlike cars and humans, you always can fix it, but sometimes it’s easier than others. A teaser, I came across some features in Old School that people have been asking for that I forgot were there. I will save those to write up for when I’m done with this project.

        * One more thing, I saw on a Drummer blog (I don’t recall which one) someone said that adding links to outline text is very hard and that Markdown is easier. I wonder if people don’t know how easy it is in Drummer. Here’s how you do it…

            * To add a link select the word or phrase you want to link from, click the link icon in the left edge (it’s the second one), paste the URL into the [dialog](http://scripting.com/images/2021/10/27/dialog.png) and click OK. That’s it.

        * The feature is [documented](http://docserver.scripting.com/drummer/iconbar.opml#1630706867000).

        * I can’t wait to be done with what has turned into a fairly major rewrite that is necessary.

    * flCodeSubs for subs that are code

        * Alex Johnstone, trailblazing Drummer blogger, [asks](https://github.com/scripting/drummerSupport/issues/100#issue-1037316578) what’s the best way to include bits of code in a Drummer post. The answer is to add an *flCodeSubs* attribute on the parent of the code block, with a value of true. This should be in the blogging howto, but as yet is not.

October 26
----------

    * Update on The Big Date Bug

        * Thanks for the help in the [Second blog timeZone experiment](http://scripting.com/code/testing/breakdownblogbydays/index.html?name=_am1t), which showed that we do indeed have an algorithm that works that figures out what goes on the home page of a non-US blog using the blog’s local time, at any time in the day or night.

        * I am now rewriting a fairly large part of Old School around this algorithm. It’s the equivalent of open heart surgery. But not as dangerous.

        * Once the work is done, maybe in a day or two, then we will do the *Third blog timeZone experiment,* on a test server, running far away from the deployed version, so we risk nothing, and once that is verified, we can proceed as if this never happened! ❤️

    * You can script your Drummer file backups

        * Alex Johnstone [explains](https://github.com/scripting/drummerSupport/issues/63#issuecomment-951849007). He does it in Python, but you could probably get it to work in Drummer.

October 25
----------

    * This is what system-level scripting is for

        * [Taking steps](https://github.com/scripting/drummerSupport/issues/83#issuecomment-951277662) out of processes we do a lot of.

        * It’s not glamorous, just useful.

    * Second blog timeZone experiment

        * First thanks for all the participation in the [first timeZone experiment](http://scripting.com/code/testing/whatdayisit/index.html). I am now confident we have an algorithm that gets the numeric values for month, day and year, *in the blog’s local time zone* for each post, and now believe we can accurately sort them out into baskets, by day.

        * This will make it possible to restructure the code that builds the home page and the daily and monthly archive pages, so that they work across all time zones.

        * The next test is to try sorting 