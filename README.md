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

* There is a Rakefile to help sync `_sites` to the `gh-pages` branch.

```bash
rake publish
```
