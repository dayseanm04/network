# 📘 Understanding EIGRP Unequal-Cost Load Balancing (Simple Explanation)

If you feel confused about **variance**, **FD**, **successor**, **feasible successor**, and the rest, don’t worry.  
These terms sound complicated, but they become easy once you understand how EIGRP chooses paths.

Below is a simple, clear explanation.

---

## 🧠 EIGRP Chooses the Best Path BUT Can Use Backup Paths Too

EIGRP normally picks **one best path** (the lowest metric).  
But unlike OSPF or RIP, EIGRP can also use **backup paths** *at the same time* to load-balance, even if those paths have **unequal costs**.

To do that safely, EIGRP uses some important rules and terms.

---

# 🔑 Terms You Must Understand

## 1️⃣ **Successor** (Primary / Best Path)

This is the **best** path to a destination, the one with the **lowest metric**.
- It is ALWAYS placed in the routing table.
- It is ALWAYS used for forwarding traffic.

👉 Think of the successor as **your “fastest route to school.”**

---

## 2️⃣ **Feasible Distance (FD)**

This is the **metric of the successor**, the best possible metric EIGRP has for a route.
- Every other path is compared to the FD.
- FD = The “gold standard” path.

👉 If the successor route has a metric of **10,000**, then FD = **10,000**.

---

## 3️⃣ **Reported Distance (RD)** (Also called Advertised Distance)

RD = What the *neighbor* router says its metric is to reach the destination.
<br/>
- Your router uses this to check whether a path is safe to use.

👉 Example:  
A neighbor may report an RD of **8,000**.

---

## 4️⃣ **Feasible Successor (FS)** (Backup Path)

A **feasible successor** is a backup path that EIGRP considers *safe* to use.  <br/>
It must satisfy the **Feasibility Condition:**
<br/>
### ✔ **Reported Distance (RD )< Feasible Distance (FD)**

**Meaning:**

- The neighbor must report a metric **smaller than the FD** of your best path.

If this is true → the path is LOOP-FREE → eligible as a backup.

👉 Think of a feasible successor as a **slightly slower but guaranteed safe alternate route.**

If **Reported Distance (RD ) ≥  Feasible Distance (FD)**, the path is **not safe**, and EIGRP will NOT use it, even with variance.

---

# ⚖️ What Is Variance?

`variance` is a multiplier that allows EIGRP to use **unequal-cost** paths for load balancing.

### ✔ Without variance → EIGRP uses only equal-cost paths.  
### ✔ With variance → EIGRP can use backup paths that are *worse* than the best path but still within an acceptable range.

### Formula:

Feasible Successor Metric ≤ (FD × variance)


Example:

- FD (best path) = **10,000**
- FS metric = **15,000**
- Variance = **2**
- Allowed maximum = 10,000 × 2 = **20,000**

Since 15,000 ≤ 20,000 → **EIGRP will use the FS for load balancing.**

---

# ❗ Important: Variance Does NOT Guarantee Load Balancing

Even if you set: variance 128

EIGRP **will NOT** use another path unless BOTH conditions are true:

### ✔ The path must be a **Feasible Successor (RD < FD)**  
### ✔ The path’s metric must be within **FD × variance**

If either condition fails → EIGRP rejects the path.

---

# 🔄 Why Does EIGRP Require RD < FD?

This protects against **routing loops**.

---

# 📊 Simple Example (Easy to Visualize)

### Router R1 has two paths to network 192.168.4.0:

| Path | Metric | RD < FD? | Eligible? |
|------|--------|----------|-----------|
| Path A (successor) | 10,000 | — | YES |
| Path B (backup) | 18,000 | RD < FD → YES | If variance ≥ 2 |

If variance = 2:

FD × variance = 10,000 × 2 = **20,000**  
Backup = **18,000 ≤ 20,000** → **Used for load balancing**

If variance = 1:

FD × 1 = **10,000**  
Backup = **18,000 > 10,000** → **Not used**

---

# 🎉 Summary 

- **Successor** = best path.
- **Feasible Distance (FD)** = metric of successor.
- **Reported Distance (RD)** = metric reported by neighbor.
- **Feasible Successor (FS)** = safe backup path because `RD < FD`.
- **Variance** = allows EIGRP to use FS paths even if they have higher metrics.

### ✔ Unequal-cost load balancing works ONLY when:
1. Path is a **Feasible Successor** (RD < FD)  
2. Path metric ≤ FD × variance  

If either condition fails → EIGRP will NOT use the path.

---

**Variance allows EIGRP to use more than one path, but only if those paths are loop-free (RD < FD) and their metrics fit within the FD × variance limit.**

