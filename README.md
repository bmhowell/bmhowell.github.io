# bmhowell.github.io — Local development

Quick notes to run this Jekyll site locally on macOS.

Prerequisites
- Homebrew (recommended): https://brew.sh
- Ruby (2.7+ or the version in Gemfile). Use rbenv or system Ruby.
- Bundler gem

Install (recommended)
```sh
brew install rbenv ruby-build
rbenv install 3.2.2      # or a Ruby version matching your Gemfile
rbenv local 3.2.2
gem install bundler
```

Get dependencies and serve
```sh
bundle install
bundle exec jekyll serve --livereload
# Open http://127.0.0.1:4000
```

If `_site` is already committed
```sh
# add to .gitignore, remove from git history in working tree, then commit
echo "_site" >> .gitignore
git rm -r --cached _site
git commit -m "Remove generated site from repo"
```

Notes and tips
- Source pages live under `pages/`, `_posts/`, assets in `assets/`. The site layout is in `_layouts/`.
- MathJax and analytics are currently included per-page; consider moving them into `_layouts/default.html`.
- Use `bundle exec jekyll build` to produce output in `_site/`.

Further help
- Jekyll docs: https://jekyllrb.com
- If you want, I can convert one page to use the site's layout