Fig
===

[![Build Status](https://travis-ci.org/orchardup/fig.png?branch=master)](https://travis-ci.org/orchardup/fig)
[![PyPI version](https://badge.fury.io/py/fig.png)](http://badge.fury.io/py/fig)

Fast, isolated development environments using Docker.

Define your app's environment with Docker so it can be reproduced anywhere.

    FROM orchardup/python:2.7
    ADD . /code
    RUN pip install -r requirements.txt
    WORKDIR /code
    CMD python app.py

Define your app's services so they can be run alongside in an isolated environment. (No more installing Postgres on your laptop!)

```yaml
web:
  build: .
  links:
   - db
  ports:
   - 8000:8000
db:
  image: orchardup/postgresql
```

Then type `fig up`, and Fig will start and run your entire app:

![example fig run](https://orchardup.com/static/images/fig-example-large.f96065fc9e22.gif)

There are commands to:

 - start, stop and rebuild services
 - view the status of running services
 - tail running services' log output
 - run a one-off command on a service

Fig is a project from [Orchard](https://orchardup.com). [Follow us on Twitter](https://twitter.com/orchardup) to keep up to date with Fig and other Docker news.

Installation and documentation
------------------------------

Full documentation is available on [Fig's website](http://orchardup.github.io/fig/).

Running the test suite
----------------------

    $ script/test


