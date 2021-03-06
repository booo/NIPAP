Configuration of the NIPAP backend (nipapd)
===========================================
Make sure nipapd is installed.

nipapd will not be able to start until it can connect to the backend database
and as postgresql does not by default listen to localhost (127.0.0.1), you will
need to edit /etc/postgresql/9.1/main/postgresql.conf and uncomment the
listen_address line to have it listen to localhost (or all '*').

If you installed nipapd using the Debian packages, it prompted you to
automatically setup the database connection in which case you should not need
to do anything further but (re)start nipapd. If you installed nipapd manually,
you will need to fill in your database connection parameters in nipap.conf
yourself.

Once done, restart nipapd::

    /etc/init.d/nipapd restart

Per default, nipapd itself only listens to localhost (127.0.0.1). If you are
going to run the web UI on the same machine and/or the CLI from the same
machine, you do not need to change anything. If you on the other hand wish to
run any of these from a second machine, you need to change the "listen" line in
nipap.conf.
for it to listen on all addresses, change the "listen" line in nipap.conf.
