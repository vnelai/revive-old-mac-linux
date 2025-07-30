# 📶 Fixing Broadcom BCM4331 Wi-Fi on Ubuntu MATE

After installing Ubuntu MATE on a 2011 MacBook Pro, Wi-Fi didn’t work. Here’s what caused it and how I fixed it.

## ❌ The Problem

- Kernel 6.8 was too new  
- Broadcom BCM4331 needs bcmwl-kernel-source, but it wouldn’t compile  
- No internet = no easy fix

## ✅ The Solution

1. Reflashed with Ubuntu MATE 22.04.3, which uses kernel 5.15 LTS  
2. On first boot, Wi-Fi worked immediately

Why? This version includes supported kernel headers and a compatible DKMS setup for Broadcom’s proprietary driver.

## 🔒 Why Broadcom Is Tricky

Broadcom chips require closed-source drivers that are often excluded from Linux distributions.  
Open-source options don’t fully support all models or may be unstable.

bcmwl-kernel-source builds the correct proprietary driver, but only if the kernel version is supported.
