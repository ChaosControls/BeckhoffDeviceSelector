# BeckhoffDeviceSelector

**E-Bus Segment Planner**: a single-page web calculator for Beckhoff EtherCAT terminal segments.

- Pick the EL terminals behind each EK coupler (EK1100, EK1101, EK1501, EK18xx, CX or a custom supply) in rail order.
- Totals E-bus current draw per segment and shows the current left after every slice.
- Flags segments that run past the coupler's supply, or below an optional reserve (5–20 %).
- Marks where an EL9410 should go and can insert it for you.
- Copies a parts list per segment to the clipboard.

## Use

Open `index.html` in any browser. No build step and no server. Your segments are saved in the browser's local storage.

## Budget rules

- Each coupler feeds the terminals to its right with its rated E-bus current (2,000 mA for EK1100, 1,000 mA for the EK18xx couplers with built-in I/O).
- An EL9410 counts as a fresh 2,000 mA for the terminals after it. The coupler's leftover is not carried past it (conservative).
- Terminal draws are typical values from Beckhoff datasheets. Ones marked **verify** are less certain. Every value can be edited in the table; check the result against the E-Bus column in TwinCAT after scanning the hardware.
