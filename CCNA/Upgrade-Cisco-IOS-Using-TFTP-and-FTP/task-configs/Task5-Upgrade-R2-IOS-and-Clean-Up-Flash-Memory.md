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

<img width="714" height="206" alt="T4-R2-show-flash" src="https://github.com/user-attachments/assets/9dda9e89-b29b-4f2f-9abc-2eae583ce3fb" />

### 2️⃣ Enter Global Config mode

```bash
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
When prompted, hit Enter

## 🧹 Clean Up Old IOS Image

### 5️⃣ Delete the Old IOS Image

In Priviliged EXEC mode:

```bash
delete flash:c2900-universalk9-mz.SPA.151-4.M4.bin
```

<img width="711" height="80" alt="T5-delete-old-os" src="https://github.com/user-attachments/assets/36a2b80f-0594-4345-b4ec-66ded2c9b8c4" />

When prompted, hit Enter

### 6️⃣ Verify Flash Cleanup

```bash
show flash
```

<img width="811" height="196" alt="Verify-flash" src="https://github.com/user-attachments/assets/e01c6cc4-7c9c-4b1a-bd25-3a8c4025a484" />

## ✅ Verification After Reload

### 1️⃣ Verify the New IOS Image Exists

#### 🟢 On R2 in Priviliged EXEC mode:

```bash
show version
```

<img width="811" height="196" alt="Verify-flash" src="https://github.com/user-attachments/assets/6b48eedf-aaa0-40b5-989e-d335c7a04a02" />
