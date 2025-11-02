# Splunk Dashboard: Sample Log Analytics

This repository contains a custom-built **Splunk dashboard** created using **Splunk Enterprise 10.x** on macOS. The dashboard is focused on visualizing and exploring sample log data.

---

## 📊 Dashboard Overview

**Dashboard name:** `Splunk_Test_1`  
**File:** `splunk_test_1.xml`  
**Dashboard type:** Classic (SimpleXML)

This dashboard was created manually in the Splunk Search & Reporting app and includes multiple panels showing useful breakdowns of ingested log data.

---

## 🛠️ What This Dashboard Contains

The dashboard visualizes events from a custom-uploaded sample log file using various SPL queries. Here's what was done:

### ✅ Step-by-step process

1. **Installed Splunk Enterprise** locally on macOS using the 60-day free trial
2. **Uploaded a sample log file** (`sample_logs.txt`) via Settings → Add Data
3. **Ran SPL searches** to explore log contents and validate data
4. **Created a Classic Dashboard** (`Splunk_Test_1`) via Search & Reporting
5. **Added the following panels:**
    - 🔸 Total log event count (using `stats count`)
    - 🔸 Events by IP address (with `rex` extraction)
    - 🔸 Events by severity (INFO, WARNING, ERROR)
6. **Saved all panels into a single dashboard**
7. **Exported dashboard XML** from local Splunk filesystem
8. **Uploaded to GitHub**

---

## 📁 Files in This Repo

| File | Description |
|------|-------------|
| `splunk_test_1.xml` | Raw XML of the dashboard, exportable and importable into Splunk |
| `README.md` | This file |

---

## 📎 Sample SPL Queries Used

```spl
index=main | stats count as Log_Events

index=main | rex "ip=(?<src_ip>[\d\.]+)" | stats count by src_ip

index=main | rex ",(?<severity>INFO|ERROR|WARNING)," | stats count by severity
```

---

## 🔁 How to Reuse This Dashboard

If you have Splunk installed:

1. Go to **Dashboards → Create New → Classic Dashboard**
2. Click **Source** and **paste the contents of `splunk_test_1.xml`**
3. Click **Save**

You’ll see all panels recreated in your Splunk environment.

---

## 🧑‍💻 Created by

This dashboard was built and documented step-by-step as part of a hands-on learning project to practice:

- Splunk Search Processing Language (SPL)
- Dashboard building
- Data ingestion
- Git version control

---

## 📝 License

This project is shared under the MIT License.
