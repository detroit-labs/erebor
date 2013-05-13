# Erebor

> This Kingdom Under the Mountain held one of the largest dwarven treasure hoards in Middle-earth.

Erebor is the Detroit Labs repository/source for custom gems: gems we create
or custom builds of 3rd party gems. The `gems` branch is a static repository
suitable for use as a RubyGems source by [Bundler](http://gembundler.com). Erebor is
a public repo; gems published here are visible to the world.

One day the dwarves of Erebor may branch out to other crafts:
[modules](https://npmjs.org),
[jars](http://search.maven.org/#browse/), or
[pods](http://cocoapods.org).

<img src="http://images.wikia.com/lotr/images/5/5d/Erebor.jpg">

## Using Erebor's Gems

Erebor is a RubyGems source, add it your project's `Gemfile`:

    source 'https://raw.github.com/detroit-labs/erebor/gems/'

## Contributing Gems to Erebor

Your gem's source should live in it's own git repo. Only the `.gem` is added to Erebor.
Build your gem the way that gems are built, then…

    cp YOUR-x.y.z.gem gems
    git add gems/YOUR-x.y.z.gem
    git checkout -m 'added YOURGEM x.y.z' gems
    git push origin master

    make sure you pull down the gems branch.
    git fetch origin && git branch gems origin/gems
    script/publish

**Reminder**: public repo, no s3kr3ts

## Why Public?

Because simple.


I started off making Erebor private. Here's what the `Gemfile` looked like:

    source "https://#{ENV['EREBOR_GITHUB_TOKEN']}:x-oauth-basic@raw.github.com/detroit-labs/erebor/gems"

Then everyone would have a one time setup to
[create an oath token](https://help.github.com/articles/creating-an-oauth-token-for-command-line-use)
and then make sure that `EREBOR_GITHUB_TOKEN` was set and how secure will it be when everyone's github oauth token is
stored in their `.bashrc`…

and then I made [detroit-labs/erebor](https://github.com/detroit-labs/erebor) a
public repo and moved on because nothing I plan on putting in it so far needs to be kept secret.

## 3rd Party Gems

First, you should get gems from [rubygems.org](http://rubygems.org). If you need an unreleased version,
then you should [get the gem from its git repo](http://gembundler.com/git.html). If you've forked a gem,
you can get them gem from your fork's git repo.

The [rugged](https://github.com/libgit2/rugged) gem [won't install via Bundler from git](https://github.com/libgit2/rugged/pull/107#issuecomment-9437471),
requiring a manual build until they release an updated version to rubygems.org.
