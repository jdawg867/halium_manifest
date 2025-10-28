---
name: "Manifest Update / AOSP Merge"
about: Track merges, rebases, or syncs between Halium and AOSP versions
title: "[Manifest Update] Merge AOSP android-XX.X.X_rXX into dev/android-15"
labels: ["manifest-update", "merge-request"]
assignees: ""
---

## 🧩 Summary

Describe what this manifest update or merge does:

- [ ] AOSP Tag or Branch: `android-XX.X.X_rXX`
- [ ] Halium Branch: `dev/android-15`
- [ ] Merge Type: `merge` / `rebase`
- [ ] Source: `aosp/android-15.0.0_rXX` → `Halium/android`

---

## 🧱 Merge Details

**Command(s) used:**
```bash
git fetch aosp android-XX.X.X_rXX
git merge aosp/android-XX.X.X_rXX --allow-unrelated-histories
```

**Conflicts Encountered:**
- [ ] `default.xml`
- [ ] `snippets/halium-15.xml`
- [ ] `system/core/init`
- [ ] `build/make`
- [ ] `vendor/halium/hybris`
- [ ] Other: (list below)

Provide a short explanation of how each conflict was resolved.

---

## 🧪 Validation

**Checklist:**
- [ ] XML passes `xmllint --noout default.xml`
- [ ] `repo sync` completes successfully
- [ ] Verified basic build targets (`make -j16 bootimage`)
- [ ] Halium projects (`vendor/halium/hybris`, `external/libhybris`, etc.) sync correctly

**Test Device(s):**
_List any devices you synced or built against (optional)_

---

## 📋 Notes / Additional Context

_Add any notes, observations, or follow-up tasks (e.g. AIDL HAL updates, init JSON patches)._

---

> **Maintainer Guidance:**
> - If this merge passes validation, tag and close with a summary comment:
>   ```bash
>   ✅ Merge completed successfully.
>   Conflicts resolved: default.xml, build/make
>   Tests: repo sync OK, bootimage compiled
>   ```
> - Optionally tag the release:
>   ```bash
>   git tag -a v15.0.1 -m "Merged AOSP android-15.0.0_rXX"
>   git push --tags
>   ```
