---
# layout: post
title: "Blogging Like a Hacker"
date: 2013-08-30 13:30
comments: true
categories: [technology]
published: true
---
My old blogs used well known blogging engines: blogger and MovableType. For years blogger has been able to keep up with trends - in my opinion always catching up. However, I didn't want to simply create a new blog on blogger; something was just not right.

One day a technical blog cought my attention because of its look and feel and nice calligraphy. It was [Octopress](http://octopress.org/) which was created under the premise that is a blogging framework for hackers.

So, what does it really mean? Let me give you more context info:
<!--more-->
I come from the Java EE world - so IDEs, frameworks, installing application servers, compiling and running - are all very well known to me. However when I joined [Moovweb](http://moovweb.com) I realized something that I had been seeing for a while: the new companies are not sold by Java or .Net anymore.

In other words, outside of the traditional corporate world developers don't talk anymore about enterprise EJBs, Controllers or JSF, and instead the dictionary words sound something like Go, JavaScript, Ruby, HTML 5, CSS3, Sass, Bootstrap, Angular, etc....

The new era of enterprise software is already here and it is rapidly taking over the traditional way that, not too long ago for some of us, were the latest trends in programming: objects oriented, MVC, JSPs (specially) .... and I thought that at that point I knew it all.

So how all of the above connects with blogging? Well, I just told you about my developer journey and where I'm right now so, the following is my new workflow journey for blogging:

* Bought a domain so my blog was easy to remember/access.
* Created a [heroku](http://heroku.com) account. Heroku allows me to host Ruby applications in the cloud. Also, it supports apps from other languages besides Ruby like Java, Node.js, Python, PHP, Clojure and, Scala.
* Created a [CloudFlare](http://cloudflare.com) account that allows me to provide CDN-type features like caching images and content, which in my case is not critical but having performance is great.
* I'm learning [Markdown](http://daringfireball.net/projects/markdown/syntax) which gets used for writing the posts. Btw it's awesome!
* I'm learning to use [GitHub](http://github.com) for source control versioning of my application code and for pushing any changes to the blog to Heroku.
* (Future) learn Sass to add customizations to the blog, [Jekyll](http://jekyllrb.com/) to add [internationalization](https://github.com/screeninteraction/jekyll-multiple-languages-plugin) and who knows where this is going to stop.... I hope never.

Do you have any suggestions on other things that I should try?
