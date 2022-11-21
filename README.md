# mysqlclient

This project is a fork of [MySQLdb1](https://github.com/farcepest/MySQLdb1).
This project adds Python 3 support and fixed many bugs.

* PyPI: https://pypi.org/project/mysqlclient/
* GitHub: https://github.com/PyMySQL/mysqlclient


## Support

**Do Not use Github Issue Tracker to ask help.  OSS Maintainer is not free tech support**

When your question looks relating to Python rather than MySQL:

* Python mailing list [python-list](https://mail.python.org/mailman/listinfo/python-list)
* Slack [pythondev.slack.com](https://pyslackers.com/web/slack)

Or when you have question about MySQL:

* [MySQL Community on Slack](https://lefred.be/mysql-community-on-slack/)


## Install

### Windows

Building mysqlclient on Windows is very hard.
But there are some binary wheels you can install easily.

If binary wheels do not exist for your version of Python, it may be possible to
build from source, but if this does not work, **do not come asking for support.**
To build from source, download the
[MariaDB C Connector](https://mariadb.com/downloads/#connectors) and install
it. It must be installed in the default location
(usually "C:\Program Files\MariaDB\MariaDB Connector C" or
"C:\Program Files (x86)\MariaDB\MariaDB Connector C" for 32-bit). If you
build the connector yourself or install it in a different location, set the
environment variable `MYSQLCLIENT_CONNECTOR` before installing. Once you have
the connector installed and an appropriate version of Visual Studio for your
version of Python:

```
$ pip install mysqlclient
```

### macOS (Homebrew)

Install MySQL and mysqlclient:

```
# Assume you are activating Python 3 venv
$ brew install mysql
$ pip install mysqlclient
```

If you don't want to install MySQL server, you can use mysql-client instead:

```
# Assume you are activating Python 3 venv
$ brew install mysql-client
$ echo 'export PATH="/usr/local/opt/mysql-client/bin:$PATH"' >> ~/.bash_profile
$ export PATH="/usr/local/opt/mysql-client/bin:$PATH"
$ pip install mysqlclient
```

### Linux

**Note that this is a basic step.  I can not support complete step for build for all
environment.  If you can see some error, you should fix it by yourself, or ask for
support in some user forum.  Don't file a issue on the issue tracker.**

You may need to install the Python 3 and MySQL development headers and libraries like so:

* `$ sudo apt-get install python3-dev default-libmysqlclient-dev build-essential`  # Debian / Ubuntu
* `% sudo yum install python3-devel mysql-devel`  # Red Hat / CentOS

If you still experience errors from pip regarding 'legacy-install-failure' or 'Python.h: No such file or directory', you have to specify the correct python3-dev library for your python interpreter like so:

* `$ sudo apt-get install python3.10-dev`   # Debian / Ubuntu

instead of: 

* `$ sudo apt-get install python3-dev`   # Debian / Ubuntu 

Then you can install mysqlclient via pip now:

```
$ pip install mysqlclient
```

### Customize build (POSIX)

mysqlclient uses `mysql_config` or `mariadb_config` by default for finding
compiler/linker flags.

You can use `MYSQLCLIENT_CFLAGS` and `MYSQLCLIENT_LDFLAGS` environment
variables to customize compiler/linker options.

```
$ export MYSQLCLIENT_CFLAGS=`pkg-config mysqlclient --cflags`
$ export MYSQLCLIENT_LDFLAGS=`pkg-config mysqlclient --libs`
$ pip install mysqlclient
```

### Documentation

Documentation is hosted on [Read The Docs](https://mysqlclient.readthedocs.io/)
