Heroku Buildpack  Long Compile
----------

# About

This is a buildpack that allows you to have a long compile step easily.
This can be useful for reproducing certain bugs things on the Heroku
Dashboard. You probably won't find this buildpack very useful unless
you're working on the Heroku platform.

# What this does

Basically adds a `sleep` of a specified duration to the `compile` step
of building your app. By default, the value is `1m`. You can change the
value by setting the following config var:

````
heroku config:set -a myapp LONG_COMPILE_TIME=1s
```

The value can be anything that `sleep` for Linux can take, which can
be found on [this blogbpost by
CyberCiti](https://www.cyberciti.biz/faq/linux-unix-sleep-bash-scripting/).

# Installation

Add the buildpack to your dyno using the standard Heroku command:

`heroku buildpacks:set https://github.com/fivetanley/heroku-buildpack-long-compile`
