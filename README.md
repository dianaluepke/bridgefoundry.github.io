Bridge Foundry Web Site
=======================

This site is build with [Jeykll](https://jekyllrb.com/) and hosted on 
[Github Pages](https://pages.github.com/) -- pushing the master branch will
update the website.


## Local development

install Ruby

```
gem install bundler
bundle
```

Note: the website integrates two other repos, which are integrated as submodules 
and then need to be built individually.  If you want to make changes to those, 
work directly in these separate repos

* [code of conduct](https://github.com/bridgefoundry/code-of-conduct)
* [workshop-map](https://github.com/bridgefoundry/workshop-map)

The full website can be built by triggering a build on Travis, which anyone
who is a member of the `bridgefoundry` organization on github should be able
to do.

To build locally:

```
git submodule update --init --recursive
(cd code-of-conduct-src; bundle; bundle exec jekyll build --destination ../code-of-conduct)
(cd workshop-map-src; bundle; bundle exec jekyll build --destination ../workshop-map)
```


to run the site:

```
jekyll serve
```

point your browser at: http://localhost:4000/


## Deploying the site

[![Build Status](https://travis-ci.org/bridgefoundry/bridgefoundry.github.io.svg?branch=master)](https://travis-ci.org/bridgefoundry/bridgefoundry.github.io)

The site is deployed with Firebase hosting and should automatically deploy
whenever a change is checked into master.  If there are any issues, please
send email to admin@bridgefoundry.org

When we update the code-of-conduct or workshop-map, then we need to make some
kind of change to this repo (such as this README) in order to trigger a new
deploy.
