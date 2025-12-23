# 🧹 Task 5 – Clear NAT Translations (Which Entries Remain?)

## 🎯 Goal
Clear the NAT translation table on **R1**, then check which NAT entries remain.

## Topology For Reference

<img width="648" height="227" alt="Topology" src="https://github.com/user-attachments/assets/9eff3467-85fb-40f2-a50c-a3eca4d670d2" />

---

## On R1

### 1️⃣ Check Current NAT Translations (Before Clearing)

In privileged EXEC mode:

```bash
show ip nat translations
```

**Expected Output✅**

<img width="791" height="304" alt="T4-check-NAT-translations" src="https://github.com/user-attachments/assets/d75b6dc7-4501-4942-a2b2-1c1e41371a6b" />

**📌 This shows the current NAT translation table after you generated traffic in Task 4.**

### 2️⃣ Clear the NAT Translation Table

```bash
clear ip nat translations *
```

**✅ This removes the **active/dynamic translation entries** created when hosts communicated with the internet.**

### 3️⃣ Check NAT Translations Again (After Clearing)

Run the show command again:

```bash
show ip nat translations
```

**Expected Output✅**

<img width="771" height="105" alt="NAT-translation-after-clear" src="https://github.com/user-attachments/assets/bbf6433b-0254-4c3a-98fe-004bb5a7ff75" />

After clearing:
- ✅ The **static NAT mappings remain**
- ❌ The dynamic entries that were created when the static mappings were used is gone.
