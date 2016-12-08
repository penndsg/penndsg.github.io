# Penn Data Science Group website

## Build site

To build the website locally, clone the repo with:

```
git clone https://github.com/penndsg/website_source.git
```

Make sure you have ruby installed (preferrably using RVM). If you don't have the `bundler` gem installed, install it by typing

```
gem install bundler
```

Then install necessary Ruby dependencies by running `bundle install` from within the `website_source` directory.  After this, the site can be be built with:

```
jekyll build
```

To view the site, run `jekyll serve` and point a browser to `http://localhost:4000/`.  More information on Jekyll can be found [here](http://jekyllrb.com/).

## Deploy site

To deploy changes to the site, first make sure you have been added as a contributor to the penndsg/website_source.git repo, then simply type

```
./deploy
```

from within the `website_source` directory. You should immediately see your changes reflected in penndsg.github.io.
