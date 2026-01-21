 NanoCommSim (AnyLogic) — Molecular Communication Simulation

This repository contains my AnyLogic simulation of molecular (diffusion-based) communication between a Transmitter and a Receiver. The idea is simple: the transmitter releases a pulse of molecules, the receiver observes a signal (“molecules in range”), performs an automatic calibration on the first pulse, and then detects messages using two thresholds (URT/LRT).

✅ Defaults in this repo
	•	Feedback is OFF by default 🚫↩️
	•	Receiver sectors = 20 🧩 (dynamic, but default is 20)
	•	Threshold lines are ON 📈✅

⸻

🔍 What the simulation does
	•	The Transmitter emits a pulse of molecules (bacteriaPerPulse).
	•	Molecules diffuse through the environment.
	•	The Receiver has a sensing/absorption area and continuously measures:
	•	Molecules in Range = how many molecules are currently inside the receiver’s sensing radius.
	•	The receiver:
	•	calibrates thresholds during the first pulse
	•	detects messages using URT/LRT afterwards

⸻

📊 The signal used (important)

The detection signal is the instantaneous signal:

Molecules in Range = molecules currently inside the receiver sensing radius.

This is the same signal shown in the plot (not cumulative absorbed molecules).

⸻

🛠️ Auto-Calibration (first pulse only)

As soon as the receiver starts seeing molecules (winAbs0 > 0), calibration begins.

During calibration:
	•	we collect samples (tRel, y)
	•	we compute the maximum value of the first pulse signal (maxY)
	•	thresholds are set “paper-style”:
	•	URT = round(0.9 × maxY)
	•	LRT = round(URT / 3)

You’ll see logs in the console like:
	•	CALIBRATION START ...
	•	CALIBRATION DONE ... URT... LRT... maxY...

⸻

✅ Message Detection (URT/LRT)

After calibration:
	•	If the signal rises above URT → message START detected 🚀
	•	Later, when it falls below LRT → message END detected ✅
	•	On END:
	•	NUMBER_OF_MESSAGES_RECEIVED++ increments 📩
	•	(optional) feedback logic can be triggered — but in this repo it’s disabled by default.

⸻

🧩 Receiver Sectors (default: 20)

The receiver is divided into sectors (default = 20).
This is used to track where molecules are being absorbed (spatial distribution around the receiver).

⚙️ You can change the number of sectors anytime (20 → 36 → 8 etc.), but the default setup is 20.

⸻

🚫 Feedback (Receiver → Transmitter) — OFF by default

There is logic for feedback molecules from receiver to transmitter, but:

Feedback is OFF by default to keep the simulation simpler and lighter.

If you want to enable it later, you can toggle it (without deleting code).

⸻

▶️ How to run
	1.	Open the project in AnyLogic.
	2.	Run Main.
	3.	Default parameters you’ll start with:
	•	receiver sectors = 20
	•	threshold lines = ON
	•	feedback = OFF
	4.	Watch:
	•	the Molecules in Range plot 📈
	•	URT/LRT lines (horizontal)
	•	console logs for calibration and detection

⸻

🧪 Notes / Debugging tips
	•	If maxY in the console seems higher than what you visually notice:
	•	verify the plot is showing the same signal used for calibration (e.g., winAbs0).
	•	For a message to be counted:
	•	it must cross URT upward
	•	then later cross LRT downward

⸻

👤 Author

Pavlos Dar 🇬🇷
Aristotle University of Thessaloniki (AUTH) — Informatics