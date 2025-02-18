# Upgrading Splunk Connect for Syslog

Splunk Connect for Syslog is updated regularly using a CI/CD development process.  The notes below outline significant changes that
must be taken into account prior and after an upgrade.  Ensure to follow specific instructions below to ensure a smooth
transition to a new version of SC4S in production.

## Upgrade process
Check the current version of SC4S by running ```sudo <docker or podman> logs SC4S```. For the latest version, use the
`latest` tag for the SC4S image in the sc4s.service unit file:
```
[Service]
Environment="SC4S_IMAGE=ghcr.io/splunk/splunk-connect-for-syslog/container:1"
```
Restart the service
```sudo systemctl restart sc4s```

Using the "1" version is recommended, but a specific version can be specified in the unit file if desired:
```
[Service]
Environment="SC4S_IMAGE=ghcr.io/splunk/splunk-connect-for-syslog/container:1.91.0"
```
See the [release information](https://github.com/splunk/splunk-connect-for-syslog/releases) for more detail.
