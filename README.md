# Autoenv: Directory-based Environments

Magic per-project shell environments. Very pretentious.


## What is it?

If a directory contains a `.env` file, it will automatically be executed
when you `cd` into it.

This is great for...

- auto-activating virtualenvs
- project-specific environment variables
- making millions

[Foreman](https://github.com/ddollar/foreman) env files are completely compatible.

You can also nest envs within eachother. How awesome is that!?

## Usage

Follow the white rabbit::

```
$ touch project/.env
$ echo "echo 'woah'" > project/.env
$ cd project
woah
```

![](http://media.tumblr.com/tumblr_ltuzjvbQ6L1qzgpx9.gif)


## Install

Install it easily:

### Mac OS X Using Homebrew

```
$ brew install autoenv
$ echo 'source /usr/local/opt/autoenv/activate.sh' >> ~/.bash_profile
```


### Using pip

```
$ pip install autoenv
$ echo "source `which activate.sh`" >> ~/.bashrc
```


### Using git

```
$ git clone git://github.com/kennethreitz/autoenv.git ~/.autoenv
$ echo 'source ~/.autoenv/activate.sh' >> ~/.bashrc
```


## Disclaimer

Autoenv overrides `cd`. If you already do this, invoke `autoenv_init` within your custom `cd` after sourcing `activate.sh`.

Autoenv can be disabled via `unset cd` if you experience I/O issues with
certain file systems, particularly those that are FUSE-based (such as `smbnetfs`).

## Testing

Install the test runner::

```
$ make
gem install dtf --version 0.1.2
Successfully installed dtf-0.1.2
```

Test::

```
$ make test
dtf tests/*
............
##### Processed commands 14 of 14, success tests 12 of 12.
```

# Python Project Template
### Install autoenv

```sh
git clone https://github.com/tranhuucuong91/autoenv.git ~/.autoenv
echo 'source ~/.autoenv/activate.sh' >> ~/.bashrc
echo 'source ~/.autoenv/activate.sh' >> ~/.zshrc_myconfig
```

### Create python project use virtualenv

```sh
virtualenv venv -p python3
```

### Create file .env with content:

```sh
BASEDIR=$(dirname $0)

source ${BASEDIR}/venv/bin/activate
```

