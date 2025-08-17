# Pet-Feeder_Project

## 📘 Project Overview
This project simulates the logic and behavior of a low-cost, programmable automated pet feeder system designed for a local animal shelter. The system is intended to:
- Dispense food for cats and dogs at scheduled times.
- Monitor whether food has been consumed.
- Alert staff if food is not dispensed or not eaten.

## 🎯 Objectives
The goal is to design and simulate the logic of the system using the Integrated Problem-Solving Process, which includes:
1. Analyzing the problem and defining its requirements.
2. Organizing and describing all the data and inputs.
3. Designing an algorithm to control the system.
4. Implementing the solution using plain English.
5. Testing and refining the solution with example input values.

## 🧠 Problem-Solving Process

### Step 1: Understand and Define the Problem
- **Features Required:**
  - Scheduled feeding
  - Consumption monitoring
  - Alert system
- **Inputs:** Feeding times, food level sensor, weight sensor under bowl
- **Outputs:** Servo motor control, alert system (buzzer)
- **Assumptions:**
  - Only one type of pet food is used
  - Limited memory and low-cost components (Arduino, servo motor, sensors)
  - Buzzer is used for alerting staff

### Step 2: Organize and Describe the Data

| Variable           | Type    | Units   | Notes                                |
|--------------------|---------|---------|--------------------------------------|
| Clock Time (Tc)    | Input   | Time    | Time from Real-Time Clock            |
| Feeding Time (Tf)  | Input   | Time    | Predefined times (8 AM, 6 PM)        |
| Food Level (Fl)    | Input   | Boolean | FULL / NOT FULL                      |
| Food Weight (Fw)   | Input   | Boolean | EMPTY / NOT EMPTY                    |
| Servo Motor (M)    | Output  | Boolean | ON / OFF                             |
| Buzzer (B)         | Output  | Boolean | ON / OFF                             |

**Constants:**
- Feeding Time: 8 AM and 6 PM
- Wait time for checking food consumption: 10 minutes
- Servo rotation: 2 seconds

### Step 3: Design the Algorithm
- At scheduled time, rotate servo to dispense food
- Check if food is present in the bowl
- Wait for 10 minutes
- Check if the food has been consumed
- If food is not consumed or has not been dispensed, trigger alert to staff

### Step 4: Implementing the Solution (Plain English)
- If Real-Time Clock time matches feeding schedule:
  - Rotate Servo Motor to dispense food
  - Check Food Weight Sensor
    - If food not detected, trigger Buzzer
    - Else, wait 10 minutes
      - Check Food Level sensor
        - If food not consumed, trigger Buzzer

### Step 5: Testing and Refining the Solution

**Test Scenarios:**
- ✅ Pet eats as expected → No Alert
- ❌ Pet does not eat → Buzzer Triggered
- ❌ Food bowl is empty → Buzzer Triggered
- ❌ Food level does not reduce after wait time → Buzzer Triggered
- ✅ Food level reduces after wait time → No Alert

## 🚀 Suggested Improvements
- Use a better weight sensor to measure exact food consumption
- Support multiple types of pet food with different shapes and sizes
- Replace buzzer with mobile app notifications for remote alerts
- Add a real-time clock (RTC) module for better timekeeping
- Include a battery backup for power outages

## 🛠 Technologies Used
- Arduino UNO (simulated)
- Servo Motor
- IR/Weight Sensors
- Buzzer
- Real-Time Clock (optional)

## 📁 Files Included
- `IIT Assessment 1 1.docx` – Full design and logic documentation
- `README.md` – Project overview and instructions

## 📌 Status
✅ Logic and simulation complete  
🔜 Hardware implementation (future phase)

## 🤝 Acknowledgements
This project was developed as part of an IIT assessment task to demonstrate problem-solving, system design, and simulation skills using embedded systems.

## 📬 Contact
For questions or collaboration, feel free to reach out via GitHub or email.
