New Rails Application
=====================

1. Set up Rails
---------------

First, check your Rails version and update, if necessary.

```
rails -v
```

Once you're happy with the version, create a new Rails application.

```
rails new PROJECT_NAME
```

2. Remove Turbolinks
--------------------

Feel free to make up your own opinion about [turbolinks](https://github.com/rails/turbolinks), but I for one am not a fan. So I remove them, and here's how you do that.

- Remove the `turbolinks` gem from your `Gemfile`
- Run `bundle install`
- Remove the `//= require turbolinks` from `app/assets/javascripts/application.js`
- Remove the `"data-turbolinks-track" => true` hashes from `app/views/layouts/application.html.erb`

3. Set up Haml
--------------

I prefer using Haml, so I start by adding the `haml-rails` gem now so that any generated views will use it as well moving forward.

4. Convert Layout ERB File to Haml
----------------------------------

Once Haml is installed, you'll need to convert the Rails `app/views/layouts/application.html.erb` file to `.haml`. Generally, it'll be converted to something like this:

```haml
!!! 5
%html(lang='en')
%head

  %title Comics
  = stylesheet_link_tag    'application'
  = javascript_include_tag 'application'
  = csrf_meta_tags

%body

  = yield
```

5. Set up Models & Database
---------------------------

Next, run your generators and do your thing.

6. Add bin/setup File
---------------------

To make it easier for others to jump on your project (if that's the case), add a `bin/setup` executable to your project that will run all the necessary commands to set the project up locally.

```
#!/usr/bin/env bash

# Bundler
bundle install

# Database
cp config/database.example.yml config/database.yml
bundle exec rake db:create db:setup

# Pow
gem install powder
powder link
powder open
```

That's an example of one I've used on a project before, and it worked really well.
