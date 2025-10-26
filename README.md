# 🛡️ GuardianBot EA — Advanced Per-Symbol Risk Management for MetaTrader 5

### **Short Description**
GuardianBot is an advanced **MetaTrader 5 Expert Advisor (EA)** designed for **per-symbol risk management**.  
It tracks floating profit/loss and applies custom drawdown limits individually per symbol to ensure controlled, intelligent risk distribution across all trades.

---

## 🚀 Overview
Traditional EAs monitor global account drawdown, but GuardianBot goes further — it manages each pair independently.  
If a symbol exceeds its configured loss limit, GuardianBot closes only that symbol’s trades while keeping others active. This provides precision control and minimizes portfolio-wide impact.

---

## ✨ Key Features
- ✅ **Per-Symbol Floating PNL Monitoring**
- ✅ **Custom Drawdown % per Symbol**
- ✅ **Multi-Broker & Symbol-Suffix Compatibility**
- ✅ **Supports Forex, Gold, and Silver**
- ✅ **Auto Symbol Detection & Filtering**
- ✅ **Optional Daily Stop-Loss**
- ✅ **Pause/Resume After Breach**
- ✅ **Real-Time Chart Display & Alerts**
- ✅ **Low Resource Usage**

---

## ⚙️ Installation
1. Copy `GuardianBot.mq5` to your `MQL5/Experts/` directory.  
2. Open MetaEditor → Compile (`F7`).  
3. Attach the EA to any chart.  
4. Configure your input parameters.  
5. Enable **AutoTrading** and allow trade permissions.

---

## 🧩 Configuration Guide

### 🔹 Symbol Settings
```ini
SymbolsToMonitor = "EURUSD,GBPUSD,XAUUSD"
AutoDetectAllSymbols = false
```
- **SymbolsToMonitor** → list of pairs to monitor  
- **AutoDetectAllSymbols** → enable to monitor all visible symbols

### 🔹 Risk Control
```ini
PerPairLimits = "EURUSD:4,GBPUSD:3,XAUUSD:8"
DefaultLimitPercent = 5.0
TotalAccountRiskPercent = 15.0
PauseMinutesAfterClose = 60
```
- **PerPairLimits** defines % drawdown limit per symbol  
- **DefaultLimitPercent** applies to unlisted symbols  
- **PauseMinutesAfterClose** = cooldown after closure

### 🔹 Daily Stop-Loss (Optional)
```ini
EnableDailyStop = true
DailyStops = "XAUUSD:1000,GBPUSD:300"
```

### 🔹 Display & Alerts
```ini
ShowOnChart = true
SendAlerts = true
SendNotifications = false
```

---

## 🧠 How GuardianBot Works
1. **Initialization:** Loads and validates symbol list.  
2. **Live Monitoring:** Calculates floating PNL every second.  
3. **Limit Breach:** Closes trades for breached symbol, pauses it.  
4. **Display Update:** Real-time chart overlay shows active/paused status.  
5. **Logging & Alerts:** Generates console + push alerts (optional).

---

## 📊 Example On-Chart Display
```
=== GuardianBot Status ===
Account Balance: $10,000.00
Total Symbols: 4

EURUSD: ACTIVE | -1.50% / 4.0%
GBPUSD: ACTIVE | 0.75% / 3.0%
XAUUSD: PAUSED | 0.00% / 8.0% | Pause: 45m
USDJPY: ACTIVE | -2.00% / 3.0%
```

---

## 🧱 Usage Examples

**Example 1 — Conservative Setup**
```
SymbolsToMonitor = "EURUSD,GBPUSD,USDJPY"
PerPairLimits = "EURUSD:2,GBPUSD:2,USDJPY:2"
```

**Example 2 — Forex + Metals**
```
SymbolsToMonitor = "EURUSD,GBPUSD,XAUUSD,XAGUSD"
PerPairLimits = "EURUSD:3,GBPUSD:3,XAUUSD:8,XAGUSD:6"
```

**Example 3 — Auto Mode**
```
AutoDetectAllSymbols = true
DefaultLimitPercent = 5.0
```

---

## ⚠️ Important Notes
- Always test on **demo account first**.  
- Start with **low drawdown limits** and increase gradually.  
- Check Market Watch for available symbols.  
- Stable internet connection required for real-time monitoring.

---

## 🧩 Troubleshooting
| Issue | Possible Cause / Fix |
|-------|------------------------|
| EA not monitoring symbols | Ensure symbols exist in Market Watch |
| PNL always 0.00 | Ensure open trades are active |
| Positions not closing | Check AutoTrading & broker permissions |
| Symbol not found | Use correct broker suffix (e.g., EURUSDm) |

---

## 📦 Version Information
- **Version:** 1.00  
- **Platform:** MetaTrader 5  
- **Compatibility:** All major MT5 brokers  
- **Last Updated:** October 2025  

---

## 👨‍💻 Author
**Kamran Ali — Kamran Ali Developer**  
📧 kamranalideveloper@gmail.com  

> **GuardianBot — Protecting your trading capital, one symbol at a time.**

---
