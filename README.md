# sourcejedi.systemd-journal

Enable the systemd journal.

This role will remove rsyslog, unless configured otherwise.

Written for systems which came with the journal installed, but did not configure it to write to persistent storage.  Often they use the rsyslog package instead.

## Status

Used sucessfully on Fedora and Debian.

## Requirements

systemd

## Role Variables

`systemd_journal__remove_syslog_daemon`


## See also

If you need to reduce the space used by the journal, see
[groks.systemd-journal](https://galaxy.ansible.com/groks/systemd-journal/).
By default, the journal is limited to 10% of filesystem capacity, or 4GB, whichever is smaller.
It is also supposed to limit itself somehow, when the filesystem hits 85% full.

There's another role which includes adding users to the group for reading the journal (systemd-journal).
I think it's probably a good feature to have, I just didn't happen to need it.
Poke me if you did, in the mean time you could look at
[znz.journald](https://galaxy.ansible.com/znz/journald/).

## License

Apache License 2.0
