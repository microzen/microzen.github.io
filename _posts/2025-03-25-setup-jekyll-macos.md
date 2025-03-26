---
layout: post
title:  "Setting Up Jekyll on MacOS"
date:   2025-03-25
categories: jekyll macOS
---

# Setting Up Jekyll on MacOS with an Existing Repository

Some systems, such as MacOS, have a built-in version of Ruby. Using `rbenv` to manage your Ruby without modifying the system Ruby is a good approach.

## Install rbenv and ruby-build

You need to install rbenv and ruby-build first.
```bash
brew update
brew install rbenv ruby-build
```

Then add rbenv to your shell:
```bash
echo 'eval "$(rbenv init -)"' >> ~/.zshrc
source ~/.zshrc
```

After installing and setting up rbenv and ruby-build, use the following commands to install Ruby:

```bash
rbenv install -l # List the latest versions
rbenv install 3.4.2 # Pick the version you want (for example, Ruby 3.4.2) and install it
rbenv global 3.4.2 # Set Ruby version to 3.4.2
rbenv global system # Set it back to the system built-in version
```

Sometimes changes in your shell configuration only take effect in a new session, so you have to restart your terminal.

Finally, check the Ruby version:

```bash
ruby -v
```

## Install Jekyll

If you want Jekyll to generate its skeleton directly into your repository directory (and you’re okay with merging files), you can run:

```bash
jekyll new . --force
```

Configure your site: [GitHub Pages and Jekyll Documentation](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/about-github-pages-and-jekyll)

## Configuring Jekyll in your GitHub Pages site

[GitHub Configuring Guide](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/about-github-pages-and-jekyll)

You can configure most Jekyll settings, such as your site's theme and plugins, by editing your _config.yml file. For more information, see Configuration in the Jekyll documentation.

Some configuration settings cannot be changed for GitHub Pages sites.
```
lsi: false
safe: true
source: [your repo's top level directory]
incremental: false
highlighter: rouge
gist:
  noscript: false
kramdown:
  math_engine: mathjax
  syntax_highlighter: rouge
```