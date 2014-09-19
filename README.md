## docs.nitrous.io - Documentation for the Nitrous CLI

### Running for the First Time

Prepare this repo for your local environment:

    $ gem install bundle
    $ bundle install

Run locally with Jekyll:

    $ bundle exec jekyll serve --baseurl "" -w

### Creating and Editing Pages/Posts

Pages are generated in /article/ format, so the title within `/_posts/2014-08-19-page-title.md` will be used in the permalink.

Articles should be dated and added to `/_posts/`. If you need to add more articles within a sub-directory, add the folder directly in the root folder (messy I know, looking for a way to organize better without plugins).

### Updating files and Publishing

Editing: Work within the **gh-pages** branch. For CSS alterations, work within the Sass files (the .css files will be overwritten upon publishing).

Publishing:

* Add the 'publish' alias to the end of your `.git/config` file:

```bash
[alias]
publish = "!f() { git checkout gh-pages && echo '[BUILD]' && jekyll build && sass css/syntax.scss css/syntax.css --style compressed && sass css/docs.scss css/docs.css --style compressed && sass css/font-awesome/css/font-awesome.scss css/font-awesome/css/font-awesome.css --style compressed && sass css/bootstrap.scss css/bootstrap.css --style compressed && sass css/main.scss css/main.css --style compressed && echo '[COMMIT]' && git add -A && git commit -m 'Build website' && echo && echo '[PUSH]' && git push origin gh-pages; }; f"
```

* After making changes, simply run `git publish` to publish to the gh-pages branch. This will automate `git add`, `git commit`, and run Sass.
