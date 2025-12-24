Arduino Smart Door Lock System
This project implements a simple smart door lock using an Arduino Uno,
a servo motor, a push button, and LED indicators.  
The system toggles between locked and unlocked states with each
button press.

Project Overview

- Locked: Servo at 0°, Red LED ON
- Unlocked: Servo at 90°, Green LED ON
- Push button toggles the door state
- Servo is powered using an external battery pack
- Proper grounding is maintained between Arduino and servo supply

---

Components Used

- Arduino Uno
- Servo Motor (SG90 or equivalent)
- Push Button
- Red LED
- Green LED
- 2 × 220Ω resistors (for LEDs)
- External 4×AA battery pack (servo power)
- Breadboard & jumper wires

---

Wiring Guide (Beginner-Friendly)

Push Button
- One side → GND
- Other side → Digital Pin 2
- Button uses `INPUT_PULLUP` (no external resistor needed)

LEDs
Red LED (Locked Indicator):
- Anode (+) → Digital Pin 4 (through 220Ω resistor)
- Cathode (−) → GND

Green LED (Unlocked Indicator):
- Anode (+) → Digital Pin 5 (through 220Ω resistor)
- Cathode (−) → GND

Servo Motor
- Signal (Yellow/White) → Digital Pin 9
- VCC (Red) → External Battery Pack (+)
- GND (Brown/Black) → External Battery Pack (−)

IMPORTANT:
Connect **Arduino GND** to **battery pack GND** (common ground).

---

Circuit Logic Explanation

1. System starts in locked state
2. Servo moves to 0°
3. Red LED turns ON
4. Button press toggles the door state
5. Servo rotates to the target angle
6. Corresponding LED updates

---

How the Code Works 
1. Button is read using `INPUT_PULLUP`
2. Software debounce prevents false triggers
3. Button press is detected on HIGH → LOW transition
4. A boolean variable stores the door state
5. Servo angle and LEDs update based on state

---

Power & Grounding Notes (VERY IMPORTANT)

- Servo motors draw high current
- Do NOT power the servo from Arduino 5V
- Always use an external battery for the servo
- Grounds must be connected together
- Failure to share ground will cause:
  - Servo not moving
  - Random behavior
  - LEDs working but servo failing

---

Troubleshooting

Servo Not Moving
- Check external battery voltage
- Ensure common ground between Arduino and battery
- Confirm servo signal pin connection
- Test servo with a simple sweep sketch

LEDs Not Turning ON
- Check LED polarity
- Verify resistor placement
- Confirm correct pin numbers

Button Not Responding
- Ensure `INPUT_PULLUP` is used
- Button must connect to GND
- Check debounce logic

---

Project Status

Complete and fully functional**

---

Images

See the `images/videos/` folder for:
- Breadboard setup
- Locked state
- Unlocked state

---

License

This project is open-source and free to use for learning and development.
