# 🔄 Task 5 Upgrade R2 IOS and Clean Up Flash Memory

## 📌 Objective

Upgrade **R2** to boot from the **new IOS image** that was transferred via FTP, then **delete the old IOS image** from flash to free up space.

## Topology For Reference

<img width="545" height="196" alt="topology" src="https://github.com/user-attachments/assets/1895f9fd-c6d2-42f5-ba47-2e54b059671f" />

---

## 📁 IOS Image Details (R2)

| Item | Value |
|------|------|
| New IOS Image | **`c2900-universalk9-mz.SPA.155-3.M4a.bin`** |
| Location | `flash:` |
| Router | R2 |

---

## ⚙️ Step-by-Step Configuration (R2)

### ♦️ Verify the New IOS Image Exists

#### 🟢 On R2 in Priviliged EXEC mode:

```bash
show flash:
```

<img width="714" height="206" alt="T4-R2-show-flash" src="https://github.com/user-attachments/assets/bc0f8a3f-dae3-499d-8c3a-107d9106e953" />

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

<img width="711" height="80" alt="T5-delete-old-os" src="https://github.com/user-attachments/assets/41598a9f-9058-422b-af04-14bf7b7d028b" />


### 4️⃣ Reload the Router

```bash
reload
```

When prompted, hit Enter

Hit enter

## ✅ Verification After Reload

### 1️⃣ Verify the New IOS Image Exists

#### 🟢 On R1 in Priviliged EXEC mode:

```bash
show version
```

<img width="969" height="240" alt="T5-verify-new-OS" src="https://github.com/user-attachments/assets/5e1fe2a0-b78e-46a7-a7a6-3dd7bb3b0d33" />
















