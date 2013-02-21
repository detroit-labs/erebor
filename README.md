# Erebor

Erebor is the Detroit Labs repository/source for custom gems: gems we created or custom builds of 3rd party gems. The `gems` branch is a static repository suitable for use as a gem source by (Bundler)[http://gembundler.com]. Erebor is a public repo; gems published here are visible to the world.

> This Kingdom Under the Mountain held one of the largest dwarven treasure hoards in Middle-earth.

One day the dwarves of Erebor may branch out to other crafts: [modules](https://npmjs.org), [jars](http://search.maven.org/#browse/), or [pods](http://cocoapods.org).

<img src="http://images.wikia.com/lotr/images/5/5d/Erebor.jpg">

## Using Erebor's Gems

To gain access to Erebor's gems, add this to your project's `Gemfile`:

    source https://raw.github.com/detroit-labs/erebor/gems/

## Adding Gems to Erebor

Build your gem the way that gems are build, then…

    cp YOUR-x.y.z.gem gems
    git add gems/YOUR-x.y.z.gem
    git ci -m 'added YOURGEM x.y.z' gems
    git push origin master
    script/publish

**Reminder**: public repo, no s3kr3ts

## Why Public?

Because simple.


I started off making Erebor private. Here's what `Gemfile` looks like:

    source "https://#{ENV['EREBOR_GITHUB_TOKEN']}:x-oauth-basic@raw.github.com/detroit-labs/erebor/gems"

Then you have a one time setup to [create an oath token](https://help.github.com/articles/creating-an-oauth-token-for-command-line-use) and then makie sure that `EREBOR_GITHUB_TOKEN` is set in your environment and how secure will it be when everyone's github oauth token is stored in the `.bashrc`…

and then I made [detroit-labs/erebor](https://github.com/detroit-labs/erebor) a public repo and moved on.

## 3rd Party Gems

First, you should get gems from [rubygems.org](http://rubygems.org). If you need an unreleased version, then you should [get the gem from its git repo](http://gembundler.com/git.html).

Reasons to put a 3rd party gem in Erebor:

* we've forked and customized the gem and our changes haven't been accepted yet
* the gem won't install via Bundler from its git source ([rugged](https://github.com/libgit2/rugged) has this [problem](https://github.com/libgit2/rugged/pull/107#issuecomment-9437471)).

## TODO

* have successful CI builds publish instead, then instructions simplify to:

        cp YOUR.gem gems
        git ci -m 'added YOURGEM' gems
        git push origin master
