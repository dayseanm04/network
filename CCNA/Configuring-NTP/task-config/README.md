## Topology For Refernece

<img width="648" height="256" alt="topology" src="https://github.com/user-attachments/assets/e30bc4fe-1d0b-480f-82fd-509165d35916" />


## 📋 Task Breakdown

| Task | File Name | Description |
|-----|----------|-------------|
| ⏰ **Task 1** | [**Task1-Configure-Software-Clock.md**](Task1-Configure-Software-Clock.md) | Configure the software clock on R1, R2, and R3 to **12:00:00 Dec 30 2020 (UTC)** and verify the time |
| 🌎 **Task 2** | [**Task2-Configure-Time-Zone.md**](Task2-Configure-Time-Zone.md) | Configure the local **time zone** on all routers and verify the clock reflects local time |
| 🌐 **Task 3** | [**Task3-Configure-External-NTP.md**](Task3-Configure-External-NTP.md) | Configure **R1 as an NTP client** using the Internet NTP server **1.1.1.1** and verify stratum levels |
| 🔐 **Task 4 & 5** | [**Task4-Configure-R1-as-NTP-Master-with-Authentication.md**](Task4-Configure-R1-as-NTP-Master-with-Authentication.md) | Configure **R1 as a Stratum 8 NTP master**, synchronize **R2/R3 with authentication**, and update the hardware calendar |

---

## 🧠 Notes
- Tasks **4 and 5 are combined** due to Packet Tracer limitations
- Physical interface IPs are used instead of `ntp source`
- Hardware calendar updates cannot be viewed in Packet Tracer but are still configured
