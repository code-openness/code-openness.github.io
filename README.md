# code-openness.github.io
## Installing ruby and Jekyll:
```
$ ruby --version
$ gem install bundler
```
followed by:
```
$ bundle install
```
This installs everything defined in the Gemfile and `_config.yml`.

for further instalation help check: [GitHub](https://help.github.com/en/articles/setting-up-your-github-pages-site-locally-with-jekyll)

## See edited jekyll site locally using: 

```
$ bundle exec jekyll serve
$ bundle exec jekyll serve
> Configuration file: /Users/octocat/my-site/_config.yml
>            Source: /Users/octocat/my-site
>       Destination: /Users/octocat/my-site/_site
> Incremental build: disabled. Enable with --incremental
>      Generating...
>                    done in 0.309 seconds.
> Auto-regeneration: enabled for '/Users/octocat/my-site'
> Configuration file: /Users/octocat/my-site/_config.yml
>    Server address: http://127.0.0.1:4000/
>  Server running... press ctrl-c to stop.
```

## Used theme:
We are using the just-the-docs theme from https://github.com/pmarsceill/just-the-docs
### specific installation: 
`$ gem install just-the-docs`

## Page Navigation:
we are currentlly using the navigation bar formating described in [just-the-docs documentation](https://pmarsceill.github.io/just-the-docs/docs/navigation-structure/)
At the beginning of each Markdown file there should be a, heading. Currently each team has an overall team link (parent file) and should add all other documentation files into their respective folder ex. teamThree. 
The parent file (ex. teamOne.md) should contain the following heading: 
```
---
layout: default
title: 'Team 1: Data Context' 
nav_order: 1
has_children: true
permalink: /teamOne
---
```
`nav_order` defines at which position in the nav-bar it will be shown, team one should be in position 1, team two in position 2 etc.
`has_children`is set to true, to indicate that there are sub files, which will need to be displayed as sub-categories.
`permalink`gives the link to the folder in which the documentation files of each team are to be found

In the child files, the following heading should be put at the beginning of each file: 
```
---
layout: default
title: Example
parent: 'Team 1: Data Context' 
nav_order: 1
---
```
Here it is important to note that the `parent` tag needs to contain the title of the parent page/file, not the file name!!
In addition the `nav_order` should be adjusted to order the child pages, eg. Background should be in position 1, Motivation in 2 etc.
