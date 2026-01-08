1. Overview

This circuit implements a password-based access system using:

Arduino UNO (ATmega328P) as the controller

4×4 Matrix Keypad for password input

16×2 LCD (LM016L) for user interface

The user enters a password via the keypad, and the Arduino verifies it. The LCD displays prompts like “Enter Password”, “Access Granted”, or “Access Denied”.

2. Major Components and Their Role
Arduino UNO

Acts as the central processing unit.

Reads keypad inputs (rows & columns).

Compares entered password with stored password.

Sends commands/data to the LCD for display.

4×4 Matrix Keypad

Contains 4 rows × 4 columns = 16 keys (0–9, A–D, *, #).

Connected to 8 digital pins of Arduino (4 rows + 4 columns).

Arduino scans rows and columns to detect which key is pressed.

Working principle:

Arduino sets columns as outputs and rows as inputs (or vice versa).

When a key is pressed, a specific row–column pair is shorted, allowing Arduino to identify the key.

16×2 LCD (LM016L)

Used in 8-bit mode (D0–D7 connected to Arduino digital pins).

Control pins:

RS → Register Select (Command/Data)

RW → Read/Write (usually tied to GND for write-only)

E → Enable pin

VSS, VDD, VEE handle ground, power, and contrast.

The LCD displays:

System messages

Entered digits (optionally masked with *)

Result of password verification

3. Power Connections

5V from Arduino powers LCD and keypad.

GND is common for all components.

Proper grounding is essential for stable operation.

4. Working Sequence

System Start

Arduino initializes LCD and keypad.

LCD shows: “Enter Password”.

Password Entry

User presses keys on the keypad.

Arduino reads each key press and stores it.

LCD shows input characters (or *).

Verification

After pressing # (or a defined key), Arduino compares input with stored password.

Result

If matched → LCD shows “Access Granted”.

If not matched → LCD shows “Wrong Password”.

5. Applications

Digital door lock systems

Locker security

Embedded security demonstrations

Proteus-based simulation projects for interviews
