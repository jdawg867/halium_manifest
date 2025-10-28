# 🧩 Pull Request — Halium 15 Manifest

## 📋 Summary

**Type of change:**
- [ ] AOSP Merge / Rebase
- [ ] Manifest Fix / Update
- [ ] Feature / Enhancement
- [ ] Cleanup / Maintenance

**Target Branch:**  
`dev/android-15`

---

## 🧱 Description

Explain **what** this PR changes and **why**.  
Example:
> Merged AOSP tag android-15.0.0_r38 into dev/android-15.  
> Resolved conflicts in default.xml and vendor/halium/hybris.

---

## 🧪 Validation Checklist

- [ ] XML validated (`xmllint --noout default.xml`)
- [ ] Repo sync completes successfully
- [ ] Build test (e.g. `make -j16 bootimage`) passes
- [ ] Verified Halium projects sync:  
  - [ ] vendor/halium/hybris  
  - [ ] external/libhybris  
  - [ ] hardware/halium  
- [ ] Conflicts resolved cleanly
- [ ] No removed essential AOSP remotes

---

## 📦 Details

**AOSP Tag (if applicable):** `android-15.0.0_rXX`  
**Merge Type:** `merge` / `rebase`  
**Conflicts handled in:**  
`default.xml`, `system/core/init`, `vendor/halium/hybris`, etc.

---

## 🧩 Related Issues or Requests

Link related issues or discussions:
```
Fixes #<issue-number>
Refs #<related-issue>
```

---

## 🧠 Additional Notes

_Add any background context, post-merge actions, or follow-up steps (e.g. new snippet addition, Halium sync test, device bring-up)._


---

**Maintainer Check before merge:**
- [ ] Reviewed and approved
- [ ] CI / test build confirmed
- [ ] Branch verified: `dev/android-15`
- [ ] Ready for squash & merge

---
