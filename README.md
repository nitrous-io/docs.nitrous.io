## docs.nitrous.io - Documentation for the Nitrous CLI

### Running for the First Time

Prepare this repo for your local environment:

    $ gem install bundle
    $ bundle install

Run with Jekyll:

    $ bundle exec jekyll serve -w

### Creating and Editing Pages/Posts

Pages are generated in /article/ format, so the title within `/_posts/2014-08-19-page-title.md` will be used in the permalink.

Articles should be dated and added to `/_posts/`. If you need to add more articles within a sub-directory, add the folder directly in the root folder (messy I know, looking for a way to organize better without plugins).

### Updating files and Publishing

Editing: Work within the **gh-pages** branch. For CSS alterations, work within the Sass files (the .css files will be overwritten upon publishing).

Publishing: After making changes, simply run `git publish` to publish to the gh-pages branch. This will automate `git add`, `git commit`, and run Sass.
