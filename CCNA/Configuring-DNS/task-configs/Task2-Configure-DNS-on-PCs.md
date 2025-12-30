# 🖥️ Task 2 – Configure DNS on PCs (PC1, PC2, PC3)

## 🎯 Goal
Configure **PC1, PC2, and PC3** to use **1.1.1.1** as their **DNS server**.  
This allows the PCs to resolve **domain names** (like `youtube.com`) into IP addresses.


## 🧠 Why This Matters
- Computers use **DNS** to translate names into IP addresses
- Without a DNS server, name-based commands (like `ping youtube.com`) will fail
- `1.1.1.1` is a public DNS server (Cloudflare)

## Topology For Reference

<img width="626" height="254" alt="Topology" src="https://github.com/user-attachments/assets/7c66d56e-4913-4f1f-97fa-fa7b65588bf3" />

---

## ✅ Configure PC1, PC2, and PC3

### 1️⃣ Open the PC Configuration

- Click the PC (PC1, PC2, or PC3)
- Go to the **Desktop** tab
- Click **IP Configuration**

---

### 2️⃣ Configure the DNS Server
- Locate the **DNS Server** field
- Enter: **1.1.1.1**

### 3️⃣ Verify DNS Configuration (Optional but Recommended)
- Go to **Desktop**
- Open **Command Prompt**
- Run: **ipconfig /all**

#### ♦️ PC1 ipconfig /all

<img width="876" height="475" alt="PC1-ipconfig-all" src="https://github.com/user-attachments/assets/644e0f43-e7a1-4c8f-8083-f9d68a1cb174" />

#### ♦️ PC2 ipconfig /all

<img width="862" height="469" alt="PC2-ipconfig-all" src="https://github.com/user-attachments/assets/f8893e2d-faab-4459-92aa-8482d10fb12e" />

#### ♦️ PC3 ipconfig /all

<img width="907" height="442" alt="PC3-ipconfig-all" src="https://github.com/user-attachments/assets/a19bf51c-fc70-4ad7-aff8-d9e0f1d1467c" />



