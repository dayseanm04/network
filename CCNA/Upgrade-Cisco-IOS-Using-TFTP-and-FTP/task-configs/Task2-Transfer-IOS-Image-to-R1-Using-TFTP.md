# 📤 Task 2 Transfer IOS Image to R1 Using TFTP

## 📌 Objective

Use **TFTP** on **R1** to download a new **Cisco IOS image** from **SRV1** and store it in **R1’s flash memory**.

---

## 🧠 Simple Explanation
- **TFTP** is a lightweight file transfer protocol
- It does **not use authentication**
- The router pulls the IOS image directly from the server
- Connectivity must already be working (verified in Task 1)

## Topology For Reference

<img width="545" height="196" alt="topology" src="https://github.com/user-attachments/assets/1895f9fd-c6d2-42f5-ba47-2e54b059671f" />

---

## 📁 IOS Image Information

| Item | Value |
|----|----|
| IOS File | `c2900-universalk9-mz.SPA.155-3.M4a.bin` |
| Transfer Method | TFTP |
| Source Device | SRV1 |
| Destination Device | R1 |
| Destination Location | Flash |

---

## ⚙️ TFTP Transfer Configuration (Exact Commands)

#### 1️⃣ Enter Priviliged EXEC mode on R1:

```bash
enable
```

#### 2️⃣ Retrieve the file with TFTP

```bash
copy tftp: flash:
```

<img width="779" height="344" alt="T2-TFTP" src="https://github.com/user-attachments/assets/af43610e-9055-49e8-b990-796edb14bca2" />

#### 🟢 When prompted, enter the following: When prompted, enter the following:

- Address or name of remote host []? **`10.0.0.1`**
- Source filename []? **`c2900-universalk9-mz.SPA.155-3.M4a.bin`**
- Destination filename [**`c2900-universalk9-mz.SPA.155-3.M4a.bin`**]? <Hit Enter>

**Note:** ⏳ The transfer may take some time. Do not interrupt the process.

## ✅ Verify IOS Image Was Transferred

```bash
show flash
```

<img width="733" height="199" alt="T2-verify-show-flash" src="https://github.com/user-attachments/assets/1b9a7edb-b21e-45ca-8ae5-a8103dd3b842" />













