---
# layout: post
title: "A new theme and performance added to the blog"
date: 2014-08-22 23:42
comments: true
categories: [techonology, octopress, theme]
published: true
---
This week I started looking at how to modify or replace the "classic" theme that comes off-the-shelf with Octopress. I was positively surprised when I found the glorious [3rd party Octopress themes](https://github.com/imathis/octopress/wiki/3rd-Party-Octopress-Themes). I took the time to check most of them and it was great to see a consistent high-quality around most of them. Also, how easy it was to add them into the blog. On top of that, I added a few experimental performance settings to speed up the blog using the limited free infrastructure. Read on to get more details.
<!--more-->

The theme that I liked the most (which is the one that you are looking at right now) is called [MediumFox](http://https://github.com/sevenadrian/MediumFox), created by Adrian Artiles. It is inspired on the design of Medium and FoxSlide.

Besides being fully responsive, it contains really nice visual design: from the picture to the font, as well as the top bio which is a great way to present the blog to new visitors.

When installing Octopress themes I recommend that you install them using git submodules, this way every time you deploy the blog to your server, it will pull the latest changes to the theme by free which is really good.

Another improvement that I added to the blog, was changing the default ruby web server that octopress uses locally which is the same that Heroku uses when deployment-called WEBrick.

After installing the theme I received a console message from Heroku advising changing the web server to [Unicorn](http://unicorn.bogomips.org/). The interesting part about unicorn is the fact that using a single Dyno (heroku's processor), with Unicorn you can have up to 4 workers in pararell in comparison with a single worker that WEBrick offers. Heroku has some really nice instructions about how to add unicorn to your Ruby application [here](https://devcenter.heroku.com/articles/rails-unicorn)

Although the blog didn't have any performance issues that I'm aware off, this I consider it my personal playground and I'll continue adding things as I'm learning about them.
