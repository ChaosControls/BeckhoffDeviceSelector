# BeckhoffDeviceSelector

**E-Bus Segment Planner**: a single-page web calculator for Beckhoff EtherCAT terminal segments.

- Choose the bus coupler first (EK1100, EK1101, EK1501, EK18xx, EK9xxx, CX, BK K-bus couplers or a custom supply). Device selection unlocks once it is on the fieldbus; select the coupler and press **Change** to swap it.
- The **Device** dropdown keeps your 8 most recent devices. **List** opens a searchable window of about 1,300 EL / ES / ED / ELM / ELX / KL / KS / KM / EP / EPP devices (including TwinSAFE) plus extensions such as the EK1110 and EK1122; pick one, press **Select**, then **Add** to drop it into the last open slot.
- In the fieldbus window, click a device to select it, drag it to change the order (or Shift + arrow keys), and press **Remove** to delete it.
- Totals E-bus and K-bus (after a BK1250) current per segment and shows the current left after every slice.
- Flags segments that run past the coupler's supply, or below an optional reserve (5–20 %).
- Marks where an EL9410 (or KL9400 on K-bus) should go and can insert it for you.
- Flags layout problems: KL terminals without a K-bus source, devices after an EK1110, rail devices after an EP box.
- Copies a parts list per segment to the clipboard.

## Use

Open `index.html` in any browser. No build step and no server. Your segments are saved in the browser's local storage.

## Budget rules

- Each coupler feeds the terminals to its right with its rated E-bus current (2,000 mA for EK1100, 1,000 mA for the EK18xx couplers with built-in I/O, 1,750 mA K-bus for most BK couplers). A BK1250 gives 500 mA of K-bus.
- An EL9410 counts as a fresh 2,000 mA for the terminals after it. The coupler's leftover is not carried past it (conservative).
- Device draws and coupler supplies are the typical figures from each device's Beckhoff product page (crawled November 2026). ES terminals use the matching EL value. About 30 devices whose page gives no figure use the family median and are marked **verify**. Every value can be edited in the table; check the result against the E-Bus column in TwinCAT after scanning the hardware.
