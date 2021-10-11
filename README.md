# sourcejedi.systemd_journal

Enable the systemd journal.

This role will disable rsyslog, unless configured otherwise.

This is intended for installs which came with systemd, but did not configure the journal to write to persistent storage.  This includes Ubuntu 17.10 or earlier, and Debian 10 or earlier.  Typically such systems use rsyslog to write log files instead.

You can also grant read access to the journal for specified users.


## Requirements

systemd should be installed and running :).

Also, this role can add users to the systemd-journal group.  I recommend making sure the users are created before this role is run.  Otherwise this role will end up creating the users, which is probably not what you wanted.


## Role Variables

* `systemd_journal__disable_syslog_daemon` - defaults to yes.
* `systemd_journal__users` - list of users to grant read access to the journal.


## See also

If you need to reduce the space used by the journal, see
[groks.systemd-journal](https://galaxy.ansible.com/groks/systemd-journal/).
By default, the journal is limited to 10% of filesystem capacity, or 4GB, whichever is smaller.
It should also limit itself when the filesystem hits 85% full.

## License

Apache License 2.0
