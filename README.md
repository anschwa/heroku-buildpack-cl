Heroku Buildpack for Common Lisp
================================

A Buildpack that allows you to deploy Common Lisp applications on the Heroku infrastructure.

Original work by Mike Travers, mt@hyperphor.com and José Santos, jsmpereira@gmail.com

## Using Buildpack
* Support for SBCL, CCL, Quicklisp, Hunchentoot, and Postgres

```
# Create a new Heroku app
heroku create --buildpack http://github.com/anschwa/heroku-buildpack-cl.git --app <your-app>

# Create Git Repository and add to Heroku
git init && heroku git:remote --app <your-app>

# Implementation choice via environment variables.
heroku config:add CL_IMPL={sbcl|ccl} --app <your-app>

# To avoid trouble with SBCL source encoding use:
heroku config:add LANG=en_US.UTF-8 --app <your-app>

# Set webserver
heroku config:add CL_WEBSERVER=huchentoot --app <your-app>

# Add Postgres Database
heroku addons:create heroku-postgresql:hobby-dev --app <your-app>

# Deploy
git push heroku master

# View App
heroku open
```

## Credits
* [the example application](https://github.com/jsmpereira/heroku-cl-example).
* [the WuWei demo site](http://warm-sky-3012.herokuapp.com/) and [source](https://github.com/mtravers/wuwei).
* Heroku and their new [Buildpack-capable stack](http://devcenter.heroku.com/articles/buildpacks)
* [QuickLisp](http://www.quicklisp.org/) library manager 
* [OpenMCL](http://trac.clozure.com/ccl) aka Clozure CL 
* [Portable AllegroServe](http://portableaserve.sourceforge.net/)


