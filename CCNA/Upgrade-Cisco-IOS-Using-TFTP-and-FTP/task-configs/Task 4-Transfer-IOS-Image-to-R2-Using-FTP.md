# 📤 Task4 Transfer IOS Image to R2 Using -FTP

## 📌 Objective
Use **FTP** on **R2** to download a new **Cisco IOS image** from **SRV1** and store it in **R2’s flash memory**.

✅ FTP requires authentication:

- **Username:** `jeremy`
- **Password:** `ccna`

⏱️ *Note:* The transfer may a couple of minutes.

## Topology For Reference

<img width="545" height="196" alt="topology" src="https://github.com/user-attachments/assets/1895f9fd-c6d2-42f5-ba47-2e54b059671f" />

---


## 📁 IOS Image Information

| Item | Value |
|----|----|
| IOS File | **`c2900-universalk9-mz.SPA.155-3.M4a.bin`** |
| Transfer Method | FTP |
| Source Device | SRV1 |
| FTP Username | jeremy |
| FTP Password | ccna |
| Destination Device | R2 |
| Destination Location | Flash |

---

- Click on the SRV1
- Click on Services
- Click on FTP

<img width="953" height="378" alt="T4-FTP-SRV" src="https://github.com/user-attachments/assets/208e8f44-5d01-441e-85b1-3b700f1efe8c" />



## ⚙️ FTP Transfer Configuration

### 1️⃣ Enter Global Config mode on R2:

```bash
enable
conf t
```

### 2️⃣ Configure FTP username of password

```bash
ip ftp username jeremy 
ip ftp password ccna
```





