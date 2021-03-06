Magical MapRoulette Machine
===========================

An interactive Challenge loader script for MapRoulette - create or maintain a challenge with just an Overpass query!

## Install it

First, clone this repository:

```shell
git clone https://github.com/mvexel/magical-maproulette-machine.git
```

Then, move into the directory, and install the requirements.

```shell
cd magical-maproulette-machine
pip install -r requirements.txt
```

Other than those, you will also need the Overpass Python wrapper. This module is not on PyPi yet, so you will need to head to [its project page](https://github.com/mvexel/overpass-api-python-wrapper), clone the repo and `python setup.py install` it.

## Use it

You can invoke the Machine in two modes: **interactive** or **headless**. In interactive mode, you will be guided through the process of creating or updating the challenge. You invoke interactive mode by calling the Machine without arguments: `./mmm.py`.

The headless mode is useful for maintaining a challenge. It requires no user intervention so you can use it in a cron job. To use headless mode, you will need a config file. An example is in the repository. You then pass in the path to the config file as a positional argument: `./mmm.py config.yaml`. In this mode, it is assumed that you are updating an existing challenge. You can override this behavior by passing `--new`: `./mmm.py --new config.yaml`

Invoke the Machine with `--help` for more information and some other optional arguments you can pass in:

```shell
$ ./mmm.py --help

Hey! This is the Magical MapRoulette Machine.

It lets you create a real MapRoulette challenge
from an Overpass query. Pretty neat. Magical!

usage: mmm.py [-h] [--new] [--v] [--dry-run] [CONFIG_FILE]

The Magical MapRoulette Machine

positional arguments:
  CONFIG_FILE     YAML config file. If omitted, we will use interactive mode.

optional arguments:
  -h, --help         show this help message and exit
  --new              Create a new challenge? If omitted we will try to update
                     an existing challenge.
  --v, --verbose     Verbose output
  --dry-run          Do not actually post anything
  --timeout TIMEOUT  API timeout limit in seconds (defaults to 30)
  ```

Tested with Python 2.7, should work with 3.x also.

## Wish list / Contribute / File a bug

See issues.