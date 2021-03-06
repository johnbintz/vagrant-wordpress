# Vagrant Wordpress Theming #

This is a [Vagrant][vagrant] setup for creating Wordpress themes. Uses
[Chef Solo][chef] recipes for provisioning. The recipes are copied from
[my fork][cookbooks-developish] of [those by Opscode][cookbooks-opscode], which
allows for their use with Chef Solo and for a blank MySQL root password.

NEVER WORRY ABOUT SETTING UP MYSQL AND PHP ON YOUR COMPUTER EVER AGAIN!

## Requirements ##

* [Bundler](http://github.com/carlhuda/bundler)

    $ gem install bundler

## To get started ##

    $ git clone git://github.com/paulcarvill/vagrant-wordpress.git <working directory>
    $ cd <working directory>
    $ bundle install
    $ bundle exec vagrant up
    $ open http://localhost:8080

You'll need to install Wordpress (i.e. set up an admin user, name the Wordpress 
blog etc.). Then copy a base theme (like the totally stripped-down [Starkers][starkers]) into the theme 
directory, select Appearance > Themes in the Wordpress dashboard, choose the new theme and get to work!

Your Ubuntu/PHP/MySQL box exists as a virtual machine. The website running on 
the virtual machine is pointing back at the theme directory on your local 
machine. So you can do your work, keep it in version control, and destroy the 
virtual machine once you're finished using:

    $ bundle exec vagrant destroy

[vagrant]:http://vagrantup.com
[chef]:http://wiki.opscode.com/display/chef/Chef+Solo
[cookbooks-developish]:https://github.com/opscode/cookbooks
[cookbooks-opscode]:https://github.com/opscode/cookbooks
[starkers]:http://starkerstheme.com

## Eat your veggies and get strong ##

You also get a basic configuration of [Cucumber](http://cukes.info/) set up to
make sure your initial install of WordPress is sane. Just run `bundle exec cucumber`.
You'll be using [capybara-webkit](http://github.com/thoughtbot/capybara-webkit) to run your tests in a virtual
browser. Write those acceptance tests for your theme/plugin!

