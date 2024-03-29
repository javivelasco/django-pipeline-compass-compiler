## Django Pipeline Compass Compiler

Compiler class to use with [Django Pipeline](https://github.com/cyberdelia/django-pipeline) package to compile [Compass](http://compass-style.org/). It uses the official compass gem so you have to install it first:

```shell
$ sudo gem install compass
```

### Installation

The installation is as a `pip` regular package. Remember you have to install [Django Pipeline](https://github.com/cyberdelia/django-pipeline) first since the compiler works as a plugin for it. Once you have it:

```bash
$ pip install django-pipeline-compass-compiler
# or from source
$ pip install git+https://github.com/javivelasco/django-pipeline-compass-compiler.git

```

### Usage

In your `settings.py` you should specify the location of your compass compiler binary installed with RubyGems. As an option, you can give extra arguments to the compiler just as you'd do it when compiling from the command line. Also, you have to tell Pipeline to use the compiler. An example:

```python
PIPELINE_COMPASS_BINARY = '/usr/local/bin/compass'   # default: '/usr/bin/env compass'
PIPELINE_COMPASS_ARGUMENTS = '-c path/to/config.rb'  # default: ''

PIPELINE_COMPILERS = ('pipeline_compass.compass.CompassCompiler')
```

### About

I've created and updated this package to reuse it in my future projects, but is strongly based in [this](https://github.com/mila-labs/django-pipeline-compass-rubygem) package. The main difference is that here the source is compiled only if there were no changes from last compiling.
