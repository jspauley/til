# View Journal System Logs

In Linux, `systemd` does an excellent job logging and managing all kernal and user level services. These centralized logs can be very helpful in debugging services and understanding what the system is doing. 

To view the `systemd` log journal, run:

```bash
journald
```

Alternatively, to jump to the end of the `systemd` log journal, run:

```bash
journald -e
```

A more comprehensive tutorial prepared by DigitalOcean on all the features of this journal is available [here](https://www.digitalocean.com/community/tutorials/how-to-use-journalctl-to-view-and-manipulate-systemd-logs).
