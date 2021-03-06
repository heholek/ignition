# Supported Platforms #

Ignition is currently only supported for the following platforms:

* [Bare Metal] - Use the `ignition.config.url` kernel parameter to provide a URL to the configuration. The URL can use the `http://`, `https://`, `tftp://`, or `s3://` schemes to specify a remote config.
* [Amazon Web Services] - Ignition will read its configuration from the instance userdata. Cloud SSH keys are handled separately.
* [Microsoft Azure] - Ignition will read its configuration from the custom data provided to the instance. Cloud SSH keys are handled separately.
* [VMware] - Use the VMware Guestinfo variables `ignition.config.data` and `ignition.config.data.encoding` to provide the config and its encoding to the virtual machine. Valid encodings are "", "base64", and "gzip+base64". Guestinfo variables can be provided directly or via an OVF environment, with priority given to variables specified directly.
* [Google Compute Platform] - Ignition will read its configuration from the instance metadata entry named "user-data". Cloud SSH keys are handled separately.
* [Packet] - Ignition will read its configuration from the instance userdata. Cloud SSH keys are handled separately.
* [QEMU] - Ignition will read its configuration from the 'opt/com.coreos/config' key on the QEMU Firmware Configuration Device (available in QEMU 2.4.0 and higher).
* [DigitalOcean] - Ignition will read its configuration from the droplet userdata. Cloud SSH keys and network configuration are handled separately.
* [zVM] - Ignition will read its configuration from the reader device directly. The vmur program is necessary, which requires the vmcp and vmur kernel module as prerequisite, and the corresponding z/VM virtual unit record devices (in most cases 000c as reader, 000d as punch) must be set online.

Ignition is under active development, so this list may grow over time.

For most cloud providers, cloud SSH keys and custom network configuration are handled by [Afterburn] or by platform-specific agents.

[Bare Metal]: https://github.com/coreos/docs/blob/master/os/installing-to-disk.md
[Amazon Web Services]: https://github.com/coreos/docs/blob/master/os/booting-on-ec2.md
[Microsoft Azure]: https://github.com/coreos/docs/blob/master/os/booting-on-azure.md
[VMware]: https://github.com/coreos/docs/blob/master/os/booting-on-vmware.md
[Google Compute Platform]: https://github.com/coreos/docs/blob/master/os/booting-on-google-compute-engine.md
[Packet]: https://github.com/coreos/docs/blob/master/os/booting-on-packet.md
[QEMU]: https://github.com/qemu/qemu/blob/d75aa4372f0414c9960534026a562b0302fcff29/docs/specs/fw_cfg.txt
[DigitalOcean]: https://github.com/coreos/docs/blob/master/os/booting-on-digitalocean.md
[zVM]: http://www.vm.ibm.com/overview/

[Afterburn]: https://github.com/coreos/afterburn
