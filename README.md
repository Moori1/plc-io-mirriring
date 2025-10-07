# ⚙️ PLC Kit Project

This repository documents the practical work completed with the **PLC Kit** using **Phoenix Contact’s PLCnext Engineer** software.  
The goal of this project was to gain hands-on experience with device configuration, programming, and network setup while creating an **I/O Mirror Program** that replicates input states to corresponding outputs in real time.

---

## 📘 Overview

- **Project Title:** PLC Kit  
- **Author:** Morteza Naseri  
- **Field:** Energy and Environmental Technology  
- **Year:** 2025  
- **Software Used:** PLCnext Engineer (Phoenix Contact)

This project walks through every step — from creating a new PLC project, connecting devices, defining variables, to deploying a running program on the hardware.

---

## 🔧 Objectives

- Configure a **PLC (AXC F 2152)** device using PLCnext Engineer  
- Add and set up hardware modules (AXL F DI8/1 DO8/1 1H, AXL F AI2 AO2 1H, AXL F BK PN)  
- Define digital and analog variables  
- Write an ST (Structured Text) program to mirror inputs to outputs  
- Test the system functionality and verify the results on the physical board

---

## 🧩 Project Steps

### 1. Project Setup
- Open **PLCnext Engineer**
- Create a new project
- Add the **AXC F 2152** controller as the main device

### 2. Connecting to PLC
- Use **Online Controllers** to detect and connect to the PLC via network
- Authenticate using the credentials printed on the PLC kit

### 3. Adding Modules
Modules used in this project:
- `dio-1`: AXL F DI8/1 DO8/1 1H (digital I/O)
- `Hall01_Tank`: AXL F AI2 AO2 1H (analog I/O)
- `AXL F BK PN`: added manually via Profinet

### 4. Defining Variables
- Variables are generated for each module to represent input/output ports.
- These variables are used in the ST code to mirror the data flow.

### 5. Creating the I/O Mirror Program
The main logic is written in **Structured Text (ST)** to copy input values directly to corresponding outputs.

#### Example Code
```pascal
dio_1_OUT00 := dio_1_IN00;
dio_1_OUT01 := dio_1_IN01;
dio_1_OUT02 := dio_1_IN02;
dio_1_OUT03 := dio_1_IN03;
dio_1_OUT04 := dio_1_IN04;
dio_1_OUT05 := dio_1_IN05;
dio_1_OUT06 := dio_1_IN06;
dio_1_OUT07 := dio_1_IN07;

Hall01_Tank_AQ32 := Hall01_Tank_AI32;
axl_f_bk_pn_1_dio_1_dio_1_DO8 := axl_f_bk_pn_1_dio_1_dio_1_DI1;
```

### 6. Network Configuration
- Configure IP ranges under **Project → Settings** to match the connected PLC network.

### 7. Run and Test
- Deploy the program to the PLC (`Write and Start Project`)
- Verify functionality: toggling switches and adjusting potentiometer changes outputs correspondingly.

---

## ✅ Results

- The **I/O Mirror Program** successfully mirrors input signals to outputs.  
- System verification confirms correct mapping and operation of digital/analog channels.  
- Achieved visual confirmation through LEDs, switches, and potentiometer feedback.

---

## 📚 References

- Phoenix Contact. *Nisses skola – PLCnext video.*  
  [https://www.phoenixcontact.com/sv-se/nisses-skola/nisses-skola-plcnext-video](https://www.phoenixcontact.com/sv-se/nisses-skola/nisses-skola-plcnext-video)

- *PLCnext Engineer. Interbus Parameterization.*  
  [https://engineer.plcnext.help/2025.0_en/InterbusParameterization.htm](https://engineer.plcnext.help/2025.0_en/InterbusParameterization.htm)

- *Software PLCnext Engineer.*  
  [https://www.phoenixcontact.com/en-pc/products/software-plcnext-engineer-1046008](https://www.phoenixcontact.com/en-pc/products/software-plcnext-engineer-1046008)

---

## 💬 Contact

**Author:** Morteza Naseri  
**Field:** Energy and Environmental Technology  
**Institution:** Arcada University of Applied Sciences  
**Year:** 2025
