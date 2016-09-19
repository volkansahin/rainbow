Rainbow
=======

**Easily colorize logs or commands output using patterns.**
::

  rainbow [ --COLOR=PATTERN ... | --conf CONF ] COMMAND


Examples
--------

Using patterns
~~~~~~~~~~~~~~
Just prepend ``rainbow`` with ``COLOR=PATTERN`` associations to your
command, for example:

-  Tail some log file with lines containing ``ERROR`` in red:
   ::

     rainbow --red='.*ERROR.*' -- tail -f /var/log/my.log

-  Ping Google with IP addresses colorized in yellow:
   ::

     rainbow --yellow='\d{1,3}\.\d{1,3}\.\d{1,3}\.\d{1,3}' -- ping www.google.com

-  Rainbow can also read from STDIN instead of providing a command:
   ::

rainbow --red='ERROR.*' --green='INFO.*' --yellow='WARNING.*' --magenta='DEBUG.*' -- tail -f /var/log/ahenk.log

     tail -f /var/log/my.log | rainbow --red='.*ERROR.*'

Using confs
~~~~~~~~~~~

Rainbow can read ``COLOR=PATTERN`` associations from config files, which
is the most common way to use it. It automatically uses the config file
if there is one named after the command name in ``~/.rainbow``, or a builtin one:

-  Colorize the ``diff`` command output using the builtin config:
   ::

     rainbow diff file1 file2

-  Start JBoss application server with colorized logs:
   ::

     rainbow --config=jboss -- jboss/bin/run.sh run

The syntax for writing configs is very simple. See the
`builtin configs <https://github.com/nicoulaj/rainbow/blob/master/configs>`_
for examples.


Installation
------------

Using packages
~~~~~~~~~~~~~~

- Ubuntu/Debian based distributions: coming soon.
- Arch Linux : `AUR/rainbow <https://aur.archlinux.org/packages.php?ID=54146>`_ / `AUR/rainbow-git <https://aur.archlinux.org/packages.php?ID=54147>`_.

Building from sources
~~~~~~~~~~~~~~~~~~~~~

You can build from sources this way:

::

    git clone git://github.com/nicoulaj/rainbow.git
    cd rainbow
    sudo python setup.py install


License
-------

This project is a fork of `Linibou's colorex <http://bitbucket.org/linibou/colorex>`_.
It is is released under the terms of the `GNU General Public
License <http://www.gnu.org/licenses/gpl.html>`_. See ``COPYING`` for
details.
