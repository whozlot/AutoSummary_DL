# AutoSummary

**AutoSummary** is compatible with Schneider Electric EcoStruxure™ Building Operation (EBO) (tested with Version 7).

It provides a fast, repeatable way to discover devices, select points, and generate a live summary table—without navigating the EBO tree manually.

---

## Overview

AutoSummary allows you to:

- Discover devices from any EBO root path  
- Select and organize key points  
- Build a real-time summary table  
- Save configurations for reuse  

Configure once. Use indefinitely.

---

## Core Workflow

1. Set root path  
2. Discover devices  
3. Select points  
4. Configure table layout  
5. Save configuration  

---

## Requirements

AutoSummary requires a small amount of setup inside Schneider Electric EcoStruxure™ Building Operation.

### Required Steps

1. Import the provided XML file into an AS-P  
2. Modify two lines in the HTML file  
3. Re-import and associate the modified HTML file over the existing HTML5 object in EcoStruxure  
4. Configure the required string values in EcoStruxure  

---

### HTML Configuration

Modify the following lines in your HTML file:

#### 1. Client API Script (Approx. Line 893)

**Live AS-P:**
```html
<script src="/publicweb/client_api.js"></script>
```

**PCT:**
- This must be referenced from the Web Link path instead

#### 2. Configuration Path (Approx. Line 897)

```javascript
const CONFIG_BASE = "/NAME_OF_ASP/Web/config";
```

---

### Required String Values in EcoStruxure

Create the required string values under:

```
/ASP/Web/Config
```

Use the following values:

| Name | Description | Note | Example Value |
|---|---|---|---|
| `cfg_graphicpath` | Graphic path | Path from Root Device to Graphic, including graphic name | `/Application/Graphics/VAV Flow Diagram` |
| `cfg_root` | Root path | Path to the VAV network | `/MODOT_TC_ASP1/Infinet Interface/Comm B` |
| `cfg_serverbase` | Config path | Path where config files live | `/MODOT_TC_ASP1/Web/config` |
| `cfg_title` | Display title | Title shown in the summary | `MyBMS VAV Summary` |

---

## Setup

### 1. Set Root Path

Define the location of your devices in EBO.

**Example:**
```
/Server/Network/CommPort/VAVs
```

---

### 2. Discover Devices

- Click **Discover Devices**
- Select devices to include

![Device Discovery](docs/images/devices.png)

---

### 3. Select Points

- Choose a device  
- Navigate object folders  
- Select required points (e.g., SpaceTemp, Damper, Airflow)

![Point Selection](docs/images/points.png)

---

### 4. Configure Columns

- Show or hide columns  
- Reorder via drag-and-drop  

![Columns](docs/images/columns.png)

---

### 5. Grouping (Optional)

Group devices using naming patterns.

**Example:**
- Floor1 → VAV1*  
- Floor2 → VAV2*  

Adds subtotal rows per group.

![Groups](docs/images/groups.png)

---

### 6. AFDD (Optional)

Basic fault detection:

- Flow vs setpoint deviation  
- Temperature deviation  
- Device status validation  

![AFDD](docs/images/afdd.png)

---

### 7. Save Configuration

Click **Save View** to persist:

- Devices  
- Points  
- Column layout  
- Grouping rules  
- AFDD settings  

Configuration is stored and reused.

---

## File Structure

- `VavSummary.html` — UI  
- `VavSummaryApp.js` — Application logic  

---

## Purpose

AutoSummary makes EBO data immediately usable without digging through the system tree.

It provides a consistent, structured view of live data for commissioning, troubleshooting, and operations.

---

## Notes

- Designed for BAS / controls workflows  
- No external dependencies  
- Runs as a standalone HTML application within EBO  

---

## Disclaimer

Schneider Electric and EcoStruxure are trademarks of Schneider Electric.  
AutoSummary is an independent tool and is not affiliated with or endorsed by Schneider Electric.

---
