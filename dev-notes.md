## push as cudmorelab

```
git push https://cudmorelab:<token>@github.com/cudmorelab/cudmorelab.github.io.git --all
```

## Using two _config.yml

Building locally is really slow with remote_theme. Solution is to use two config files. The two cconfig files are a comma seperated list without space, e.g. `--config _config.yml,_config_local.yml`.

```
bundle exec jekyll serve --livereload --config _config.yml,_config_local.yml
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
gem "minimal-mistakes-jekyll"
```

Then

```
bundle
bundle install
```

## Warnings/Errors installing ruby

Add to path

```
# if your using zshrc shell
echo 'export PATH="/usr/local/lib/ruby/gems/3.0.0/bin:$PATH"' >> ~/.zshrc
# if your using bash shell
echo 'export PATH="/usr/local/lib/ruby/gems/3.0.0/bin:$PATH"' >> ~/.bash_profile
```

These were warnings/errors on installing ruby.

```
 default, binaries installed by gem will be placed into:
  /usr/local/lib/ruby/gems/3.0.0/bin

You may want to add this to your PATH.

ruby is keg-only, which means it was not symlinked into /usr/local,
because macOS already provides this software and installing another version in
parallel can cause all kinds of trouble.

If you need to have ruby first in your PATH, run:
  echo 'export PATH="/usr/local/opt/ruby/bin:$PATH"' >> /Users/cudmore/.bash_profile

For compilers to find ruby you may need to set:
  export LDFLAGS="-L/usr/local/opt/ruby/lib"
  export CPPFLAGS="-I/usr/local/opt/ruby/include"

For pkg-config to find ruby you may need to set:
  export PKG_CONFIG_PATH="/usr/local/opt/ruby/lib/pkgconfig"
```

## Install jekyll

```
gem install --user-install bundler jekyll
```

Also needed:

```
gem install webrick
```
