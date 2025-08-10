# **🧹 Delete Buff/Cache Automatically – Step-by-Step Guide**

This guide sets up an **automated Linux cache cleaning system** so your server stays fresh, light, and speedy — without manual intervention for all kinds of node.
#### **(read for) gensyn only:** others ignore it
it barely works if you have only 16GB of RAM, so for better perforamce choose more than 16GB RAM, (20GB is enough)

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

## **Step 6 – Make the script executable**
```bash
sudo chmod +x /usr/local/bin/clear_cache.sh
```

## **Step 7 – Install Cron for automation**
```bash
sudo apt update && sudo apt install cron -y
```

## **Step 8 – Edit root crontab bash Copy Edit**
```bash
sudo crontab -e
```
**Select 1 for Nano when prompted.**


## **Step 9 – Schedule automatic cache clearing (Most Important)**
paste at last 
 **this is for clear every 3 minutes**
```bash
*/3 * * * * /usr/local/bin/clear_cache.sh
```

**💡 For hourly:**
```bash
0 * * * * /usr/local/bin/clear_cache.sh
```
**Save and exit:**
- CTRL+O → Enter → CTRL+X
---

## **✅ Done! Your system will now automatically free RAM on schedule.**
## **📌 Tip: Avoid setting too short an interval — frequent clearing can hurt performance.**


---


### **🙏 Thank you for using this project!**
This GitHub repo is proudly built and maintained by Blynq. Your support and contributions mean a lot!
