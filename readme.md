# Simple SEO Blog for RefineryCMS

This project is the search engine-optimized version of [refinerycms-blog](https://github.com/refinery/refinerycms-blog).

Main SEO optimizations:

* `/blog/:category_slug/:post_slug` post urls (with a 1-n association between category and posts);
* `/blog/:category_slug` category urls;
* sticky posts

This is the *edge* -and for now the only- version of `refinerycms-seoblog` and it supports only Refinery 3.x and Rails 4.1.x. But it works!

<!-- Options:

* [ShareThis.com](http://sharethis.com) support on posts. To enable, set your key in Refinery's settings area. -->

## Requirements

Refinery CMS version 3.0.0 or above.

## Install

Open up your ``Gemfile`` and add at the bottom this line. If refinerycms-page-images extension is also installed, make sure the line come before gem 'refinerycms-page-images'

```ruby
gem 'refinerycms-seoblog', git: 'https://github.com/darmens/refinerycms-seoblog', branch: 'master'
```

Now, run ``bundle install``

Next, to install the blog plugin run:

    rails generate refinery:blog

Run database migrations:

    rake db:migrate

Finally seed your database and you're done.

    rake db:seed

## Visual Editor

By default, this extension does not require any particular visual editor.
Previously, Refinery was coupled to WYMeditor but this has been extracted to an
extension, [refinerycms-wymeditor](https://github.com/parndt/refinerycms-wymeditor).

If you want to use `refinerycms-wymeditor`, simply place it in your Gemfile:

```ruby
gem 'refinerycms-wymeditor', ['~> 1.0', '>= 1.0.6']
```

## Developing & Contributing

The version of Refinery to develop this engine against is defined in the gemspec. To override the version of refinery to develop against, edit the project Gemfile to point to a local path containing a clone of refinerycms.

### Testing

Generate the dummy application to test against

    $ bundle exec rake refinery:testing:dummy_app

Run the test suite with [Guard](https://github.com/guard/guard)

    $ bundle exec guard start

Or just with rake spec

    $ bundle exec rake spec

## Additional Features
* To limit rss feed length, use the 'max_results' parameter

        http://test.host/blog/feed.rss?max_results=10

## More Information
* Check out the [Refinery Website](http://refinerycms.com/)
