---
# layout: post
title: "Ruby RVMs and Mac OS X Update2 (Mavericks) Issues"
date: 2014-03-26 00:29
comments: true
categories: [technology]
---
I use [RVMs](http://rvm.io/) to run ruby applications such as this blog and @Moovweb's pre-release software built via [ruby gems](http://en.wikipedia.org/wiki/RubyGems).

A friend of mine and I are going to try to work on a Rails application, which is a good opportunity for me to understand the technology behind so many apps nowadays.

As I was getting my environment ready, I ran in some issues on a couple of computers that I had recently updated to Mavericks update 2, this is what happened. I advice that you read the end of this post first... trust me.
<!--more-->
The first symptom is when you try to install a RVM version and you get messages of this type:

	ruby-2.0.0-p247 - #installing.................................................................................................................................
	Retrieving rubygems-2.1.11
	There is no checksum for 'http://production.cf.rubygems.org/rubygems/rubygems-2.1.11.tgz' or 'rubygems-2.1.11.tgz', it's not possible to validate it.
	This could be because your RVM install's list of versions is out of date. You may want to
	update your list of rubies by running 'rvm get stable' and try again.
	If that does not resolve the issue and you wish to continue with unverified download
	add '--verify-downloads 1' after the command.

	There has been an error while trying to fetch rubygems.
	Halting the installation.

Even if you get this error, it seems that the installation was successful. Now I tried to run a rails command:

	$ rails console
	Could not find rake-10.1.1 in any of the sources
	Run `bundle install` to install missing gems.

So then I follow the instruction:

	$ bundle install

And bump into the error:

	Gem::Installer::ExtensionBuildError: ERROR: Failed to build gem native extension.

    /Users/juanca/.rvm/rubies/ruby-2.0.0-p247/bin/ruby extconf.rb
	checking for pg_config... no
	No pg_config... trying anyway. If building fails, please try again with
	 --with-pg-config=/path/to/pg_config
	checking for libpq-fe.h... no
	Can't find the 'libpq-fe.h header
	*** extconf.rb failed ***
	Could not create Makefile due to some reason, probably lack of necessary
	libraries and/or headers.  Check the mkmf.log file for more details.  You may
	need configuration options.

	Provided configuration options:
		--with-opt-dir
		--with-opt-include
		--without-opt-include=${opt-dir}/include
		--with-opt-lib
		--without-opt-lib=${opt-dir}/lib
		--with-make-prog
		--without-make-prog
		--srcdir=.
		--curdir
		--ruby=/Users/juanca/.rvm/rubies/ruby-2.0.0-p247/bin/ruby
		--with-pg
		--without-pg
		--with-pg-dir
		--without-pg-dir
		--with-pg-include
		--without-pg-include=${pg-dir}/include
		--with-pg-lib
		--without-pg-lib=${pg-dir}/
		--with-pg-config
		--without-pg-config
		--with-pg_config
		--without-pg_config


	Gem files will remain installed in /Users/juanca/.rvm/gems/ruby-2.0.0-p247@railstutorial_rails_4_0/gems/pg-0.15.1 for inspection.
	Results logged to /Users/juanca/.rvm/gems/ruby-2.0.0-p247@railstutorial_rails_4_0/gems/pg-0.15.1/ext/gem_make.out
	An error occurred while installing pg (0.15.1), and Bundler cannot continue.
	Make sure that `gem install pg -v '0.15.1'` succeeds before bundling.

So after looking around, I discover that pg stands for [postgresql](http://www.postgresql.org) so then it was suggested that I could installed using [brew](http://brew.sh). The plan of attack was to manage to install all of the above to then re-run the bundle install.

Unfortunately this attempt also failed, after running bundle install again, I got.

	Users/juanca/.rvm/rubies/ruby-2.0.0-p247/lib/ruby/2.0.0/rubygems/core_ext/kernel_require.rb:45:in `require': dlopen(/Users/juanca/.rvm/rubies/ruby-2.0.0-p247/lib/ruby/2.0.0/x86_64-darwin13.1.0/digest/sha1.bundle, 9): Library not loaded: /opt/local/lib/libssl.1.0.0.dylib (LoadError)
	Referenced from: /Users/juanca/.rvm/rubies/ruby-2.0.0-p247/lib/ruby/2.0.0/x86_64-darwin13.1.0/digest/sha1.bundle
	Reason: image not found - /Users/juanca/.rvm/rubies/ruby-2.0.0-p247/lib/ruby/2.0.0/x86_64-darwin13.1.0/digest/sha1.bundle
	from /Users/juanca/.rvm/rubies/ruby-2.0.0-p247/lib/ruby/2.0.0/rubygems/core_ext/kernel_require.rb:45:in `require'
	from /Users/juanca/.rvm/gems/ruby-2.0.0-p247@railstutorial_rails_4_0/gems/bundler-1.5.3/lib/bundler/definition.rb:1:in `<top (required)>'
	from /Users/juanca/.rvm/gems/ruby-2.0.0-p247@railstutorial_rails_4_0/gems/bundler-1.5.3/lib/bundler.rb:152:in `definition'
	from /Users/juanca/.rvm/gems/ruby-2.0.0-p247@railstutorial_rails_4_0/gems/bundler-1.5.3/lib/bundler/cli.rb:253:in `install'
	from /Users/juanca/.rvm/gems/ruby-2.0.0-p247@railstutorial_rails_4_0/gems/bundler-1.5.3/lib/bundler/vendor/thor/command.rb:27:in `run'
	from /Users/juanca/.rvm/gems/ruby-2.0.0-p247@railstutorial_rails_4_0/gems/bundler-1.5.3/lib/bundler/vendor/thor/invocation.rb:121:in `invoke_command'
	from /Users/juanca/.rvm/gems/ruby-2.0.0-p247@railstutorial_rails_4_0/gems/bundler-1.5.3/lib/bundler/vendor/thor.rb:363:in `dispatch'
	from /Users/juanca/.rvm/gems/ruby-2.0.0-p247@railstutorial_rails_4_0/gems/bundler-1.5.3/lib/bundler/vendor/thor/base.rb:440:in `start'
	from /Users/juanca/.rvm/gems/ruby-2.0.0-p247@railstutorial_rails_4_0/gems/bundler-1.5.3/lib/bundler/cli.rb:10:in `start'
	from /Users/juanca/.rvm/gems/ruby-2.0.0-p247@railstutorial_rails_4_0/gems/bundler-1.5.3/bin/bundle:20:in `block in <top (required)>'
	from /Users/juanca/.rvm/gems/ruby-2.0.0-p247@railstutorial_rails_4_0/gems/bundler-1.5.3/lib/bundler/friendly_errors.rb:5:in `with_friendly_errors'
	from /Users/juanca/.rvm/gems/ruby-2.0.0-p247@railstutorial_rails_4_0/gems/bundler-1.5.3/bin/bundle:20:in `<top (required)>'
	from /Users/juanca/.rvm/gems/ruby-2.0.0-p247@railstutorial_rails_4_0/bin/bundle:23:in `load'
	from /Users/juanca/.rvm/gems/ruby-2.0.0-p247@railstutorial_rails_4_0/bin/bundle:23:in `<main>'

This story ends bad. After my many attempts, I ended up removing all rvms from my system and then re-installing everything again. I believe that after update symbolic links got removed. If you have had a similar experience or found a better workaround please leave a comment.
