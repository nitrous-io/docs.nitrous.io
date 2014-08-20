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

**Always keep the Master branch updated before updating the gh-pages branch.**

To update the `gh-pages` branch run `bundle exec rake`. This will generate static content within the `_site/` folder, which Github Pages can host.
