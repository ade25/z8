Setup webserver buildout
========================

We strive to establish a general working environment and therefore provide
this "best practice" information. In order to make a webserver buildout
usable in your local development environment you only need to follow a few
simple steps:


Requirements
------------

All interaction is based on the push deployment tool Fabric. In order to
bootstrap you local directory you need to setup a virtual environment and
install a few dependencies

``` bash
$ cd ~/
$ virtualenv .
$ bin/pip install zc.buildout
$ bin/buildout -c development.cfg
```

You need to setup your global fabfile configuration by adding a user and slack
specific configuration to oyut buildout settings ~/.buildout/default.cfg:

```
[settings]
user                    = jd
username                = 'John Doe'
slack-api-token         = xoxp-accountid-some-super-secret
```

Usage
=====

In order to work with your webserver configuration and deployment setup you can
use the provided fabfile.

Example:

```bash
$ bin/fab list 	# show all available commands
$ bin/fab ctl:nginx,restart
$ bin/fab restart_varnish
$ bin/fab deploy_full
```




