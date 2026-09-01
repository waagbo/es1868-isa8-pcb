# SMD Conversion Notes (`ISA_ES1868_smd`)

`ISA_ES1868_smd.kicad_pcb` / `.kicad_sch` / `.kicad_pro` are a copy of the rev 1.2 project
with through-hole parts converted to hand-solderable SMD footprints. The files are saved in
KiCad 10 format (the original rev 1.2 files are untouched and remain KiCad 7).

## What was converted

| Group | Old footprint | New footprint | Refs |
|---|---|---|---|
| Ceramic disc capacitors (38) | `C_Disc_D6.0mm` / `D3.8mm` | `C_0805_..._HandSolder` | C1–C11, C15–C33, C38–C41, C46–C48, C53 |
| 10 µF electrolytics on supply/bias nets (5) | `CP_Radial_D5.0mm` | `C_0805_..._HandSolder` (MLCC) | C12, C13, C50, C51, C52 |
| Resistors (34) | `R_Axial_DIN0207` | `R_0805_..._HandSolder` | R1–R18, R22–R37 |
| Axial ferrite beads (3) | `L_Axial_Vishay_IM-1` | `L_0805_..._HandSolder` | L1, L2, L3 (now same bead as L4–L9/L12) |
| 78L05 regulator | TO-92 | `SOT-89-3_Handsoldering` | U1 (pin functions 1=OUT/2=GND/3=IN identical in both packages) |
| 74LS138 decoder | DIP-16 | `SOIC-16_3.9x9.9mm` | U2 |
| 93LC66 EEPROM | DIP-8 | `SOIC-8_3.9x4.9mm` | U4 |

All converted parts keep their original position, rotation, reference, value and pad-net
assignments (verified pad-by-pad against the original board — zero net differences).

Like the original board, the converted parts print their **value on the front silkscreen**
(1×1 mm text, 0.15 mm stroke — same style as the THT originals). Ferrite beads keep their
values hidden, matching the original convention for L4–L12. Expect to nudge some value labels
apart while re-routing dense areas.

## What deliberately stays through-hole

* **U3 ES1868F** — already SMD (LQFP).
* **U7 LM1877 (DIP-14)** — no SMD package of this part ever existed; the chip itself is obsolete
  (see BOM notes).
* **Audio-path electrolytics** — kept as THT radial on purpose:
  * C36, C37 (10 µF): line-out coupling caps. A ceramic here would add DC-bias/piezo distortion;
    a leaded electrolytic (or audio-grade type) is the better part, and THT radials are trivial
    to hand solder.
  * C34, C35 (470 µF): speaker output coupling after the LM1877.
  * C14, C43 (47 µF): ES1868 VREF/CMR filter and LM1877 bias bypass — value too large for a
    sane 0805 ceramic, and both sit in audio-relevant reference nodes.
  * C42 (100 µF): amplifier supply bulk on `/Filtered_12V`.
* **Y1 crystal, all connectors, ISA edge, solder jumpers** — unchanged.

## Audio-circuit classification of the capacitors

Positions that are **in the audio signal path** (choose good dielectrics here):

| Refs | Function | Recommendation |
|---|---|---|
| C27, C28 (220 nF) | Line-in coupling | 50 V X7R 0805 (voltage headroom minimises C(V) distortion) |
| C31, C32 (220 nF) | AUX A coupling | 50 V X7R 0805 |
| C29, C30 (220 nF) | AUX B (wavetable) coupling | 50 V X7R 0805 |
| C8, C9 (220 nF) | FM out → codec in coupling | 50 V X7R 0805 |
| C47, C48 (220 nF) | LM1877 input coupling | 50 V X7R 0805 |
| C6 (100 nF) | Mic coupling | 50 V X7R 0805 |
| C10, C33 (1 nF) | Codec input filters | **C0G/NP0** |
| C38, C39 (10 nF) | LM1877 feedback | **C0G/NP0** |
| C40, C41 (100 nF) | LM1877 Zobel/snubber | 50 V X7R |
| C36, C37 (10 µF) | Line-out coupling | THT electrolytic (audio grade optional) |
| C34, C35 (470 µF) | Speaker coupling | THT electrolytic |

The original card used ceramic discs in all the small-value audio positions, so 0805 MLCCs are
not a downgrade — using 50 V-rated X7R (never Y5V/X5R for coupling) keeps distortion negligible
at ~1 Vrms line levels.

Non-audio positions: supply decoupling (C1–C5, C17, C50–C53, C12, C42), joystick timing caps
(C18–C21, C23–C26 — use **C0G** so gameport position readings stay stable with temperature),
crystal load caps (C15, C16 — **C0G**), reset filter (C46), VREF/bias filters (C7, C11, C13, C14,
C22, C43).

## Layout status — re-routing required

The converted footprints sit at the old component centroids, but 0805 pads do not land on the
old THT pad locations, so **the tracks around every converted part need to be re-routed** before
fabrication. DRC (`kicad-cli pcb drc --schematic-parity`) against the original board shows:

* schematic parity: **identical to the original** (the 188 reported net-name conflicts also
  exist on the untouched rev 1.2 board — they are KiCad 7 → 10 auto-net renaming, not errors),
* ~157 unconnected items + clearance/short/mask violations, all clustered at converted parts:
  this is exactly the pending re-route work. The old routing was left in place so it can be
  dragged/reused; the ratsnest shows every required connection.

Note: several THT pads were also used as layer-change points — where a track reached a
converted component on the back copper layer, a via is now needed.

## BOM

See [BOM_smd.csv](BOM_smd.csv) / [BOM_smd.md](BOM_smd.md) for the full bill of materials with
DigiKey, Mouser and LCSC alternatives.
