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

