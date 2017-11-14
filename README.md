# sourcejedi.systemd-journal

Enable the systemd journal.

This role will remove rsyslog, unless configured otherwise.

This is written for installs which came with systemd, but did not configure the journal to write to persistent storage.  Often such systems (e.g. Debian) would be using rsyslog to write log files instead.

You can also grant read access to the journal for specified users.

This also works on Fedora, though you shouldn't have any need for it, unless you're managing a mixture of systems.


## Requirements

systemd should be installed and running :).

Also this role can add users to the systemd-journal group.  I recommend making sure the users are created before this role is run.  Otherwise this role will end up creating the users, which may not be what you expect.  For example the users will be created using the default setting for their home directories.


## Role Variables

* `systemd_journal__remove_syslog_daemon` - defaults to yes.
* `systemd_journal__users` - list of users to grant read access to the journal.


## See also

If you need to reduce the space used by the journal, see
[groks.systemd-journal](https://galaxy.ansible.com/groks/systemd-journal/).
By default, the journal is limited to 10% of filesystem capacity, or 4GB, whichever is smaller.
It should also limit itself when the filesystem hits 85% full.

## License

Apache License 2.0
