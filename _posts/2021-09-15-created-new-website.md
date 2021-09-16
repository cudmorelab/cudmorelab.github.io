---
title: "Created this website"
categories:
  - Tech Blog
tags:
  - tech
---

This blog is created with [Jekyll][jekyll] using the [Minimal Mistakes][mm] theme. All the code is stored on GitHub and the website gets built automatically as the content is updated.

[jekyll]: https://jekyllrb.com/
[mm]: https://mademistakes.com/work/minimal-mistakes-jekyll-theme/

### Install Ruby

xxx

### Install Jekyll

xxx

### Install Minimal-Mistakes

###Tweeks

#### Serve local

```
bundle exec jekyll serve --livereload --config _config.yml,_config_local.yml
```

#### Serve locally with 2 YAML files

When online, we build with xxx. When we do this locally it takes forever to proof new changes. To get around this, when locaal, we use to YAML files where the seccond one just over-rides this xxx.

```
theme: minimal-mistakes-jekyll
remote_theme: none
```

See: https://talk.jekyllrb.com/t/using-gem-locally-using-remote-on-github/5211/4

Requires a local copy of:

```
gem install minimal-mistakes-jekyll

# if that does not work
gem install --user-install bundler minimal-mistakes-jekyll
```

Add to GemFile. The Gemfile is not used by github pages so it is fine to add to it in version control.

```
# Add this to GemFile
gem "minimal-mistakes-jekyll"
```

Then

```
bundle
bundle install
```

### Push to GitHub with a different username

```
git push https://cudmorelab:<token>@github.com/cudmorelab/cudmorelab.github.io.git --all
```
