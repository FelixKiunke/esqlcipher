Esqlcipher

An Erlang nif library for sqlcipher.

Introduction
------------

This library allows you to use the excellent sqlite engine from
erlang. The library is implemented as a nif library, which allows for
the fastest access to a sqlite database. This can be risky, as a bug
in the nif library or the sqlite database can crash the entire Erlang
VM. If you do not want to take this risk, it is always possible to
access the sqlite nif from a separate erlang node.

Special care has been taken not to block the scheduler of the calling
process. This is done by handling all commands from erlang within a
lightweight thread. The erlang scheduler will get control back when
the command has been added to the command-queue of the thread.

On the Author(s)
----------------

This version is derived from Maas-Maarten Zeeman’s Erlang sqlite
library [esqlite](https://github.com/mmzeeman/esqlite).
I (Felix Kiunke) merely made some smaller amendments to provide
support for sqlcipher, a library that provides encryption for sqlite
databases.