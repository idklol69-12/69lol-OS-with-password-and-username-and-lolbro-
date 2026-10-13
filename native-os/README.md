# 69LolOS — Complete ARM64 QEMU build

This build target is a **standalone ARM64 Linux operating system for QEMU's virtual ARM64 machine**. The existing 69LolOS blue browser desktop in `index.html` is intentionally left unchanged.

## What the QEMU build includes

- ARM64 Linux kernel and a root filesystem
- Console login / shell environment
- Bash, Nano, htop and Python 3
- SSH server, curl, wget, IP networking tools and CA certificates
- EXT4 disk image, plus CPIO/TAR root filesystem outputs when produced by Buildroot
- An automated QEMU boot smoke test in GitHub Actions

The downloadable workflow artifact is named **`69LolOS-ARM64-QEMU-complete`**. It contains boot files for QEMU, not a Windows installer.

## Build and download

1. Open the repository's **Actions** tab.
2. Select **Build 69LolOS ARM64 for QEMU**.
3. Open a successful run and download **`69LolOS-ARM64-QEMU-complete`** under Artifacts.

The workflow builds the system and checks whether it reaches the Buildroot welcome/login prompt in QEMU. A successful build alone is not enough; the QEMU smoke test must also pass.

## Important limits

- This is a complete **console-based Linux environment for QEMU**, not yet the finished 69LolOS graphical desktop or a complete OS for the HP OmniBook Snapdragon hardware.
- The QEMU virtual hardware differs from the laptop. Do not copy this image to the laptop's internal drive, repartition Windows, or change Secure Boot settings.
- The existing `index.html` desktop and Pages site are not replaced by this native OS experiment.
- The next stage after a passing QEMU test is adding a graphical desktop and adapting the boot/hardware support separately for the target laptop.

This is the QEMU target being built and tested; do not describe it as laptop-ready until hardware compatibility has been implemented and tested.
