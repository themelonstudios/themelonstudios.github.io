[![Build Status](https://travis-ci.org/artsy/artsy.github.io.svg)](https://travis-ci.org/artsy/artsy.github.io)

The Artsy OSS page and the blog runs on top of a default jekyll install. If you would like an overview of jekyll their [website rocks](http://jekyllrb.com/).

## Setup

```
  git clone git@github.com:artsy/artsy.github.io.git
  cd artsy.github.io
  rake bootstrap
  rake build
```

## Running the OSS Site / Blog locally

Running `rake serve` will _not_ generate category pages. They take a _long_ time to generate. No one wants that when working on the site.

```
  rake serve
```

Categories are generated when the ENV var `PRODUCTION` = `"YES"`.

## Deploying

Travis CI will automatically deploy when new commits are pushed to the `source` branch, so you should not need to deploy from your local computer. However, if you need to deploy locally, the `rake deploy` command is available. 

## Adding an Author

Authors are key-value stored, so you will need to give yourself a key inside [_config.yml](_config.yml) - for example:

```yaml
  joey:
    name: Joey Aghion
    github: joeyAghion
    twitter: joeyAghion
    site: http://joey.aghion.com
```

Everything but name is optional.

## Authoring an Article

TLDR
_To generate a new post, create a new file in the `_posts` directory. Be sure to add your name as the author of the post and include several categories to file the post under. Here is a sample header YAML:_

```yaml
---
layout: post
title: "Responsive Layouts with CSS3"
date: 2012-01-17 11:03
comments: true
author: Matt McNierney
github-url: https://www.github.com/mmcnierney14
twitter-url: http://twitter.com/mmcnierney
blog-url: http://mattmcnierney.wordpress.com
categories: [Design, CSS, HTML5]
---
```

More info can be found in the [official docs](http://jekyllrb.com/docs/posts/).

When you have authored an article, `git add` and `git commit` it, then push to a named branch with `git push origin [branch]`, and create a pull request to the `source` branch, it will be deployed to the site by travis when merged.
