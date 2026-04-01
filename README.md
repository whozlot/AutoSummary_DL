# AutoSummary

AutoSummary is a tool for Schneider Electric EcoStruxure (EBO).

It discovers devices, builds a live summary table, and saves the configuration so you don’t have to rebuild it again.

---

## What It Does

- Discovers devices from an EBO root path  
- Lets you select points from those devices  
- Builds a clean, real-time table view  
- Saves configuration (devices, points, columns, layout)  

---

## Core Workflow

1. Set root path  
2. Discover devices  
3. Select points  
4. Configure table  
5. Save view  

That’s it.

---

## Setup

### 1. Set Root Path

Define where your devices live in EBO.

Example:
/Server/Network/CommPort/VAVs

---

### 2. Discover Devices

- Click **Discover Devices**
- Select which devices to include

![Device Discovery](docs/images/devices.png)

---

### 3. Select Points

- Choose a device
- Browse folders
- Select points (SpaceTemp, Damper, Airflow, etc.)

![Point Selection](docs/images/points.png)

---

### 4. Configure Columns

- Show / hide columns  
- Drag to reorder  

![Columns](docs/images/columns.png)

---

### 5. Groups (Optional)

Group devices by naming pattern.

Example:
- Floor1 → VAV1*
- Floor2 → VAV2*

Adds subtotal rows.

![Groups](docs/images/groups.png)

---

### 6. AFDD (Optional)

Basic diagnostics:

- Flow vs setpoint
- Temperature deviation
- Device status

![AFDD](docs/images/afdd.png)

---

### 7. Save View

Click **Save View**

This stores:
- Devices
- Points
- Columns
- Groups
- AFDD settings

Configuration is saved and reused.

---

## Files

- `VavSummary.html` → UI  
- `VavSummaryApp.js` → Logic  

---

## Purpose

Make EBO data usable without digging through the tree.

Configure once. Use forever.

---

## Notes

- Built for internal BAS workflows  
- No external dependencies  
- Runs as a standalone HTML app  

---
