# Services

systemd services are a way of starting (and  re-starting) a service.
A process that's set up as a systemd service will automatically be integrated
the [journald logging service](https://man7.org/linux/man-pages/man8/systemd-journald.8.html),
can be started and stopped using [systemctl](https://man7.org/linux/man-pages/man1/systemctl.1.html),
and can be automatically re-started if it fails or if the system re-starts.


## Unit File

Services are configured with unit files. An example/template follows. Consult the manpages for
detailed configuration options.


```conf
[Unit]
Description=Short and Specific Human-Readable Description
After=network.target
StartLimitIntervalSec=1

[Service]
Type=exec
Restart=always
RestartSec=1
User=<user to run as>
ExecStart=<absolute path to service executable>
WorkingDirectory=<where to run the service>
Environment=<list of "VAR=VAL" environment variables>

[Install]
WantedBy=multi-user.target
```

These files live in `/etc/systemd/system/`.


## Setup

```shell
systemctl daemon-reload  # get unit file into systemd
systemctl start <servicename>  # start the service
systemctl enable <servicename>  # start unit automatically on server restart
```


## Management

See service status

```shell
systemctl status <servicename>
```

Get service logs

```shell
journalctl -u <servicename>
```

## References

* [systemd.service manpage](https://man7.org/linux/man-pages/man5/systemd.service.5.html)
* [systemd.unit manpage](https://man7.org/linux/man-pages/man5/systemd.unit.5.html)
