# servo-sync
🤖 servo-sync
Sweep. Hold. Repeat.
A simple Arduino-based project that brings 4 servo motors to life in perfect sync — sweeping together, then locking into position, all built and simulated on Tinkercad.
📋 Overview
This project controls four servo motors simultaneously using an Arduino Uno, executing two clean, sequential actions:
	•	🔄 Sweep — all four motors sweep back and forth together for 2 seconds
	•	🎯 Hold — the motors then settle and lock at 90°, staying perfectly still
Simple concept, satisfying to watch — four motors moving as one.

🧰 Components
	•	Arduino Uno R3 — 1
	•	Micro Servo Motor — 4
	•	Jumper Wires — as needed

🔌 Wiring
	•	Servo 1: Signal → Pin 9, Power → 5V, Ground → GND
	•	Servo 2: Signal → Pin 10, Power → 5V, Ground → GND
	•	Servo 3: Signal → Pin 11, Power → 5V, Ground → GND
	•	Servo 4: Signal → Pin 12, Power → 5V, Ground → GND
All four servos share the same 5V and GND rails — only the signal pin changes per motor.

💻 Code
The full sketch lives in servo_control.ino.
How it works, in short:
	•	Each of the 4 servos gets its own Servo object and pin via attach().
	•	A sweep loop moves all motors from 0° → 180° → 0° repeatedly for ~2 seconds.
	•	Once the sweep finishes, every motor is commanded to write(90) and holds there.
	•	loop() is left empty — the motion happens entirely in setup(), and there’s nothing left to repeat.
