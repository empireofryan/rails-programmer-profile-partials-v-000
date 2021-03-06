# Objectives
1. Practice using partials.
2. Use all the different techniques you've learned in this unit. 
3. Create helper methods in your model to DRY up your views.

## Overview

We have a Rails app that showcases some of our favorite programmers. The landing page is an index of all the programmers, and users can click on each programmer to see his or her profile page. There's just one problem - the views are loaded with repetition and clunky iteration, and could use some serious refactoring. Your job is to clean up `programmers/index.html.erb` and `programmers/show.html.erb` by using partials.

## Instructions

Fork and clone the lab. Run `bundle install` and `rake db:migrate`, then `rake db:migrate RAILS_ENV=test`. Next, seed the database with some programmers - run `rake db:seed` - and start the sever to see the app in the browser.

Run `rspec` and make the tests pass one at a time! The app will continue to have the same functionality (keep checking it in the browser), but you'll be making the following partials to clean up the views:

1. A partial to render the navbar.
2. A partial to render all the programmers on the index page (see the example above!).
3. A bonus partial to abstract away some of the repetition in `app/views/programmers/show.html.erb`. More details on that in the next section.

## Bonus

This part is a little more complex than the previous two steps, and will require you to get a little more creative.

When you look at `app/views/programmers/show.html.erb`, you will probably notice a pattern in how several of the attributes are rendered (specifically `home_country`, `quote`, and `claim_to_fame`. They each seem to be in a `<p>` tag with a bold capitalized label followed by the value for the given attribute. You'll want to render each of these with a single partial, `app/views/programmers/_attribute.html.erb`. Here are two hints to set you on the right track:

1. You'll need some way to dynamically refer to the different attributes of the programmer we need to display, and the associated values.
2. You'll have to pass those key-value pairs as local variables to the partial to but still be able to dynamically refer those pairs in the partial.


## Resources
- [Rails Guides - Using Partials](http://guides.rubyonrails.org/layouts_and_rendering.html#using-partials)
- [Action View Partials](http://api.rubyonrails.org/classes/ActionView/PartialRenderer.html)
- [Metaprogramming in Ruby](http://ruby-metaprogramming.rubylearning.com/html/ruby_metaprogramming_2.html) - See section 1.3.2 to learn about `send`.
- [Stack Overflow - Passing Variables to a Partial](http://stackoverflow.com/questions/16242121/rails-4-passing-variable-to-partial) (see the first answer for a concise example)


<a href='https://learn.co/lessons/rails-programmer-profile-partials' data-visibility='hidden'>View this lesson on Learn.co</a>
