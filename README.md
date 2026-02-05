# 🚗 MNC Respray Points

[![FiveM](https://img.shields.io/badge/FiveM-Ready-green.svg)](https://fivem.net/)
[![QBCore](https://img.shields.io/badge/Framework-QBCore-blue.svg)](https://github.com/qbcore-framework)
[![Version](https://img.shields.io/badge/Version-1.1.0-brightgreen.svg)]()

---

## 🌟 Overview

**MNC Respray Points** is a lightweight, highly configurable vehicle respray system for QBCore servers.

Players can pay to fully customize their vehicle at public respray stations, while mechanics on duty automatically hide the public points (forcing players to visit actual mechanic shops). Job-restricted and emergency-only bays (police, ambulance, etc.) offer **free resprays** for official vehicles.

Built with **ox_lib** for clean menus, live preview, and modern notifications.

---

## ✨ Key Features

- ✅ Public respray points **auto-hide** when any mechanic is on duty  
- ✅ Job-restricted bays (`police`, `ambulance`, custom jobs)  
- ✅ Emergency-only bays with **free respray** for class 18 vehicles  
- ✅ Full color options: Primary, Secondary, Pearlescent, Wheels, Interior, Dashboard  
- ✅ Livery system with automatic detection (mod 48 vs native liveries)  
- ✅ Real-time **live preview** + confirmation dialog  
- ✅ Bundle "Full Respray" option  
- ✅ Configurable prices per type  
- ✅ Clean ox_lib context menus & notifications  
- ✅ Debug mode with detailed logging  

---

## 📋 Requirements

| Dependency      | Version   | Required |
|-----------------|-----------|----------|
| qb-core         | Latest    | Yes      |
| ox_lib          | Latest    | Yes      |

---

## 🚀 Installation

1. Download the resource
2. Place it in your resources folder:
   ```
   [server-data]/resources/[custom]/mnc-respraypoints/
   ```
3. Add to your `server.cfg`:
   ```lua
   ensure mnc-respraypoints
   ```
4. Restart your server (or just the resource)

No database tables required.

---

## ⚙️ Configuration (config.lua)

### Mechanic Jobs (hide public points)
```lua
Config.MechanicJobs = {
    mechanic = true,
    mechanic2 = true,
    bennys = true,
    beekers = true,
    -- add your mechanic jobs here
}
```

### Prices
```lua
Config.ResprayPrices = {
    primary      = 350,
    secondary    = 300,
    pearlescent  = 250,
    wheel        = 200,
    interior     = 300,
    dashboard    = 250,
    livery       = 500,
    full         = 1000,
}
```

### Locations
```lua
Config.Locations.respray = {
    -- Public points (hidden when mechanic on duty)
    { coords = vector4(-211.1, -1308.04, 30.67, 270.37), name = 'Bennys Respray Point' },
    { coords = vector4(108.0, 6608.75, 31.35, 319.44),   name = 'Beekers Respray Point' },

    -- Police-only free emergency bay
    {
        coords = vector4(462.73, -1014.6, 27.68, 271.51),
        name = 'MRPD Respray Bay',
        job = 'police',
        minGrade = 0,
        emergencyOnly = true
    },
    -- Ambulance example
    {
        coords = vector4(337.79, -561.15, 28.35, 160.82),
        name = 'Pillbox Medical Respray Bay',
        job = 'ambulance',
        emergencyOnly = true
    },
}
```

### Vehicle Colors
Edit the big `Config.VehicleColors` table to add/remove colors (includes matte, chrome, etc.).

---

## 🎮 How to Use

1. Walk up to a respray point (when visible)
2. Press **E**
3. Choose color type → live preview on your vehicle
4. Confirm → pay from bank (or free if emergency bay)
5. Done!

**Mechanics on duty?**  
Public points show a red warning: “Mechanic on duty – visit customs!”

---

## 📝 Credits

**Author**: Stan Leigh  
**Version**: 1.1.0  
**Framework**: QBCore + ox_lib

---

**Enjoy clean, professional vehicle resprays on your server!** 🚗💨