# ESPHome privileged hardening fixture

Minimal ESPHome Device Builder fixture derived from the upstream Docker
deployment shape. It deliberately requests `privileged: true`, host networking,
a published port, a fixed container name, and a repository bind mount.

The PanelTutor Apps hardener must remove those host capabilities, run the
official ESPHome image as a non-root user with a read-only root filesystem, and
keep the dashboard functional on the internal Compose network.

This fixture exercises the dashboard only. USB flashing, host mDNS discovery,
and access to physical devices are intentionally unavailable after hardening.
