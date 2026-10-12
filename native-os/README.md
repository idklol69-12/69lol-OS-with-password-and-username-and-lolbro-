# 69LolOS native ARM64 work

This folder is for the **native-OS experiment**. The existing `index.html` desktop is intentionally left unchanged.

## What the automated build does

The GitHub Actions workflow `.github/workflows/arm64-prototype.yml` builds a minimal ARM64 Linux system using Buildroot's `qemu_aarch64_virt_defconfig`. It uploads the resulting kernel and root-filesystem images as a GitHub Actions artifact.

## Important limitations

- This first target is **QEMU's virtual ARM64 machine**, not the HP OmniBook's Snapdragon hardware.
- A successful build is not proof that it boots on the laptop.
- It does not yet include the 69LolOS blue desktop, its apps, or a hardware-specific boot configuration.
- Do not replace Windows, repartition the internal drive, or change Secure Boot settings for this prototype.
- The workflow is manually runnable from **Actions → Build 69LolOS ARM64 prototype → Run workflow**. It also runs when files in this folder or the workflow itself change.

## Next milestones

1. Confirm that GitHub Actions can build the ARM64 kernel and root filesystem.
2. Test the produced image in an ARM64 QEMU environment.
3. Investigate the laptop's UEFI, ACPI, storage, Wi-Fi, graphics, and Snapdragon platform support.
4. Only then design a separate, non-destructive USB test path.
5. Port the 69LolOS desktop into the native environment after the base system works.

This is a build experiment, not a finished or tested bootable 69LolOS release.
