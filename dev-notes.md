## Install on a new macOS machine

This is always super hard/stupid, to get a jekyll environment working on macOS. Too many moving parts

Hey ruby and jekyll developers, why is this so complicated?

Following this: https://jekyllrb.com/docs/installation/macos/

```
brew install chruby ruby-install

# install ruby (takes a few minutes)
ruby-install ruby

# should get
# Successfully installed ruby 3.1.2 into /Users/cudmore/.rubies/ruby-3.1.2

# configure shell to use chruby
echo "source $(brew --prefix)/opt/chruby/share/chruby/chruby.sh" >> ~/.zshrc
echo "source $(brew --prefix)/opt/chruby/share/chruby/auto.sh" >> ~/.zshrc
echo "chruby ruby-3.1.#1" >> ~/.zshrc

# quit and restart terminal and check ruby install
ruby -v

# should get something like
# ruby 2.6.8p205 (2021-07-07 revision 67951) [universal.arm64e-darwin21]

# finally, install jekyll
# does not work !!!!!!!!!!!
#gem install jekyll

# gives
#ERROR:  While executing gem ... (Gem::FilePermissionError)
#    You don't have write permissions for the /Library/Ruby/Gems/2.6.0 directory.

# this works better
gem install --user-install bundler jekyll

# then I tried (always a bad idea)
sudo gem install jekyll

# then `jekyll serve` gives errors

bundle install # why do I need to do this ???

gem install minimal-mistakes-jekyll



```

## push as cudmorelab

```
git push https://cudmorelab:<token>@github.com/cudmorelab/cudmorelab.github.io.git --all
```

## Using two _config.yml

Building locally is really slow with remote_theme. Solution is to use two config files. The two config files are a comma seperated list without space, e.g. `--config _config.yml,_config_local.yml`.

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
# Add this to GemFile
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
