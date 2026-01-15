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

### ♦️ Verify the New IOS Image Exists

#### 🟢 On R1 in Priviliged EXEC mode:

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

### 4️⃣ Reload the Router

```bash
reload
```

Hit enter

## ✅ Verification After Reload

### 1️⃣ Verify the New IOS Image Exists

#### 🟢 On R1 in Priviliged EXEC mode:

```bash
show version
```

<img width="805" height="230" alt="T3-verify-new-OS" src="https://github.com/user-attachments/assets/0b478970-474f-4da2-9233-f6a3c35d9d97" />

## 🧹 Clean Up Old IOS Image

### 1️⃣ View Flash Contents

```bash
show flash:
```

<img width="733" height="199" alt="T2-verify-show-flash" src="https://github.com/user-attachments/assets/ed7cdc46-fb0e-46fd-8b29-6d63c17035b6" />

Note the old OS is File 3 (c2900-universalk9-mz.SPA.151-4.M4.bin). Copy the file

### 6️⃣ Delete the Old IOS Image

```bash
delete flash:c2900-universalk9-mz.SPA.151-4.M4.bin
```

<img width="698" height="81" alt="T3-delete-old-os" src="https://github.com/user-attachments/assets/8ca39e5c-315f-4cc4-948f-71595d983511" />

When prompted, hit Enter

### 7️⃣ Verify Flash Cleanup

```bash
show flash
```

<img width="650" height="190" alt="show-flash-R1-cleanup" src="https://github.com/user-attachments/assets/2b273d6e-6593-4a59-91a6-85c7660933ff" />
