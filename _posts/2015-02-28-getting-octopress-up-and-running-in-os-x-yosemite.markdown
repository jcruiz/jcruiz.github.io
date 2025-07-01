---
# layout: post
title: "Getting Octopress Up and Running in OS X Yosemite"
date: 2015-02-28 16:07
comments: true
categories: [technology]
published: true
---

I started working on a new computer and it didn't have any of the pre-requisites to work with Octopress installed, it took me a good amount of time to get everything up an ready. In this post I explain how to get Octopress up an running on OS X Yosemite.
<!--more-->

##Installing Ruby
I was not able to install Ruby at first because Homebrew was not installing and required a separate installation. The symptoms were:

{% highlight javascript %}
curl -L https://get.rvm.io | bash -s stable --ruby
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   184  100   184    0     0    181      0  0:00:01  0:00:01 --:--:--   181
100 22817  100 22817    0     0  16792      0  0:00:01  0:00:01 --:--:-- 67706
Downloa ding https://github.com/wayneeseguin/rvm/archive/1.26.10.tar.gz
Downloading https://github.com/wayneeseguin/rvm/releases/download/1.26.10/1.26.10.tar.gz.asc
Found PGP signature at: 'https://github.com/wayneeseguin/rvm/releases/download/1.26.10/1.26.10.tar.gz.asc',
but no GPG software exists to validate it, skipping.

Upgrading the RVM installation in /Users/jz/.rvm/
    RVM PATH line found in /Users/jz/.mkshrc /Users/jz/.profile /Users/jz/.bashrc /Users/jz/.zshrc.
    RVM sourcing line found in /Users/jz/.profile /Users/jz/.bash_profile /Users/jz/.zlogin.
Upgrade of RVM in /Users/jz/.rvm/ is complete.

# Juan Camilo Ruiz,
#
#   Thank you for using RVM!
#   We sincerely hope that RVM helps to make your life easier and more enjoyable!!!
#
# ~Wayne, Michal & team.

In case of problems: http://rvm.io/help and https://twitter.com/rvm_io

Upgrade Notes:

  * No new notes to display.

rvm 1.26.10 (latest) by Wayne E. Seguin <wayneeseguin@gmail.com>, Michal Papis <mpapis@gmail.com> [https://rvm.io/]
Searching for binary rubies, this might take some time.
No binary rubies available for: osx/10.10/x86_64/ruby-2.2.0.
Continuing with compilation. Please read 'rvm help mount' to get more information on binary rubies.
Checking requirements for osx.
About to install Homebrew, press `Enter` for default installation in `/usr/local`,
type new path if you wish custom Homebrew installation (the path needs to be writable for user)
: Requirements installation failed with status: 1.
{% endhighlight %}

What gave me a more clear indication that something was missing was when I attempted to install Homebrew by itself
{% highlight javascript %}
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
ruby: no code specified for -e (RuntimeError)
{% endhighlight %}

With more digging around, I found this [post](http://stackoverflow.com/questions/22776751/installing-rvm-requirements-installation-failed-with-status-1) at StackOverflow where basically explained it was because I never executed Xcode on this machine before, so I had to manually open it one time which kicked off the installation of additional components. Onces that finished I was able to install Homebrew and I executed brew doctor

{% highlight javascript %}
brew doctor
{% endhighlight %}

After that I hit another roadblock during the installation of Ruby 1.9.3
{% highlight javascript %}
rvm install ruby 1.9.3-p551
...
checking whether we are cross compiling... configure: error: in `/Users/jz/.rvm/src/ruby-1.9.3-p551':
configure: error: cannot run C compiled programs.
If you meant to cross compile, use `--host'.
See `config.log' for more details
There has been an error while running configure. Halting the installation.
{% endhighlight %}

Found the issue again and basically I needed to install more xcode dependencies. I did it by executing
{% highlight javascript %}
xcode-select --install
{% endhighlight %}

After all of that I decided to upgrade the Ruby version used by Octopress to version 2.2.0. To do that I edit the version of ruby in the following files:

	.rbenv-version
	.ruby-version
	Gemfile

Last I got a warning about htmltags in liquid that basically can be solved by upgrading liquid to version. 2.6.2. I changed the version in the Gemfile.lock and Gemfile and executed

	bundle install
