# Contributing to the Halium 15 Manifest Project

This repository hosts the **Halium 15 manifest**, rebased on **AOSP 15.0.0_r36**.  
It integrates Halium’s core layers (hybris, libhybris, device/halium, hardware/halium) into the Android 15 platform.

Please follow this workflow and branching policy to ensure stability and reproducibility.

---

## 🧭 Branch Workflow

| Branch | Purpose | Description |
|--------|----------|-------------|
| **master** | Stable base | Always points to the latest clean, syncable manifest. Used for public reference (`repo init -u … -b master`). |
| **dev/android-15** | Active development | All feature work, AOSP merges, and Halium integration changes occur here. Consider it rolling. |
| **release/halium-15.0** | Frozen release | Snapshot of a known-good, bootable, and verified manifest. Tagged (e.g. `v15.0.0`). |

---

## 🛠️ Contribution Process

1. **Fork this repository** on GitHub.  
2. **Create a feature branch** from `dev/android-15`:
   ```bash
   git checkout -b feature/<short-description> origin/dev/android-15
   ```
3. **Make and test your changes**  
   - Validate XML syntax:
     ```bash
     xmllint --noout default.xml
     ```
   - Verify a clean repo sync:
     ```bash
     repo init -u https://github.com/<yourname>/android.git -b dev/android-15
     repo sync -j16
     ```
4. **Commit and push** your branch:
   ```bash
   git add .
   git commit -m "Brief, clear summary of change"
   git push origin feature/<short-description>
   ```
5. **Open a Pull Request** on GitHub → target branch `dev/android-15`.

---

## 🧩 Merge and Release Rules

- PRs **must target `dev/android-15`** unless they are emergency hotfixes.  
- Only maintainers may merge into `master` or `release/*`.  
- When a dev branch reaches stability:
  ```bash
  git checkout dev/android-15
  git checkout -b release/halium-15.0
  git push origin release/halium-15.0
  git tag -a v15.0.0 -m "First stable Halium 15 manifest release"
  git push --tags
  ```
- The `release/halium-15.0` branch becomes read-only once tagged.

---

## 🧠 Technical Guidelines

- Indentation: **2 spaces** for all XML files.  
- Keep `<remote>` and `<project>` elements alphabetized when possible.  
- Use HTTPS for all remote URLs.  
- Do **not** include proprietary device/vendor projects here — use a separate `local_manifests/` overlay.  
- When merging a new AOSP tag:
  ```bash
  git fetch aosp android-15.0.0_rXX
  git merge aosp/android-15.0.0_rXX --allow-unrelated-histories
  ```
  Resolve conflicts in `default.xml`, keeping Halium additions intact.

---

## 🔀 Branch Policy (Quick Reference)

```text
master           →  Stable public branch
dev/android-15   →  Active development branch
release/halium-15.0 →  Frozen release branch
```

Typical flow:

```bash
# Work on dev branch
git checkout -b feature/fix-init-json origin/dev/android-15
# Push feature branch
git push origin feature/fix-init-json
# Then open a PR to dev/android-15
```

---

## 🧩 Communication

For large changes (e.g., new AOSP merges, Halium 16 migration),
open a GitHub Discussion or Issue first to coordinate work and prevent conflicts.

---

## 🧱 Repository Lineage

- **Base:** AOSP 15.0.0_r36  
- **Halium lineage:** halium-12.0 → halium-15.0 → halium-16.0  
- **Maintainer:** James M. Freeman

---

_Thanks for contributing to the Halium project!_
