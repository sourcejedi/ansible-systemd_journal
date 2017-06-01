# sourcejedi.systemd-journal

Enable the systemd journal.

This role will remove rsyslog, unless configured otherwise.

This is written for installs which came with systemd, but did not configure the journal to write to persistent storage.  Often such systems (e.g. Debian) used rsyslog to write log files.

## Requirements

systemd :).

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
