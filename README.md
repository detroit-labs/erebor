# Erebor

> This Kingdom Under the Mountain held one of the largest dwarven treasure hoards in Middle-earth.

<img src="http://images.wikia.com/lotr/images/5/5d/Erebor.jpg">

## Using Erebor's Gems

To gain access to Erebor's gems, add this to your project's `Gemfile`:

    source https://raw.github.com/detroit-labs/erebor/gems/
    
## Adding Gems to Erebor

**IMPORTANT**: this is a public repo, don't commit secrets.

Assuming you've succesfully built a gem, 

    cp YOUR-x.y.z.gem gems
    git add gems/YOUR-x.y.z.gem
    git ci -m 'added YOURGEM x.y.z' gems
    git push origin master
    script/publish

## TODO

* have successful CI builds publish instead, then instructions simplify to:

        cp YOUR.gem gems
        git ci -m 'added YOURGEM' gems
        git push origin master
