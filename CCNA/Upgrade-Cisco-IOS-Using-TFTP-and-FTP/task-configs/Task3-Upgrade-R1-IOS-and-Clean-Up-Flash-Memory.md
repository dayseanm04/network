# 🔄 Task 3 Upgrade R1 IOS and clean Up Flash Memory

## 📌 Objective
Upgrade **R1** to boot from the **new IOS image** that was transferred via TFTP, then **remove the old IOS image** from flash memory to free up space.

## Topology For Reference

<img width="545" height="196" alt="topology" src="https://github.com/user-attachments/assets/1895f9fd-c6d2-42f5-ba47-2e54b059671f" />

---
## 📁 IOS Image Details (R1)

| Item | Value |
|------|------|
| New IOS Image | **`c2900-universalk9-mz.SPA.155-3.M4a.bin`** |
| Location | `flash:` |
| Router | R1 |

---

## ⚙️ Step-by-Step Configuration (R1)

### 1️⃣ Verify the New IOS Image Exists

#### 🟢 On R1:

```bash
show flash:
```

<img width="733" height="199" alt="T2-verify-show-flash" src="https://github.com/user-attachments/assets/16a7ebff-3f81-4212-955b-0c719cf473d4" />

### 2️⃣ Enter Global Config mode
```bash
enable
configure terminal
```

### 3️⃣ Boot with the new version of IOS on R1

```bash
boot system flash:c2900-universalk9-mz.SPA.155-3.M4a.bin
end
```























