# **🧹 Delete Buff/Cache Automatically – Step-by-Step Guide**

This guide sets up an **automated Linux cache cleaning system** so your server stays fresh, light, and speedy — without manual intervention.

---

## **Step 1 – Test cache clearing manually**
Run this to clear the page cache:
```bash
sudo sync; echo 1 | sudo tee /proc/sys/vm/drop_caches
```
**💡 Run this and see memory changes or not.**
```bash
free -h
```

## **Step 2 – Update packages & install Nano editor**
```bash
sudo apt update
sudo apt install nano
```

## **Step 3 – (Optional) Install Nano in one line**
```bash
sudo apt update && sudo apt install nano -y
```

## **Step 4 – Create the cache clearing script**
```bash
sudo nano /usr/local/bin/clear_cache.sh
```

## **Step 5 – Add the script code**
**Paste this into the file:**
```bash
#!/bin/bash
sync
echo 3 > /proc/sys/vm/drop_caches
```
- sync → writes pending data to disk
- echo 3 → clears page cache, dentries, and inodes
**Save and exit:**
- CTRL+O → Enter → CTRL+X

## **Step 5 – Add the script code**



















