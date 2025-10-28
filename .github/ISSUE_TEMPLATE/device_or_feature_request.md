---
name: "Device or Feature Request"
about: Propose a new device tree, vendor overlay, or Halium feature addition
title: "[Feature] Add <device/feature-name>"
labels: ["feature-request", "enhancement"]
assignees: ""
---

## 🔧 Summary

Describe the feature or device you’d like to add.

Example:
> Add support for Pixel 9 Pro Fold (comet) using AOSP 15 vendor base.

---

## 🧱 Details

- [ ] Device Codename (if applicable): `<codename>`
- [ ] Android Base Version: `15.0.0_r36`
- [ ] Vendor Source: `<URL or repo>`
- [ ] Kernel Source: `<URL or repo>`
- [ ] Type: `device` / `vendor` / `hardware` / `integration`

---

## 🧪 Testing Status

- [ ] Synced successfully with `repo sync`
- [ ] Booted to LXC or system shell
- [ ] Verified binder communication
- [ ] Graphics / EGL works
- [ ] Audio HAL functional

---

## 🧩 Additional Context

_Add any notes, dependencies, or related issues._

---

> Maintainers: please review whether the device/vendor should be tracked directly in manifest or handled through `local_manifests/`.
