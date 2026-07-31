
# PostmarketOS_pipa_builder
[![Build postmarketOS for xiaomi-pipa](https://github.com/SlimKen/postmarketos_pipa_builder/actions/workflows/pmos-build.yml/badge.svg)](https://github.com/SlimKen/postmarketos_pipa_builder/actions/workflows/pmos-build.yml)

A workflow to build the latest PostmarketOS for the Xiaomi Pad 6 (pipa) for testing purposes.

Find out what is working and more info here: https://wiki.postmarketos.org/wiki/Xiaomi_Pad_6_(xiaomi-pipa)

## Contents of the release
 
 | File | Description |
 |------|-------------|
 | `xiaomi-pipa.img` | Root filesystem image |
 | `u-boot-xiaomi-pipa.img` | U-boot EFI image |

If the archive is split into multiple `.7z` parts, download all of them before extracting.
Extract with: `7z x pmos-xiaomi-pipa.7z` (or `pmos-xiaomi-pipa.7z.001` if split)

## Flashing instructions

Prerequisites: unlocked bootloader, fastboot installed on your PC.

```sh
# Boot into fastboot mode by Powering off the device first, then hold Volume Down + Power

fastboot erase dtbo
fastboot flash boot u-boot-xiaomi-pipa.img
fastboot flash userdata xiaomi-pipa-root.img
# Do not use hardware buttons to reboot, it could brick the device
fastboot reboot

```
