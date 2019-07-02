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

for further instalation help check: https://help.github.com/en/articles/setting-up-your-github-pages-site-locally-with-jekyll

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
we are currentlly using the navigation bar formating described in [Section 8](https://jekyllrb.com/tutorials/navigation/#)
At the beginning of each Markdown file there should be a, heading as seen below: 
```
---
Title: Example Page
category: team_1
order: 1
---
```
