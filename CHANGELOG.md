# Changelog

All notable changes to avocado-ext-sshd-dev are documented in this file.
The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.1.1]

### Added
- sshd also reads authorized keys from `/var/lib/ssh/authorized_keys.d/<user>`
  (`/etc/ssh/sshd_config.d/50-avocado-authorized-keys.conf`). The root
  filesystem is read-only, so `~/.ssh/authorized_keys` cannot be written for
  root; `/var` is writable and survives reboots and OS updates. Ship keys with
  the runtime's `var_files` or write them at provisioning.
- CI builds against the 2026 feed as well as 2024.

## [0.1.0]

### Added
- Initial release: SSH server with root login.
- CI via the shared `avocado-linux/actions` reusable workflows: PR build check
  (`test.yml`) and tag-driven package + publish to the Avocado feed (`release.yml`).
