Rescale API Documentation
========

Rescale's [API documentation](https://rescale.github.io/api-docs/) is built 
with [Slate](https://tripit.github.io/slate).


Getting Started
------------------------------

### Prerequisites

 - **Linux or OS X** — Windows may work, but is unsupported.
 - **Ruby, version 1.9.3 or newer**
 - **Bundler** — If Ruby is already installed, but the `bundle` command doesn't work, just run `gem install bundler` in a terminal.

### Getting Set Up

 1. Install all dependencies: `bundle install`
 2. Start the test server: `bundle exec middleman server`

Your local copy of the API documentation is now available at <http://localhost:4567>.

### Editing

All the documentation is written in
[markdown syntax](httpss://github.com/tripit/slate/wiki/Markdown-Syntax),
and built into html by the `rake build` command. The main file of interest
is `source/index.md`, which outlines the structure of the documentation.
Under `includes`, we have files for each section of documentation, which must be added
to the `includes` section in `index.md`.

### Deploying


 1. Merge your markdown changes into `origin/master`
 1. Run `bundle exec rake publish` to compile the changes and push to github pages
    deployment
