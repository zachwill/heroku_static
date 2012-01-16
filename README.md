Heroku Static
=============

An example for putting static sites on Heroku, taken from [Kenneth
Reitz's blog post](http://kennethreitz.com/static-sites-on-heroku-cedar.html).


Usage
-----

First, make sure you have the [Heroku CLI
installed](http://devcenter.heroku.com/articles/heroku-command).

You need the blank `index.php` and correct `.htaccess` file in order for
Heroku to serve your static site. You can then create your new Heroku
application by running the following on the commandline (with your
application's name substituted for `my-app-name`):

    heroku create my-app-name -s cedar
    git push heroku master

You can then open your new static site with the following command:

    heroku open


Development
-----------

During development, you'll probably want to still use `localhost` when
working on your project &mdash; rather than simply looking at the
`index.html` file in your browser of choice. You can use Python to serve
your content during development:

    cd path/to/my/project
    python -m SimpleHTTPServer

Your project should then be up and running on:
[`localhost:8000`](http://localhost:8000)


Custom Domain
-------------

Attaching [your own custom domain to your Heroku
instance](http://devcenter.heroku.com/articles/custom-domains) is pretty
easy.

    heroku addons:add custom_domains
    heroku domains:add example.com
    heroku domains:add www.example.com

Make sure to attach the following A records using your DNS management
tool:

    75.101.163.44
    75.101.145.87
    174.129.212.2

For more information, make sure to read this [Heroku devcenter
article](http://devcenter.heroku.com/articles/custom-domains).
