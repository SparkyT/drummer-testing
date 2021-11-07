# November 2021

* November 6

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

    * It should work for you too\!

      * Questions, comments [here](https://github.com/scripting/drummerSupport/issues/105).

  * http.client verb, day 2

    * There’s a new version of the [http.client](http://docserver.scripting.com/?verb=http.client) verb.

    * You can help by running a simple experiment, [explained here](https://github.com/scripting/drummerRFC/issues/6#issuecomment-962468957). It’s definitely something a poet can run, but it’s mostly for plumbers. 😀

    * Before testing please reload your Drummer web app to get the latest changes.

    * For now, the changes are only in web Drummer. I use Electric Drummer myself so you know getting a new release of that is high on my list.

    * Devs: This is very fluid right now, if you see things that are wrong, *now* is the time to speak up. Once it’s frozen, the no-breakage rule kicks in.

    * This is a *central verb*, and the better it is, the more flexible Drummer scripting will be. It’s how Drummer will connect to the web. Everything will go through it. It pays to get this right.

    * This is the [thread](https://github.com/scripting/drummerRFC/issues/6).

* November 5

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

* November 4

  * A roadmap for getting Drummer importing from LogSeq

    * I asked Sabre23t for examples of LogSeq outlines in Markdown, and he [came back](https://github.com/scripting/drummerRFC/issues/4#issuecomment-960981491) with exactly what I wanted and I didn’t even have to say what I wanted. ;-)

    * He took the canonical [states outline](http://opml.org/examples/states.opml?format=opml), in OPML, imported into LogSeq (which it can do) and exported it as Markdown, and pasted it into a comment on GitHub.

    * I’m bookmarking it, so when I swing around to working on this I’ll have everything I need ready to go.

    * I love how the users of Drummer are reaching out and making it work with all the other cool tools\! :-)

  * Gary makes progress with Obsidian

    * He’s [reporting](https://twitter.com/gwthompson/status/1456255879641288704) on Twitter.

* November 3

  * Steven Johnson on idea processors

    * He’s a famous author, and is working in the area Drummer is in.

    * Here’s his [tweet](https://twitter.com/stevenbjohnson/status/1455925230556286978) this morning about ThinkTank, first shipped almost 40 years ago.

    * Gulp\! :-)

  * GitHub

    * One of the holy grails of integrating Drummer with everything is connecting through GitHub.

    * I have [lots of code](http://scripting.com/2021/11/03/142215.html?title=myGithubProjects) that pushes stuff to GitHub, it’s how I automate my nightly backups, for example. Or the opmltweets project. It’s easy when all I want to do is upload to my own repo. I store the credentials in a config.json file on the server, access the file via Node.js and upload via Node.

    * But the problem comes up if I want to do something that works for Drummer users.

    * Well, Scott Hanson [may have the answer](https://github.com/scripting/drummerRFC/issues/3#issuecomment-958793021) in the form of GitHub Actions, which is something that I really don’t understand. But here’s Scott’s explanation. If you’re a GitHub person, here’s something for you to help with possibly.

* November 2

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

        * If it’s false or not provided, the verb returns the URL of the blog, as before (no breakage).

    * The data Old School returns is pretty fantastic if you ask me. ;-)

      * {

        * “baseUrl”: “http://clueless.lucky.wtf/”,

        * “ctSecs”: 1.199,

        * “oldSchoolVersion”: “0.7.9”,

        * “eventLog”: {

# “pagesPublished”: \[

# “2021/10/30/174131.html”,

# “2021/10/30/152252.html”,

# “2021/10/30.html”,

# “index.html”,

# “homepage.html”,

# “rss.json”,

# “fb/rss.xml”,

# “index.json”

# \],

# “pingsSent”: \[

# {

# “urlServer”: “http://rpc.rsscloud.io:5337/ping”,

# “urlFeed”: “http://clueless.lucky.wtf/rss.json”

# },

# {

# “urlServer”: “http://rpc.rsscloud.io:5337/ping”,

# “urlFeed”: “http://clueless.lucky.wtf/fb/rss.xml”

# }

# \]

# },

        * “headLevelAtts”: {

# “dateCreated”: “Mon, 09 Aug 2021 16:53:40 GMT”,

# “flPublic”: “true”,

# “urlPublic”: “http://oldschool.scripting.com/cluelessnewbie/”,

# “description”: “Searching for clues, so far no luck.”,

# “urlHeaderImage”: “http://scripting.com/images/2020/10/05/sky.png”,

# “copyright”: “copyright 2021 Dave Winer”,

# “titlex”: “I don’t have a clue”,

# “title”: “No clues”,

# “urlGlossary”: “http://scripting.com/publicfolder/misc/glossary.opml”,

# “urlLinkblogJson”: “http://radio3.io/users/davewiner/linkblog.json”,

# “urlAboutOpml”: “http://drummer.scripting.com/cluelessnewbie/about.opml”,

# “urlBlogWebsite”: “http://clueless.lucky.wtf/”,

# “timeZoneOffset”: “-5”,

# “urlTemplate”: “http://scripting.com/code/drummercms/templates/minimal/index.html”,

# “ownerTwitterScreenName”: “cluelessnewbie”,

# “ownerName”: “Clueless Newbie”,

# “ownerId”: “http://twitter.com/cluelessnewbie”,

# “urlUpdateSocket”: “ws://drummer.scripting.com:1232/”,

# “dateModified”: “Sun, 31 Oct 2021 15:07:36 GMT”,

# “expansionState”: “1,2,8,13,14”,

# “lastCursor”: “12”,

# “generator”: “opmlPackage v0.4.9”

# }

        * }

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

* November 1

  * freeDiskSpace

    * Not related to Drummer specifically, I had to update my [freeDiskSpace](https://github.com/scripting/freeDiskSpace) Node package and app because there was a breaking change (undocumented apparently) in a package called [node-cmd](https://www.npmjs.com/package/node-cmd).

    * The problem was fixed by figuring out which was the last version of node-cmd that worked, and editing my [dependencies list](https://github.com/scripting/freeDiskSpace/blob/master/package.json#L12) to make sure that was the version we used. The routine that disappeared was the central routine, basically the only thing the package actually did.

    * Is this a way to run a platform?

    * As usual this change came up when I was provisioning a new server, when I was already juggling lots of other details, as if I needed to go rewrite a package of my own that I have allocated zero percent of my consciousness to. :smile:

  * The monthly ritual is complete

    * I carefully [documented](http://scripting.com/2021/11/01/125625.html?title=theMonthlyRitual) the monthly ritual this month because it’s the first time I did it since Drummer shipped.

    * There was a bug. The first time I built the Scripting News home page after deleting the October branch, the month of October was a jumble of days in October, whcih now that I found and fixed the problem make sense.

    * It was a matter of calling the JavaScript function getDay when I meant to call getDate. Otherwise even though the new code that was untested until today, it seems to be correct. The home page of my blog is good, even though the content for October is coming from the cache Old School keeps, not from my outline.

    * If you want to try it, you can – but be sure you have a backup\! I was glad I had mine.

    * Here’s the [advisory](http://scripting.com/drummer/blog/2021/10/30/145939.html?title=oldSchoolDustsweeping#a150136) I posted on the 30th.

# October 2021

* October 31

  * Drummer & Gatsby via Papascott

    * An [announcement](https://github.com/scripting/drummerRFC/issues/3) from Scott Hanson that he has Drummer working with Gatsby.

    * Here’s the [post](https://www.papascott.de/archives/2021/10/31/blogging-in-gatsby-with-drummer/) that is the proof of concept.

    * Apparently the software is a Gatsby plugin.

    * Gatsby is an [open source](https://github.com/gatsbyjs/gatsby) static site generator. It’s [also](https://www.crunchbase.com/organization/gatsby-e828) a [company](https://www.gatsbyjs.com/about/). Based in Berkeley, has raised $46.8 million.

    * Looking for an easy tutorial. I have literally never used it, so i would like to at least be able to talk about it, explain what it is and what this connection means.

    * Glad to have it\! Our goal is to connect everything with everything. Outlines in the middle. We rock\! 😀

* October 30

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

    * *Still diggin\!* is still the thing we do. :boom:

  * Old School dust-sweeping

    * This doesn’t concern Drummer users directly, but I thought it deserved a change note.

    * I installed the new version of Old School on the server that builds Scripting News. This predates Drummer by 4.5 years, so it works somewhat differently. It seems to work, I did a bunch of writing and rebuilding this morning. I made a couple of changes in cosmetic areas. The result is [something](http://scripting.com/2021/10/30.html) that looks exactly like it should as far as I can tell.

    * In a change note on the 28th, I [talked](http://scripting.com/drummer/blog/2021/10/28/212107.html?title=thisChangeWasDisruptive#a212312) about how you can delete days off the end of your outline, how this is a necessary feature for Scripting News, where I have been writing in the same OPML file for 4.5 years. It would have become unwieldy long before.

    * Here’s my suggestion for Drummer users considering using this feature, and I think eventually most of you *will* want to use it.

      * Wait until November 1 or 2, after I give the all-clear, when we see if it works on Scripting News, and after I’ve had a chance to fix any resulting problems.

    * I’d rather be the test case on this myself before trying to figure out why something went wrong on one of your systems.

    * This is new code, and it’s better to assume it has problems than just assuming it works as documented. Remember Murphy’s Law and It’s even worse than it appears.

* October 29

  * DrummerCms changes

    * Link nodes now work properly.

      * Here’s a [demo](http://clueless.lucky.wtf/2021/10/30.html#a131838).

      * They were lost temporarily in the big shakeup.

    * Fixed a bug where an empty blog would cause server to stop responding.

      * By empty blog –\> no calendar, no typed headlines of type outline, tweet or link.

      * An empty blog [looks](http://oldschool.scripting.com/hsy/) kind of stark. I had never seen one before.

* October 28

  * And thanks\!

    * For all the help.

    * In all my years making software and working with users, I’ve never worked with so great a group of people. Amazing. I know I’ve said it before but I continue to be impressed\! :-)

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

    * Still diggin\!

    * Etc.

  * Experiment 3 appears to be a success

    * It would be helpful if everyone who sees this, whether or not you’re in a Far East timezone, tries to build with the new CMS, just to test it out, so you have used it before it becomes the only option.

    * The previous version is in pretty bad shape, I really want to get the new version installed and get beyond the date problems.

    * Here’s the URL:

      * http://scripting.com/code/testing/experiment3/?name=cluelessnewbie

    * I just tried it as if I were from Los Angeles, and there was a problem. Fixed it, now that and the other areas seem to work.

* October 27

  * Experiment 3 is ready for you\!

    * Dear international friends\!

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

    * Also yesterday, a [report](https://github.com/scripting/drummerSupport/issues/99#issue-1036509784) from gwthompson that the Delete file command deleted a file when he pressed Cancel. I could not reproduce, and after a time, it stopped misbehaving on his machine. If you can confirm, that would be helpful. As always, steps to reproduce are essential. I might just rewrite the confirmation code, it could use it. Caveat: Only test with files you can afford to lose\! :smile:

    * Software maintenance is a lot like working on a car, or a human body. Sometimes parts wear out after years of use. You then have to roll up your sleeves and figure out what happened, and fix it. In software, unlike cars and humans, you always can fix it, but sometimes it’s easier than others. A teaser, I came across some features in Old School that people have been asking for that I forgot were there. I will save those to write up for when I’m done with this project.

    * One more thing, I saw on a Drummer blog (I don’t recall which one) someone said that adding links to outline text is very hard and that Markdown is easier. I wonder if people don’t know how easy it is in Drummer. Here’s how you do it…

      * To add a link select the word or phrase you want to link from, click the link icon in the left edge (it’s the second one), paste the URL into the [dialog](http://scripting.com/images/2021/10/27/dialog.png) and click OK. That’s it.

    * The feature is [documented](http://docserver.scripting.com/drummer/iconbar.opml#1630706867000).

    * I can’t wait to be done with what has turned into a fairly major rewrite that is necessary.

  * flCodeSubs for subs that are code

    * Alex Johnstone, trailblazing Drummer blogger, [asks](https://github.com/scripting/drummerSupport/issues/100#issue-1037316578) what’s the best way to include bits of code in a Drummer post. The answer is to add an *flCodeSubs* attribute on the parent of the code block, with a value of true. This should be in the blogging howto, but as yet is not.

* October 26

  * Update on The Big Date Bug

    * Thanks for the help in the [Second blog timeZone experiment](http://scripting.com/code/testing/breakdownblogbydays/index.html?name=_am1t), which showed that we do indeed have an algorithm that works that figures out what goes on the home page of a non-US blog using the blog’s local time, at any time in the day or night.

    * I am now rewriting a fairly large part of Old School around this algorithm. It’s the equivalent of open heart surgery. But not as dangerous.

    * Once the work is done, maybe in a day or two, then we will do the *Third blog timeZone experiment,* on a test server, running far away from the deployed version, so we risk nothing, and once that is verified, we can proceed as if this never happened\! ❤️

  * You can script your Drummer file backups

    * Alex Johnstone [explains](https://github.com/scripting/drummerSupport/issues/63#issuecomment-951849007). He does it in Python, but you could probably get it to work in Drummer.

* October 25

  * This is what system-level scripting is for

    * [Taking steps](https://github.com/scripting/drummerSupport/issues/83#issuecomment-951277662) out of processes we do a lot of.

    * It’s not glamorous, just useful.

  * Second blog timeZone experiment

    * First thanks for all the participation in the [first timeZone experiment](http://scripting.com/code/testing/whatdayisit/index.html). I am now confident we have an algorithm that gets the numeric values for month, day and year, *in the blog’s local time zone* for each post, and now believe we can accurately sort them out into baskets, by day.

    * This will make it possible to restructure the code that builds the home page and the daily and monthly archive pages, so that they work across all time zones.

    * The next test is to try sorting actual blog.opml files.

    * For example, I have temporarily changed the timeZoneOffset attribute for [cluelessnewbie](http://clueless.lucky.wtf/) to 12, which means it’s now already the 26th according to my blog. And sure enough the top two posts that I just created appear in the sorting in the 26th.

    * Here’s the link I used to test that.

    * <http://scripting.com/code/testing/breakdownblogbydays/?name=cluelessnewbie>

    * You can run the test against your blog by changing the name parameter on the URL to the name you use for your Drummer account, and see if the algorithm correctly sorts your posts into days.

    * [Report the results here](https://github.com/scripting/drummerSupport/issues/88#issuecomment-951088327). Be sure to include your name, so we can run the test too.

    * Thanks for the help. This has been a uniquely cooperative process, for what is a surprisingly difficult problem. ;-)

  * Update to default template CSS

    * Thanks to [Amit](https://github.com/scripting/drummerSupport/issues/98#issue-1034737224) for the report of two errors in the [default template CSS](http://scripting.com/code/drummercms/templates/minimal/styles.css) for Drummer blogs.

    * [While I was there](https://github.com/scripting/drummerSupport/issues/98#issuecomment-950939742) I found a third omission, and fixed it,

    * Net result of these changes – your sites should work better on phone-size devices.

* October 23

  * Another timezone approach

    * OK – once I [gave up](http://scripting.com/drummer/blog/2021/10/23/131437.html?title=timezonesArrrgh) on getting it done today, I started to think about the problem differently.

    * As you can hear in my [second voicemail](http://scripting.com/2021/10/23/progressReportOnDateStuff.m4a), the question that was so hard to answer is this:

      * What day is it in the location the user is in?

    * It’s just an algorithm, it must be possible to get the computer to figure that out. So I put together this little app.

      * <http://scripting.com/code/testing/whatdayisit/>

    * I’m turning to my friends around the world to check this little app, over the course of a day and let me know if it’s got it right.

    * Comment [here](https://github.com/scripting/drummerSupport/issues/88#issuecomment-950206243).

  * Timezones arrrgh

    * I didn’t make any progress on the problem, and my work day is over.

      * So – here’s the thing, I’m not going to be able to work on this for a bit, and when I do, it’s going to be with a test server.

      * Bottom line – dates are weird, and we’re pushing up against the limits of the language here.

      * It’s time to take a step back, work on some other stuff for a while, and come back to this with a fresh perspective.

      * What this means is, if you’re hit by this issue, finding a way to work with it until the problems are fixed.

      * That happens sometimes, I want nothing more than to put this behind us, but it isn’t going to happen in the next few days.

    * Here’s the report from this morning

      * I swear I’m going to have this nailed by end of business today.

      * It’s all math, but it’s really confusing when you’re in one time zone and the users are far away in different time zones.

      * Thanks to Amit for championing this. 👍

      * A [voicemail](http://scripting.com/2021/10/23/moreThoughtsOnTimeZonesAndBlogs.m4a) on the zen of timezones in blogging.

      * [Progress report](http://scripting.com/2021/10/23/progressReportOnDateStuff.m4a). Not going very well, JS is not cooperating.

  * PagePark fix

    * Fixed default error page for sites using PagePark and hosting over HTTPS

    * It was loading a font and an image over HTTP which is a no-no.

  * Publishing to WordPress gets started

    * Frank Meeuwsen is [working](http://oldschool.scripting.com/frankmeeuwsen/2021/10/23/065437.html?title=publishToWordpressWithDrummer) on a script to publish to WordPress from his Drummer outline.

    * He says he’s not a programmer, but reading his code, he’s figured a bunch of stuff out.

    * It’s a *perfect* use of the [new RFC site](https://github.com/scripting/drummerRFC/issues/1).

    * We can fill in all the details as far as Drummer is concerned, so don’t worry about that. The important contribution here is that Frank is digging in to the WordPress API, one that I have looked at and not grokked. So just focus on getting that part right, and I’m happy to add new verbs to the language to support this connection.

    * I can imagine a class of verbs for WordPress, it’s that important a product for Drummer to connect to.

  * Drummer has a new bookmarklet

    * It’s [documented](http://docserver.scripting.com/drummer/general.opml#1634950078000) on the FAQs page.

    * You install it in the usual way, by dragging a bit of text to the icon bar in your browser, also known as its “chrome.”

    * Think of it as a way to save a link to something on the web without leaving a tab open in the browser.

    * The clip is added to the calendar structure of your Notes outline.

    * If you have comments or questions, I started a thread [here](https://github.com/scripting/drummerSupport/issues/96).

* October 22

  * Bug for non-American blogs

    * It’s a timezone issue, thanks to Amit for finding it, reporting it, and re-reporting it.

    * It’s a nasty one because it moves around, and depends on what time of day he started blogging, believe it or not.

    * If you’re sufficiently east of the US, and you start blogging early in the day (relatively) you might not see today’s posts on your home page.

    * This will be fixed shortly, but I wanted to give you all a heads up in case you’re seeing this, you’re not losing your mind. 😛

    * Follow along in [this thread](https://github.com/scripting/drummerSupport/issues/88).

    * Update: Two problems were [found and fixed](https://github.com/scripting/drummerSupport/issues/88#issuecomment-949702524) and now Amit’s blog is building correctly.

    * There’s a new release of [Old School](https://github.com/scripting/oldSchoolBlog) with the fixes and the new version is deployed on the server.

    * And now I will take a much-needed break. 😀

    * Update at 6PM Eastern – more work needed tomorrow, we have the problem solved for India, but still more to do for New Zealand. Amit has been a huge help.

* October 21

  * A new version of Public Folder app

    * [Amit Gawande](https://github.com/scripting/drummerSupport/issues/83) has been trying to figure out the workflow for images from his desktop, to the web and back into web Drummer.

    * Electric Drummer already has this facility built into it, but Amit can’t use E/D for his application, since he has to be able to edit his blog from multiple locations.

    * I suggested he try my [Public Folder](http://publicfolder.io/) app. I was hoping he would use it because then I would have someone who could test its use with Drummer in a real world setting, and work with me to create a smooth workflow for people working from the web Drummer. It really helps to have another human being with the perspective of a user as something is developing. And I wanted to solve the problem not just for E/D for for web Drummer too.

    * So, I had an idea how this might work, but unfortunately it wasn’t possible to connect from the web browser to a local web server, which is actually what the Public Folder app is. We had a lot of fun with [fractional horsepower http servers](http://scripting.com/davenet/1997/09/14/FractionalHorsepowerHTTPSe.html) in Frontier in the 90s, but the powers that be thought this was a security problem (it likely is) so that avenue is no longer open. Tis a shame. We were so much more innocent then\! :boom:

    * Then I had the idea that since Public Folder is able to write files to S3, and Drummer scripts can read those files, that might work. And – *tadahh* – it did work, resulting in version 0.4.8 of [Public Folder](http://this.how/publicFolder/), which is now available for download. The instructions on [how to set up](http://this.how/publicFolder/#1634847088000) are also on that page.

    * I was sure at some time Public Folder would come in handy for others. I already depend on it myself for all my this.how style outlines, including the docs for Drummer, which are all uploaded publicly via Public Folder.

    * The idea of Public Folder, btw, was to replace the public folder [Dropbox used to have](http://scripting.com/stories/2011/04/25/publicDropboxWithoutTheLoc.html) which it phased out. It was an important thing.

    * I think eventually all my apps will fit into *The World of Drummer* in some way. It’s like the Marvel Universe or a big family reunion. :heart:

  * I’m not keeping up with the error reports

    * I know the rope is slipping through my hands.

    * I try to spend some time each day looking at fixing bugs, but I have to move forward on other fronts too, and I only spend about 4-5 hours working on this stuff every day. Any more than that is a waste of time, I lose productivity, burn myself out, am unhappy and eventually it makes me sick. Not that you wanted to know all that. ;-)

    * Sometimes I can’t dig in because I don’t understand what happened, because (honestly) the reports are not well specificed, or well written. People can help out by trying to get reproducible steps, that makes it a quicker job for me, more likely to result in a fix, rather than wasted time.

    * Sometimes I can’t dig in because I just can’t get there. Esp problems in [Concord](https://github.com/scripting/concord), the core outliner. It is open source, so other people can work on that.

    * PS: One of the things on my todo list is to update the Concord repo with my latest fixes.

  * A place for Drummer RFCs

    * I started a new GitHub repo called [DrummerRFC](https://github.com/scripting/drummerRFC/blob/main/README.md).

    * Read the [readme](https://github.com/scripting/drummerRFC/blob/main/README.md) with some care before posting an [RFC](https://en.wikipedia.org/wiki/Request_for_Comments).

    * It’s not for support and bug reports, that’s what the [support site](https://github.com/scripting/drummerSupport/issues) is for.

    * It’s also not a community site, not a place to promote yourself, or your projects. It’s a place to try out ideas, get feedback or buy-in, to initiate collaboration.

    * You’re still on your own for community, this is not something I want to be involved in at this time. But I do want to share ideas. In fact I have an RFC I plan to write myself, for a feature that I’m not ready yet to release because I want to hear what people think first.

    * But please before you post anything there, [read the readme](https://github.com/scripting/drummerRFC/blob/main/README.md). It’s important.

  * Drummer and Gatsby

    * [Scott Hanson](http://oldschool.scripting.com/ScottHansonDE/2021/10/21/100522.html?title=connectingDrummerToGatsby) has Drummer hooked up to Gatsby.

    * I love this. Scott has been an incredible contributor to Drummer since we started testing in August.

    * He picked up work done by Andrew Shell, who was the first user, after myself – and wrote the core code in the preprocessor for JavaSxript.

    * Combined, they made Drummer work with Gatsby.

    * All because we deliberately made that possible by using an open format, OPML.

    * Here’s the real punchline. I’ve never used Gatsby, yet my product works with it.

    * As they say…

    * *Bing\!*

  * Docs pages look better on tablets

    * I made minor changes to the CSS.

    * Previously the navigation block was too close to the text block.

    * Added another 10 pixels between them.

    * Also use 98% of the page space instead of 65%.

    * [Example](http://docserver.scripting.com/drummer/outliner.opml).

* October 20

  * New section of Blogging docs

    * [Head-level attributes Old School looks for](http://docserver.scripting.com/drummer/blogging.opml#1634760877000).

  * Links to new docs

    * Two new sections in the Electric Drummer page.

      * [The Mac will make you jump through hoops](http://docserver.scripting.com/drummer/electricDrummer.opml#1634739263000).

      * [Doesn’t Electron suck](http://docserver.scripting.com/drummer/electricDrummer.opml#1634740239000)?

    * I changed the name of the [General page](http://docserver.scripting.com/drummer/general.opml) to FAQs.

    * Many of the docs I’m grabbing from the Change notes outline are going into that (new) page.

    * Everything on this page is rough, needs a review, which I plan to do when I get a fresh perspective.

    * BTW, the one feature you all may not know about is Drag and Drop outlines in Drummer. I added it to the [Files](http://docserver.scripting.com/drummer/files.opml#1634743285000) page. There’s a [video demo](https://www.youtube.com/watch?v=FKM65EL6abo).

    * I have one more big item on my docs list for today – documenting the head-level atts for blogging.

  * Lots of docs changes coming

    * Yesterday I built a list of change notes that are really docs.

    * This morning I’m going to add them to the existing docs, and I’ll post links here.

    * What you should expect, esp if you came on board after Drummer was released, is a bunch of features that are new to you.

  * Some people write great reports…

    * Other people, maybe not so great. 😀

    * When I read some reports, I want to ask “What did you mean by that?”

    * Because it isn’t at all apparent to me what you did, or what you expected to happen.

    * Sometimes people use a word that means something updated, when you meant it didn’t appear at all. These distinctions matter a lot – when trying to figure out what went wrong, if the software did something incorrect, if the user did, or if there was a misunderstanding about what the software was supposed to do.

    * So here’s a request of the people who write great bug reports – when you see something that’s fuzzy or unclear, please pitch in and help out, and ask the other person to clarify what they mean.

    * In general I think people who write great bug reports know that they do. One way to tell is if I was able to quickly fix a problem you reported without asking any questions. Those are the best. We all win. You get software that does what you want, and I get to fix a problem in the software, that’s not going to go away until it is dealt with.

  * Fixed problem with urlBlogWebsite head-level att in DrummerCms

    * Jack [reported](https://github.com/scripting/drummerSupport/issues/67#issuecomment-947634406) a problem with urlBlogWebsite, that the change wouldn’t be reflected in the rendered blog.

    * On investigating I found DrummerCms was only passing the value through when the user’s config record was being created, which is the first time they built their blog after DrummerCms rebooted. That’s why rebooting cleared the problem, temporarily. I fixed it, and also fixed the same problem with the timeZoneOffset value.

    * This is a result of a frantic pace of feature-adding and bug fixing. Normally I’m more careful. Sorry for the problem, and Jack thanks for the very good report. It pointed me right to the problem.

  * File/Open list bug fixed

    * Scott [reported](https://github.com/scripting/drummerSupport/issues/89) a bug, quickly verified, fixed.

    * The problem was that when we closed a tab, the internal array of tabs wasn’t being automatically rebuilt.

    * So when you opened a file after closing a file, that file would still be in the tabs array, and therefore wasn’t included in the list.

    * The problem was solved by recomputing the array after closing a tab.

* October 19

  * Radio 3 bookmarklet

    * There’s an updated version of the Radio3 bookmarklet [here](http://this.how/radio3/#1511448661000).

    * Thanks to Jack Baty, Frank Meeuwsen for their help sorting this out.

    * If you have questions or comments, please post them [here](https://github.com/scripting/drummerSupport/issues/71).

  * Going back through the change notes

    * I’ve been reading the Change Notes archive

    * So far I’ve read the October and September notes.

      * [October](http://scripting.com/drummer/blog/2021/10/).

      * [September](http://scripting.com/drummer/blog/2021/09/).

    * I’m looking for docs I posted here that have not made it into the official docs, and I’m finding quite a lot. I expected to. I had this on my todo list for a long time.

    * I recommend it, esp if you came in after the test period. You’ll probably find some unexplored corners of the product.

  * Are you using micro.blog with Drummer?

    * Can you share a link to a Drummer-authored micro.blog?

    * I started a [thread](https://github.com/scripting/drummerSupport/issues/84).

* October 18

  * Micro.blog and Drummer

    * [12-minute podcast](http://scripting.com/2021/10/18/microblogAndDrummerFTW.m4a) about this fantastic new connection.

    * Here’s the [initial post](http://scripting.com/2021/04/03/133021.html?title=theMakingOfDrummer) I mentioned in the podcast.

    * Just before Drummer shipped I sent an email to Manton Reece, the developer and runner of micro.blog, asking if he was interested in being the first blogging system to hook up with Drummer via the OPML bridge. The same interface we use in Drummer to connect to Old School.

    * [Well here it is](https://www.manton.org/2021/10/18/drummer-and-microblog.html). He works fast. ;-)

    * Just watched the video – I *love* how he did it. Beautiful.

  * Docs work

    * I’m going to spend the rest of the day planning another pass over the docs.

    * I want to make it easier for me to move stuff from the Change Notes outline to the docs.

    * Right now imho it’s too hard to find things. I want to improve that too.

    * I watched Anton try to help someone find the docs for the header image att. That should be both memorable and quick, and it’s neither of those things at this point.

    * I very much consider docs an integral part of this product, not an afterthought. We’re going to make the docs better and better, just as we do with the software.

  * Workflow for images

    * There was a discussion about workflow for images in web Drummer yesterday, and it got me thinking of how it should work, and I think I figured it out, at least for people who have Amazon accounts and know how to set up an S3 location. It’s a good skill to have, and I wish Amazon made it easier, it shouldn’t be anywhere near as hard as it is, esp if all you want to do is store small images there. But as they say it is what it is.

    * There are other answers possible, but mine is to use the [PublicFolder](http://this.how/publicFolder/) app. I checked and it has a HTTP server built in, and therefore a simple interface can be created through a Drummer script, to get the last image you published and put it on the bar cursor headline as an image attribute.

    * This is how I do it on Electric Drummer except the PublicFolder functionality is baked in. There is a note in the blogging how to about how to set it up. It’s only complicated because Amazon makes it so. Sorry.

    * Anyway, the bridge between PublicFolder and Drummer is not built yet. I have a bit of work to do to get PF current with the latest Electron stuff. But it’s definitely on my todo list.

  * Changed prompt for the Edit OPML Headers command

    * It now includes the name of file whose head-level atts you’re editing.

    * [Screen shot](http://scripting.com/images/2021/10/18/headAttDialogPrompt.png).

  * Fixed problem for HTTPS users

    * There was a problem in how the default template worked for people who were using HTTPS for their blog. It’s a long story, but it meant that they couldn’t use the About panel, and I want you all to use them, so when I read your blog I have an idea who’s speaking. ;-)

    * I fixed the problem by making Old School read the outline pointed to by urlAboutOpml.

    * And the outline is baked into the home page of the site, via a macro called \[%aboutOutline%\].

    * If you’ve created a custom version of the template, you’ll need to add a bit of code to it.

    * More details in this [comment](https://github.com/scripting/drummerSupport/issues/78#issuecomment-945941809) on the thread for HTTPS support.

* October 17

  * Style note – singular items before titled items

    * On Scripting News I always put the singular items ahead of the titled items.

    * It’s hard on the readers if you don’t do it this way, because the singular items that follow a titled item appear to be part of the titled item. The delineation isn’t easy to spot. It’s possible that there’s a visual way to keep them sorted out, but I don’t know what it is. So I put all the singular items first.

    * Here’s an [example](http://scripting.com/2021/10/15.html).

  * Style note – links in blog post titles

    * I see people including links in the titles of their posts.

    * In general this isn’t done on the web. Not sure why, but it’s jarring to see a post that links from the title.

    * Here’s an [example](https://cannabiscto.com/2021/10/17/213921.html?title=theStoreHasAPresenceOnGoogleMyBusiness).

  * Starting a new doc

    * [General tips](http://drummer.scripting.com/davewiner/drummer/general.opml).

    * This is for topics that are not specific to outlining, scripting, etc.

    * First item is going to be about backing up\!

    * I’m also thinking of making that the first item on the [About page](http://docserver.scripting.com/drummer/about.opml).

  * A tab-related problem

    * Scott Hanson [reports](https://github.com/scripting/drummerSupport/issues/82) on a problem that was reported last night by Alex Johnstone.

    * And a [similar issue](https://github.com/scripting/drummerSupport/issues/38#issuecomment-945090274) reported this morning by @ambiprospect. (No name on his profile page.)

    * The must be a reason these are all showing up now, but I can’t think of why. Maybe when we figure out what it is, it’ll be apparent. But there have been zero changes in anything core in Drummer in the last week. I consider the software stable, so I don’t want to screw around with that, esp when the rollout is going so well.

    * Reproducible steps are going to be the key to solving this. I will be taking a look at the source code based on the reports and seeing if that helps to understand where there might be a problem.

    * We’ve had problems like this with Drummer in development.

  * Reproducible steps

    * When we catch a problem in the software, before we can fix it we need to be able to reproduce it.

    * We’re looking at what might be a serious problem in the tabs in Drummer, I’ll have more on it shortly, but in this case as in all serious testing work, the reproducible steps are the only way you can get a problem fixed with any certainty.

* October 16

  * Fixed bug in timeZoneOffset implementation

    * If it’s a negative offset, like -8.5, subtract the fraction of the hour instead of adding it.

    * The timeZoneOffset number grows more negative, in other words.

  * Fixed bug when opening instant outline

    * Fixed, so that the lightning bolt icon appears when you open the file via the Open URL command.

    * Previously you’d get a globe icon, which would be corrected when you reloaded.

  * Home page for oldschool.scripting.com

    * There was no index page for the site. I put a [placeholder](http://oldschool.scripting.com/) there.

  * HTTPS project is rolling

    * Thanks to [Trevor Manternach](https://github.com/tmanternach) for taking the lead.

    * A bunch of the other smart techies are working with him.

    * I love to see this kind of cooperative development.

    * And I’ve been able to just watch, that’s the best part. 😀

    * Here’s the [thread](https://github.com/scripting/drummerSupport/issues/78).

    * And here’s Trevor’s [blog](https://trevormanternach.com/).

  * Whoa

    * I just lost my first two change notes for the morning. How did that happen? Oy.

    * Replaced the one about HTTPS, above.

    * The other said I’m deleting requests for help that don’t have any information other than something they did didn’t work the way they thought it should. No one has the time to coax the relevant info out of the person. If you want help, you have a basic responsibility to respect the person you’re asking for help from.

    * Also noted that a lot of times the problem is web caching. Learn how to get your browser to do a hard reload. Always try that first. Once you have that mastered, it’s amazing how much time you’ll save.

    * Postscript. I didn’t lose them. I put them in the wrong outline. Operator malfunction.

* October 15

  * Sharing links into Drummer outlines

    * “The link opens an outline in Drummer.”

    * You may have noticed me saying this in the last few days.

    * Now I’m going to show you how to do it yourself.

    * There’s a new command in the DW menu, which is explained in the [Scripting howto](http://docserver.scripting.com/drummer/scripting.opml#1627745102000).

    * The command is in the Utilities sub-menu of the DW menu.

    * How it works.

      * Put the bar cursor on any headline in a public outline.

      * Choose the *I/O Permalink* command in the Utilities sub-menu of the DW menu.

      * It confirms you want to create a public link to the bar cursor headline.

      * Drummer opens with that outline open with the bar cursor on the headline.

    * You can share that URL with others. Try it yourself.

      * Copy the URL from the browser’s address bar.

      * Close the Drummer tab.

      * Paste the URL in the browser’s address bar. Press Return.

      * Drummer should open with the outline open and the cursor on the headline.

    * If you have questions, comments or want to see the source code, [go here](https://github.com/scripting/drummerSupport/issues/75).

  * HTTPS

    * It’s totally okay if you want to have an HTTPS gateway to your Drummer blog.

    * There is an HTTPS address for the S3 bucket containing the rendered blogs:

      * https://s3.amazonaws.com/oldschool.scripting.com/

    * Give it a try. Let us know if it works\! :-)

    * Update: Trevor Manternach [posted](https://github.com/scripting/drummerSupport/issues/78) an HTTPS howto.

  * Permalinks and the docs

    * I’m sure you’ve noticed that permalinks didn’t work reliably in the Drummer docs.

    * I want to revisit how the outlines are rendered, I want much less of it to happen every time the page is accessed.

    * In the meantime, I’ve found that if I turn off the glossary for these files, permalinks do work.

    * Here’s an [example](http://docserver.scripting.com/drummer/scripting.opml#1628514152000). It should take you The iconbar section of the Scripting howto.

    * I also don’t like the menu on the side. I might change it to work like the [opml.org](http://opml.org/) site.

  * Quotes in file titles

    * A long-time bug – if a file title has a single-quote character, the display of the tab title will be screwed up. I’ve seen this before and tried to fix it unsuccessfully in August. I took another stab at it today, and it appears to be fixed on my machine.

    * There’s a [thread](https://github.com/scripting/drummerSupport/issues/74#issuecomment-944429247) on this – if you’ve seen the problem and it’s now either fixed or not, please report. Thanks.

    * I bumped the version to 2.0.10.

  * Another support request

    * If I help you get a problem solved, please…

      * Let me know if it worked. I’m going to keep thinking it might be a problem, esp for others, until I hear back from you that it cured your problem. I’m not just helping you to help you, it’s to help others too.

      * Pay it back. If I helped you solve the problem, then when someone else pops up with the same problem, help them. It’s how we build a community here. Otherwise it just burns itself out.

  * I only work about four to five hours a day

    * I’ve got a routine. Right now all my time is being spent helping people with urgent matters, but the thing is, most of them are not actually urgent.

    * This week is unusual. Next week I’d like to spend most of my working time fixing problems and moving forward with the software.

    * What can’t change is the amount of time I work each day. I used to be willing to push it way too far, and that got me sick. I just can’t do that anymore.

    * So try to be aware of that, right now I am the support for this product. No one else can do it. People are trying to pitch in and that’s much appreciated.

    * It’s got to settle down, a bunch. If you feel exhausted and upset, then slow down, take a breath, we tend to get very urgent as we do our web thing. That’s not a way to relate in a community like this. Go for a walk or a whatever you to do to relax, then take another look at the problem. It often happens that by the time you get back you’ve figured out what the problem is. If not, then carefully write up what you did, what you expected to happen, etc.

  * When you post a request for help…

    * A common mistake is to assume the person reading the request is there with you.

    * You have to give us some basic information.

    * If it’s about your blog, what’s the address of your blog.opml file.

    * How can we guess how the CMS is dealing with your blog if we don’t know what you sent to it?

    * Common sense. Empathy. And if you really want help you have to think about what info someone is going to need to help you.

    * More [here](http://scripting.com/2020/12/12/165429.html?title=howToAskForHelpWithSoftware). And [here](http://scripting.com/2014/03/19/howToAskForHelpWithSoftware.html).

    * And here’s a [bit](http://scripting.com/2014/09/21/theLostArtOfSoftwareTesting.html) about the lost art of software testing.

* October 14

  * Changing PagePark advice

    * In the [section](http://docserver.scripting.com/drummer/blogging.opml#1628776787000) of the Blogging howto where we discuss how to use [PagePark](http://pagepark.io/) to create a custom URL for your Drummer blog, I changed the recommendation for how to do it. The new way does not require a complex setup of Amazon credentials.

  * A working R3 bookmarklet?

    * Jack Baty has posted a Radio3 bookmarklet written by John Johnston that supposedly works. Somewhere along the line, the one on the Radio3 site broke? As Jack says it’s been hard for me to respond to all the fires that have been burning, but I’m really glad these guys did.

    * [Here’s the link](https://github.com/scripting/drummerSupport/issues/71). If the consensus is that it works, I’ll update the Radio3 site.

    * Thanks\! I totally appreciate the help. 😀

  * New head-level attribute – timeZoneOffset

    * There’s a new [section](http://docserver.scripting.com/drummer/blogging.opml#1634213853000) in the Blogging howto, about getting the time zone of your blog right.

    * Thanks to Amit and Scott for their help testing this feature.

    * If you have questions, this is [where](https://github.com/scripting/drummerSupport/issues/64) you go.

  * New server code releases

    * New versions of [oldSchoolBlog](https://github.com/scripting/oldSchoolBlog) and [drummerCms](https://github.com/scripting/drummerCms).

  * Drummer is a scripting system

    * The focus has been on Drummer as a blogging tool, and I couldn’t be happier with the response. I think we have gotten the initial glitches taken care of, and now I can step back and take a deep breath and start to think about what’s next.

    * In the meantime, if you’re a script person, and I think a bunch of you are, have a look at the [scripting howto](http://docserver.scripting.com/drummer/scripting.opml).

    * I have an interesting new script I want to share with you, in the morning.

    * In the meantime as a former Californian and a baseball fan since childhood, I have a game to watch tonight. And of course I’m rooting for the Giants.

  * Thanks\!

    * I don’t know where all you lovely people came from.

    * Were you always there?

    * In any case, please stick with Drummer, we’re just getting started. ❤️

* October 13

  * Custom URL for your Drummer blog

    * There are a number of people who want to use Drummer to host a blog using their own domain.

    * The instructions on the [blogging page](http://docserver.scripting.com/drummer/blogging.opml#1628776787000) only worked for the home page, the subordinate page links would still point to oldschool.scripting.com.

    * I thought we’d have to use custom installs of drummerCms to solve the problem, but along the way I found a simpler approach which I have implemented.

    * Basically the instructions on the Blogging page now work, with an additional step.

    * There’s a new head-level attribute called urlBlogWebsite, which tells drummerCms where the links should point.

    * It works. I’ve set it up for clueless.lucky.wtf. Click around. The links all stay within the domain.

    * Now, you still need a server, and need to set up PagePark. But this is a lot easier than setting up drummerCms.

    * Please [let me know](https://github.com/scripting/drummerSupport/issues/67) if it works or you have problems.

  * Why we use Twitter identity

    * I made this a [blog post](http://scripting.com/2021/10/13/140500.html?title=whyWeUseTwitterIdentiy).

  * If something isn’t working

    * And you can’t figure out what went wrong…

    * Two things to try that you might not thought of..

      * Hard reload the app

      * Open the JavaScript console and see if there are any error messages.

    * When you think the software isn’t working, that’s the problem, if there were error messages in the console, try to include them in your report.

  * Security questions for Electric Drummer

    * When you launch E/D for the first time, you are told the author of the program can’t be verified and the Mac will refuse to launch it. Hope is not lost\!

    * Open the System Preferences app.

    * Click on the Security & Privacy button.

    * At the bottom of the display you’ll see an option to load the app anyway.

    * That’s the thing to do.

    * People have noted that the mod date is in 2020, that’s because that’s the mod date of the Electron package. I can probably fix that, and will attempt to do so.

    * People have noted that the app is big. Yes it is. That’s because there’s a full browser and Node stack in the package. Drummer itself is quite small. This is the way it works in 2021. You have to bring the browser and operating system with you on trips to the Mac.

    * Luckily today’s machines have *lots* of memory\!

    * And Drummer is nice and fast.

  * Dark mode

    * Frequently asked question about Dark Mode.

    * How to turn back to light mode?

    * Reload.

    * This even works in Electric Drummer.

    * All the way at the top of the screen, there’s a menu Window menu, with a Reload command.

    * It has the same effect.

* October 12

  * Update on blogging on your own domain

    * I’ve reviewed the code in drummerCms, and I’m 99 percent sure we’ll be able to set it up so you can run your own CMS and put the pages in your own S3 bucket. I think that’ll probably be ready tomorrow, knock wood, praise murphy.

    * You will have to run a server to get that feature though. But there will be no programming involved.

  * Drummer’s key scripting innovation

    * There’s a huge innovation in the JavaScript runtime in Drummer.

    * I wrote up an example illustrating the new thing in [a blog post](http://scripting.com/2021/03/24/161331.html?title=drummersKeyInnovation).

  * How to set up a Unix system for Node apps that write to S3

    * Some Drummer users are trying to get [drummerCms](https://github.com/scripting/drummerCms) to work on their servers, so they can publish to a custom domain. To do so you have to set up your system so that Node apps can read and write to S3 via Amazon’s API.

    * I’ve been telling people to [follow Amazons directions](https://docs.aws.amazon.com/ses/latest/DeveloperGuide/create-shared-credentials-file.html). I just reviewed them and they seem pretty straightforward. But they could be a tiny bit easier, so I wrote these instructions.

      * At the command line type this:

        * cd \~/.aws

        * nano credentials

      * Paste [this text](https://gist.github.com/scripting/054e8430d870f85438208635bf6fc05a), replacing the dummy values with the ones from your AWS account:

        * \[default\]  
aws\_access\_key\_id=tz4nhbttfvll76gb9ej7  
aws\_secret\_access\_key=cedx5jixadnwca1e3fnopkg8ji6cvynx4nlhgpy8

      * Type this:

        * Control-O

        * Return

        * Control-X

      * Make sure the file was correctly created.

        * cat credentials

    * Having done all that, the app that tried to write to S3 should now be able to do it without error.

  * The Drummer blog

    * Want to be sure you all know about the [Drummer blog](http://scripting.com/drummer/blog/).

    * It has an RSS feed, of course, and you can subscribe to it in your favorite reader.

    * The thing I want to point out is that the blog and the Change Notes outline are the same thing. The text you’re reading also appears [on the blog](http://scripting.com/drummer/blog/2021/10/12/123333.html?title=theDrummerBlog). It’s kind of a unified field theory of writing for the web. It’s all outlines, from top to bottom. And imho that’s as it should be. 😀

    * I think there are very strong advantages to subscribing to the outline in an outliner, that we’re just beginning to explore this communication medium. We used it in the early 2000s at UserLand, with the right team, it really works.

    * If you want to get an idea of what I/O is about, I recommend this [2009 piece](https://bhc3.com/2009/01/16/before-there-was-twitter-there-was-dave-winers-instant-outliner/) by Hutch Carpenter.

* October 11

  * We can now handle users whose names begin with underscores

  * It’s really easy to back up

    * So you should do it *now* and do it often\!

    * Here’s what you have to do

      * 1\. Choose *Download my files* from the Tools menu.

    * That’s it. It downloads a zip archive of all your files on the server, separated into two folders, one for private files, the other for public files.

    * You should do it before and after every work session.

  * The launch is a success

    * Unqualified, absolutely great response. Everyone seems to love Drummer.

    * Here’s the number, there have been 950 page loads of drummer.scripting.com on Monday.

    * That’s like saying your app was launched 950 times. That’s fantastic. I would be happy if that’s as large as the user base ever got. Because we can go somewhere with these users. And that’s what I wanted.

    * ![](http://static.scripting.com/larryKing/images/2014/03/13/curly.gif)

  * We’re getting technical users

    * Yippee\! I am so happy that we’re getting people using Drummer who know how to run servers.

    * This could make a bunch of things possible.

    * Stay tuned…

  * Server restarted at 3PM

    * I had to restart the server just now to make a configuration change.

  * New Twitter account – @drummeroutliner

    * I edited the old @littleoutliner account, changed its name, images.

      * <https://twitter.com/drummeroutliner>

    * They aren’t as clever as GitHub, the old account doesn’t redirect.

    * I guess someone else could grab littleoutliner. Oy\!

  * Twitter and Facebook metadata

    * A detail that slipped through the cracks, the Twitter and Facebook metadata in the Drummer home page still were about Little Outliner. So I took a new screen shot, and fixed up the links and description. And went ahead and linked to Drummer on both Twitter and Facebook. It had already been discussed on Twitter, but not linked to.

  * PagePark builds again

    * I was working with a [user](https://github.com/scripting/drummerSupport/issues/30#issuecomment-940060491) last night who wanted to use PagePark to provide his own domain name for his Drummer blog. This is very much a supported and recommended thing to do.

    * However, when he installed and ran PagePark it failed. On further investigation it broke due to the dateformat change I [documented](http://scripting.com/2021/09/29/133747.html?title=theDateformatModule) on Scripting News, that same one that took down the [oldSchoolBlog](https://www.npmjs.com/package/oldschoolblog) package.

    * I did a quick survey of all my code, I use dateformat everywhere. This is a first class mess.

      * What’s even more interesting is that he had the problem on Glitch, where I don’t believe they give you the option of what version of Node to install. If that’s true then dateformat broke Glitch too.

    * In any case – for today – I just updated the two bits of code that PagePark uses that broke, they are [daverss](https://www.npmjs.com/package/daverss) and [githubpub](https://www.npmjs.com/package/githubpub). I fixed them, published the new versions to NPM, updated my local test PagePark install and it boots up. Problem solved. So now we can proceed with the coolness of getting a $5 a month server to front for this user’s Drummer blog.

  * Good morning\! 😀

    * For all the newbies, welcome to the Change Notes outline for Drummer.

    * This is where I (Dave) report on new features and fixes in Drummer and related projects.

    * Today, I want to invite new Drummer users to say hi, and let us know what you think, and ask whatever questions you may have. Not promising we’ll have answers for all of them, but we’ll try.

    * This is the [place](https://github.com/scripting/drummerSupport/issues/57) for those notes/questions.

* October 10

  * The deed is done, 1PM Eastern

    * ![](http://scripting.com/images/2021/10/10/inlineImage.png)

  * Bumped version to 2.0.9

    * Four more things to do

      * Build the Electric Drummer release.

      * Flip the repo, make it public, and change its name to [Drummer Support](https://github.com/scripting/drummerSupport).

        * The links are not broken – GitHub did a nice thing, they redirect from the old URLs to the new ones.

        * Never mind.

      * Edit the readme on the Support site.

        * I’m sure there are things I missed, changing it from private to public.

      * Post a link to drummer.scripting.com on scripting.com.

  * Ideas for getting to the next level of user docs

    * I write docs in the change notes (see below), figuring at some point I’ll go through the outline and pick out things that are not in the published docs.

    * But I know I’ve missed a lot.

    * This is another kind of review we could do together, and in doing so create a new level of thoroughness in software docs.

    * I also think we should do the index-in-the-back-of-the-book type thing for these docs, by hand, to get the experience.

  * Changed where Drummer redirects to

    * I know it’s confusing that when you open a second instance of Drummer (web) it redirects the previous instance, in the background, to scripting.com. At the time, I didn’t have any other obvious choice of where to redirect to, and the browser won’t let me close the tab (that would be the obvious choice).

    * After Anton’s report, I gave it some thought and decided a better place to redirect to is the new [About page](http://docserver.scripting.com/drummer/about.opml). I thought about creating a special page just for this purpose but couldn’t figure out how to explain it to someone who will probably have no clue they did what they did. It does this to protect you from having two versions of outlines conflicting with each other.

    * There are other ways to deal with it, I’ve since learned, but at this stage can’t do anything more complicated that what I’ve done here.

  * The change notes outline is a blog too

    * BTW –

    * The change notes outline is also a blog.

      * <http://scripting.com/drummer/blog/>

    * Which you can subscribe to in your favorite RSS reader.

      * [http://scripting.com/drummer/blog/rss.xml](http://xmlviewer.scripting.com/?url=http://scripting.com/drummer/blog/rss.xml)

  * The page is flipped

    * Tomorrow is a new project. Not even sure which one it’ll be.

    * Probably still sweeping up after today’s show.

    * Feels good to have turned the corner.

    * Drummer really is a better way to blog.

    * Still diggin\!

* October 9

  * Podcast

    * I recorded a [24 minute podcast](http://scripting.com/2021/10/09/updateForDrummerUsers.m4a) about what’s going on.

    * It’s a quiet period as I get ready to flip the switch from private to public. Taking notes on changes, but not publishing them now, rather I’ll post them all here at once when it’s time to open up.

    * I talk about some of those changes in the podcast.

    * Still diggin\!

    * ![](http://scripting.com/images/2017/09/11/mrNatural.png)

    * PS: I considered how we did the [online docs](http://scripting.com/frontier/beginning/whatFrontierIs.html) for Frontier when organizing Drummer’s.

    * PPS: If you have a question, I started a [thread](https://github.com/scripting/drummerTesting/issues/54) in the repo for that.

* October 7

  * Sunday is the day

    * Since Sunday is the 27th anniversary of blogging at scripting.com (or anywhere, for that matter), let’s make that the day that the doors officially open for Drummer. There will still be things to do at that point, and that’s ok. As they say software is a process.

    * I’ve written about this on my blog, of course. 😀

* October 6

  * Changes in Electric Drummer (will be available when new E/D is released)

    * When you double-click on a Twitter node, the tweet opens in an external browser window, not one inside the Electron environment.

    * Docs menu commands now open the docs pages in external browser windows in E/D.

      * I changed the [webBrowser.openUrl](http://docserver.scripting.com/?verb=webBrowser.openUrl) verb to do this in all cases.

  * Change notes archives updated

    * Archived September changes, turned the headline in the Change Notes outline to an include node.

    * The file went from 91K to 11.2K.

    * I uploaded the Markdown versions of [August](https://github.com/scripting/drummerTesting/blob/main/notes/2021/08.md) and [September](https://github.com/scripting/drummerTesting/blob/main/notes/2021/09.md) to the Drummer testing repo. I find it’s valuable to read them in this format too, I remember ideas I noted but haven’t acted on yet. If you want to continue to help testing, you might get ideas of things to look at by reading through these files.

    * I added include nodes for: February, March, April, May, June, July (all of July, not just the 31st)

    * Also added the OPML source files to the [GitHub repo](https://github.com/scripting/drummerTesting/tree/main/notes/2021), as part of the record.

* October 5

  * Please keep testing and using

    * Please keep using Drummer and reporting problems.

    * Report things that fail. I’m not concerned so much about esthetic glitches or long-term problems we can work around, rather things that used to work that don’t work now. This is called “regression testing.” Did something we do cause the product to regress?

    * You won’t see many coding updates here until we go public with Drummer.

    * I am working, steadily and methodically (I hope) but not taking chances on breaking things.

    * I want a product that’s at least as stable as LO2, which has proven to be very stable.

    * The time to flip the switch is soon. Please find the problems now if you can, they may be harder to deal with later.

    * Thanks\!

* October 3

  * Note to testers

    * Drummer feels stable.

    * Can we verify that?

    * What to do to test…

      * Hoist in one of your tabs.

      * Try opening another file.

      * Switch back and forth between tabs.

      * Did the outline you opened get overwritten?

        * This is something that used to happen.

      * Keep the change notes outline (this list) open.

      * When it updates do other outlines get trashed?

        * This used to happen too.

      * To really test it, don’t have the change notes be the front tab.

        * Let it update in the background.

      * Basically, really mix it up, be creative, do things you don’t usually do

      * It’ll be a PITA to find out there are big problems later.

      * Now is the time.

  * More on keyboard customization

    * With Scott Hanson. I just posted a [summary](https://github.com/scripting/drummerTesting/issues/49#issuecomment-932965824) of how Drummer configures the keyboard internally. It probably would be pretty straightforward to give this ability to Drummer users, esp since Drummer has a scripting capability and you can have code run at startup.

* October 2

  * New Electric Drummer release

    * Last E/D release was on September 23, there have been a bunch of fixes since then.

    * The version number displayed in the upper right corner is now meaningful, it’s the same version as the web drummer, so today that number is 2.0.8.

    * Fixes in this release include all the hoisting fixes, keyboard commands for Find and Find Again (cmd-f and cmd-g).

    * Download from the link on the [Electric Drummer download](http://docserver.scripting.com/drummer/electricDrummer.opml) page.

  * Radio3 change and Drummer blogs

    * Anton reported a problem with the Links page on his Drummer blog, and on the Links page on Scripting News.

    * I believe I have fixed the problem in both places, by making a change in Radio3. Rather than having the blogs do the rendering of the HTML for the linkblog, I have Radio3 do it. It’s a better distribution of labor, and it was easier to work in Radio3 than in the blog rendering code.

    * The new version of Radio3 is 0.7.15.

    * Here’s how to update your linkblog so the new code will find the rendered HTML.

      * Either post a link to your linkblog, or edit a link and repost it. The link doesn’t have to change, it just needs to force a rebuild of all the Radio3 files which will now include the HTML rendering. If it works, say on Anton’s blog, [this link](http://twitter.radio3.io/users/mistersugar/linkblog.html) will work. At that point, when you reload Anton’s blog, its [links page](http://oldschool.scripting.com/mistersugar/?tab=links) will no longer be blank (as it was after I made this change).

    * Let’s keep a lookout on the Links page to make sure it keeps working. This is very old and strange code written mostly in 2014, when I didn’t understand JS as well as I do today, so it can be a bit flaky as we just found out.

  * Blogging docs page

    * I added [sections](http://docserver.scripting.com/drummer/blogging.opml#1633177803000) about creating Links and About pages to the Drummer blog.

* October 1

  * Linkblog page on Drummer blogs

    * Anton [reports](https://github.com/scripting/drummerTesting/issues/35#issuecomment-931829468) a problem with the linkblog page on Drummer blogs, and observes that the same problem is appearing on the Scripting News home page.

    * I verified that there is a problem there. And I got to work on moving the code that Radio3 uses to render the blog, into Scripting News, and now it works there too. I’m going to let it burn in for a bit to be sure it’s working there, before porting the change into Drummer.

# September 2021

# August 2021

# July 2021

# June 2021

# May 2021

# April 2021

# March 2021

# February 2021
