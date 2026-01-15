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

## ⚙️ FTP Transfer Configuration

#### 1️⃣ Enter GlobalConfig mode on R2:

```bash
enable
conf t
```


