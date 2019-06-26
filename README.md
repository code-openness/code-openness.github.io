# code-openness.github.io
## Installing ruby
```
$ ruby --version
$ gem install bundler
```
## Installing Jekyll and all dependencies: 
```
$ bundle install
```
This istalls everything defined in the Gemfile and `_config.yml`.

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
