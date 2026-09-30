# DigiKey BOM - ISA_ES1868 (original through-hole board, rev 1.2)

DigiKey order list for `ISA_ES1868.kicad_pcb`, the through-hole board. References and quantities
come straight from the PCB file (quantities are per board). Every DigiKey part number was checked on
digikey.com on 2026-09-30; stock and prices are a snapshot. Upload file:
[BOM_tht_digikey.csv](BOM_tht_digikey.csv).

**Ordering:** in DigiKey's BOM Manager (or myLists → *Upload a list*) upload the CSV, map the columns
(*Reference Designator*, *DigiKey Part Number*, *Quantity*; or map the references to *Customer
Reference* to get them printed on each bag) and set the number of boards. Delete the last two lines
(U3, U7) first — DigiKey doesn't sell those. Roughly $43 per board at single-board prices, excluding
U3/U7.

Lines marked **AUDIO** are in, or reference, the audio signal path and use audio-grade parts (see
[Audio-grade choices](#audio-grade-choices)).

| Reference Designator | Description | DigiKey Part Number | Qty |
|---|---|---|--:|
| C1, C2, C3, C4, C5, C17, C53 | Capacitor 100nF 50V 10% X7R ceramic, radial 5mm pitch - supply decoupling (not in audio path) - TDK FG28X7R1H104KNT06 | 445-173588-1-ND | 7 |
| C6, C7, C11, C40, C41 | Capacitor 100nF 100V 5% polyester (PET) film, radial 5mm pitch, 7.2x2.5mm - **AUDIO:** mic coupling (C6), CMR/VREF reference bypass (C7, C11), amp Zobel (C40, C41) - KEMET R82EC3100AA70J | 399-5861-ND | 5 |
| C8, C9, C27, C28, C29, C30, C31, C32, C47, C48 | Capacitor 220nF 63V 5% polyester (PET) film, radial 5mm pitch, 7.2x2.5mm - **AUDIO:** signal coupling (codec FM/DSP out, line in, AUX A/B, amp input) - KEMET R82DC3220AA60J | 399-9686-ND | 10 |
| C10, C33, C46 | Capacitor 1nF 50V 5% C0G/NP0 ceramic, radial 5mm pitch - **AUDIO:** codec output filter pole (C10, C33); reset filter (C46) - TDK FG28C0G1H102JNT06 | 445-173473-1-ND | 3 |
| C12, C13 | Capacitor 10uF 50V aluminium electrolytic, low-ESR long-life (Panasonic FR-A), 105C 5000h, 5 x 11mm, 2.0mm pitch - codec analog supply (C12), mic-bias filter (C13) - Panasonic EEU-FR1H100 | P124233-ND | 2 |
| C14, C43 | Capacitor 47uF 35V aluminium electrolytic, low-impedance long-life (Rubycon YXJ), 105C 5000h, 5 x 11mm, 2.0mm pitch - codec CMR audio reference (C14), amp bias / ripple rejection (C43) - Rubycon 35YXJ47M5X11 | 1189-2919-ND | 2 |
| C15, C16 | Capacitor 10pF 50V +/-0.5pF C0G/NP0 ceramic, radial 2.5mm pitch - crystal load - TDK FG18C0G1H100DNT06 | 445-173169-1-ND | 2 |
| C18, C19, C20, C21, C23, C24, C25, C26, C38, C39 | Capacitor 10nF 50V 5% C0G/NP0 ceramic, radial 5mm pitch - **AUDIO:** amp feedback (C38, C39); joystick timing (stable C0G) - TDK FG28C0G1H103JNT06 | 445-173474-1-ND | 10 |
| C22 | Capacitor 150pF 100V 5% C0G/NP0 ceramic, radial 5mm pitch - gameport +5V filter - TDK FG28C0G2A151JNT06 | 445-173528-1-ND | 1 |
| C34, C35 | Capacitor 470uF 16V aluminium electrolytic, AUDIO GRADE (Nichicon KA), 105C, 8 x 11.5mm, 3.5mm pitch - **AUDIO:** speaker output coupling - Nichicon UKA1C471MPD | 493-15326-ND | 2 |
| C36, C37 | Capacitor 10uF 25V aluminium electrolytic, BI-POLAR, AUDIO GRADE (Elna RBD), 5 x 11mm, 2.0mm pitch - **AUDIO:** line-out coupling (non-polar) - Elna RCRBD100K1TC11300T (discontinued, sold from DigiKey stock) | 604-RCRBD100K1TC11300T-ND | 2 |
| C42 | Capacitor 100uF 35V aluminium electrolytic, low-impedance long-life (Rubycon YXJ), 105C 7000h, 6.3 x 11mm, 2.5mm pitch (6.3mm body fits here) - amp +12V supply bulk - Rubycon 35YXJ100M6.3X11 | 1189-2260-ND | 1 |
| C50, C51, C52 | Capacitor 10uF 50V aluminium electrolytic, 105C, 5 x 11mm, 2.0mm pitch - +5V and -12V rail bulk (not in audio path) - KEMET ESH106M050AC3AA | 399-6543-ND | 3 |
| R1, R2 | Resistor 7.5k thin metal film 1% 50ppm 0.4W, axial 0204 - **AUDIO:** mic bias - Vishay MBA02040C7501FCT00 | 56-MBA02040C7501FCT00CT-ND | 2 |
| R3, R4, R5, R6, R8, R9, R10, R11, R12, R13 | Resistor 2.2k thin metal film 1% 50ppm 0.4W, axial 0204 - joystick / MIDI - Vishay MBA02040C2201FCT00 | BC3258CT-ND | 10 |
| R7, R32, R33 | Resistor 10k thin metal film 1% 50ppm 0.4W, axial 0204 - **AUDIO:** amp input divider (R32, R33) - Vishay MBA02040C1002FCT00 | BC3239CT-ND | 3 |
| R14, R15, R16, R17 | Resistor 1k thin metal film 1% 50ppm 0.4W, axial 0204 - EEPROM / volume-button lines - Vishay MBA02040C1001FCT00 | BC3238CT-ND | 4 |
| R18 | Resistor 22k thin metal film 1% 50ppm 0.4W, axial 0204 - MCLK pull-down - Vishay MBA02040C2202FCT00 | BC3259CT-ND | 1 |
| R22, R23 | Resistor 33k thin metal film 1% 50ppm 0.4W, axial 0204 - **AUDIO:** amp input - Vishay MBA02040C3302FCT00 | BC3501CT-ND | 2 |
| R24, R25, R26, R27 | Resistor 820k thin metal film 1% 50ppm 0.4W, axial 0204 - **AUDIO:** amp feedback - Vishay MBA02040C8203FRP00 | BC820KXCT-ND | 4 |
| R28, R29 | Resistor 2.7 ohm thin metal film 1% 50ppm 0.4W, axial 0204 - **AUDIO:** amp Zobel - Vishay MBA02040C2708FC100 | 56-MBA02040C2708FC100CT-ND | 2 |
| R30, R31 | Resistor 15k thin metal film 1% 50ppm 0.4W, axial 0204 - **AUDIO:** amp input divider - Vishay MBA02040C1502FCT00 | BC3248CT-ND | 2 |
| R34, R35, R36, R37 | Resistor 1M thin metal film 1% 50ppm 0.4W, axial 0204 - joystick - Vishay MBA02040C1004FCT00 | BC3241CT-ND | 4 |
| L1, L2, L3 | Ferrite bead on lead, axial, 70 ohm @ 100MHz, 3.5 x 4.4mm, 22AWG copper lead (bend to 7.62mm) - supply / ground filters - Fair-Rite 2743001112 (as used on the original build) | 1934-1476-1-ND | 3 |
| L4, L5, L6, L7, L8, L9, L12 | Ferrite bead 0805 SMD (solder side), 330 ohm @ 100MHz, 1A, 0.07 ohm - **AUDIO:** in series with line in/out, AUX A and mic - Murata BLM21PG331BH1D (exact PCB value) | 490-BLM21PG331BH1DCT-ND | 7 |
| L10, L11 | Ferrite bead 0805 SMD (solder side), 600 ohm @ 100MHz, 2A, 0.1 ohm - **AUDIO:** speaker outputs; replaces the Wurth 742792093 on the PCB (200mA, 0.6 ohm: loses ~0.6dB and damping) - TDK MPZ2012S601AT000 | 445-MPZ2012S601AT000CT-ND | 2 |
| U1 | Voltage regulator 78L05 5V 100mA, TO-92 straight leads (1=OUT 2=GND 3=IN) - analog +5V (VDDA) from +12V - ST L78L05ACZ | 497-2952-ND | 1 |
| U2 | IC 74LS138 3-to-8 decoder, DIP-16 - ISA address decode - TI SN74LS138N (a CD74HCT138E also works) | 296-1639-5-ND | 1 |
| U4 | EEPROM 93LC66C 4Kbit Microwire, DIP-8, ORG-pin C-version (board selects x8) - OPTIONAL: only for External ROM mode (JP1/JP2 1-2), must be programmed off-board - Microchip 93LC66C-I/P | 93LC66C-I/P-ND | 1 |
| U4 (socket) | IC socket DIP-8 0.3in, machined pins, gold contacts - for U4 - Mill-Max 110-43-308-41-001000 | ED90032-ND | 1 |
| U7 (socket) | IC socket DIP-14 0.3in, machined pins, gold contacts - for U7 (protects the scarce LM1877) - Mill-Max 110-43-314-41-001000 | ED90033-ND | 1 |
| Y1 | Crystal 14.31818MHz, HC-49/U full height, fundamental, parallel 18pF, +/-20ppm (lay flat, strap case to the ground pad) - Abracon AB-14.31818MHZ-B2 | 535-AB-14.31818MHZ-B2CT-ND | 1 |
| J1 | Jack 3.5mm stereo, right angle THT, 5-pin (switch pins unused here, they anchor the jack), light blue (PC99 line in), plastic 6.8mm nose, no thread - LINE IN - Kycon STX-3120-5B-284C | 2092-STX-3120-5B-284C-ND | 1 |
| J2, J7 | Jack 3.5mm stereo, right angle THT, 5-pin (switch pins unused here, they anchor the jack), lime (PC99 line out / speakers), plastic 6.8mm nose, no thread - LINE OUT, SPKR OUT - Kycon STX-3120-5B-577C | 2092-STX-3120-5B-577C-ND | 2 |
| J3 | D-sub DA-15 female, right angle PCB, 0.318in footprint, 4-40 threaded inserts + board locks, gold flash - joystick / MIDI - NorComp 182-015-213R531 | 182-15FE-ND | 1 |
| J3 (screwlocks) | Female screwlock 4-40, 3/16in hex, 6.0mm thread - clamps the 3D-printed bracket to J3 - NorComp SFSO4405NR | SFSO4405NR-ND | 2 |
| J5 | Pin header 2x13 male, 2.54mm, vertical, gold - wavetable (Wave Blaster) connector - Sullins PBC13DAAN | 35-PBC13DAAN-ND | 1 |
| J8 | Pin header 1x2 male, 2.54mm, right angle, gold - mic input - Sullins PBC02SBAN | 35-PBC02SBAN-ND | 1 |
| J9 | Pin header 1x3 male, 2.54mm, vertical, gold - AUX A (CD audio) input - Sullins PBC03SAAN | 35-PBC03SAAN-ND | 1 |
| J10 | Pin header 2x3 male, 2.54mm, vertical, gold - volume buttons - Sullins PBC03DAAN | 35-PBC03DAAN-ND | 1 |
| U3 | ESS ES1868F AudioDrive sound chip, LQFP-100 - buy NOS elsewhere (see [below](#not-available-from-digikey)) | *Not stocked by DigiKey* | 1 |
| U7 | TI/National LM1877N-9 dual 2W audio amp, DIP-14 (obsolete) - buy NOS elsewhere (see [below](#not-available-from-digikey)) | *Not stocked by DigiKey* | 1 |

Not listed because there is nothing to buy: JP1–JP8 are solder-bridge jumpers and J11 is the ISA edge
connector, both part of the PCB. The ISA bracket is 3D printed (see [bracket notes](#notes-for-the-3d-printed-bracket)).
Jumper shunts such as Harwin M7582-05 have no use on this board: it has no 2.54 mm jumper headers.

## Audio-grade choices

* **Small capacitors in the signal path:** polyester (PET) film for 100–220 nF (signal coupling, mic
  input, CMR/VREF reference bypass, amplifier Zobel) and C0G/NP0 ceramic for ≤10 nF (amplifier
  feedback, codec output filter). Neither has the voltage-dependent distortion or microphonics of X7R,
  which is used only for supply decoupling. C0G isn't made at 100–220 nF in a size that fits, and
  polypropylene film at these values is thicker than the 3 mm that the tight clusters (C8/C9, C29–C32,
  C47/C48) allow — the PET parts listed are 2.5 mm.
* **Electrolytics:** C34/C35 (speaker coupling) are Nichicon KA audio-grade (not for new designs, but in
  stock). C36/C37 (line-out coupling) are Elna RBD bi-polar audio capacitors — discontinued, sold from
  DigiKey's remaining stock (about 9,900 pcs); if they run out use Panasonic EEU-FR1H100
  (P124233-ND). No other audio-grade electrolytic that fits the 5 mm footprints is available at DigiKey
  (Nichicon MUSE/FW/KW/KT and Elna Silmic are obsolete there), so C12–C14, C42 and C43 use Panasonic
  FR-A / Rubycon YXJ low-impedance 105 °C long-life types.
* **Resistors:** Vishay MBA0204 thin metal film, 1 %, 50 ppm/K (low current noise). The 0204 body on
  the 0207 footprint is deliberate: Vishay allows it to be bent to the 7.62 mm pitch, while the 0207-size
  MBB version needs at least 10 mm.
* **Connectors:** gold-plated headers, D-sub and IC-socket contacts; the jacks are tin-plated.

## Differences from the values printed on the PCB

* **L10, L11:** TDK MPZ2012S601AT000 instead of the Würth 742792093 on the board. The Würth is a
  200 mA signal bead with 0.6 Ω in series with each speaker line (about 0.6 dB loss, lower damping);
  the TDK is rated 2 A / 0.1 Ω on the same 0805 pads. Exact original part: 732-1609-1-ND.
* **C42:** a 6.3 mm can on the 5 mm footprint (there is room around it).

## Not available from DigiKey

* **U3 ES1868F** and **U7 LM1877N-9** (DIP, obsolete) are new-old-stock parts. Sources and the ES1869F
  fallback are in the sourcing notes of
  [BOM_smd.md](BOM_smd.md#obsolete--hard-to-get-parts--investigated-alternatives) (same parts on both boards). Fit a
  socket for U7.
* TI still makes the LM1877 in wide SOIC-14 (LM1877MX-9/NOPB, DigiKey 296-44354-1-ND, active). It only
  fits this board on a SOIC-14 (7.5 mm body) to DIP-14 adapter, with less thermal headroom (114 vs
  79 °C/W).

## Assembly notes

* **U4 is optional.** With JP1 and JP2 bridged 2–3 the ES1868 uses its internal PnP ROM (the socket is
  empty on the photographed board). External ROM mode (1–2) needs a 93xx66**C** programmed off-board with
  the PnP data (see [eeprom/](eeprom/)); the board ties the ORG pin low for ×8. A 93xx66B (×16 only)
  won't work.
* L4–L12 are 0805 SMD beads on the solder side.
* C36/C37 are bi-polar, so either orientation is fine. C52 sits on −12 V: its + lead goes to GND (the
  square pad).
* J3's board-lock holes are Ø2.87 mm (NorComp recommends Ø3.05 mm): expect a firm press, or ream
  lightly.
* **Jacks:** Kycon STX-3120 in PC99 colours (blue line in, lime line out / speaker out), same pins and
  posts as the STX-3100 the original build used. The 5-pin (switched) version is used on purpose: its
  two switch pins go into pads 4/5, which are unconnected on this board, so they only add solder joints
  — the jacks have no nut, so the joints take the plug forces. DigiKey had only 9 of the blue 5B on
  2026-09-30; fallbacks are the 3-pin blue STX-3120-3B-284C (2092-STX-3120-3B-284C-ND) or the black
  5-pin STX-3120-5B (2092-STX-3120-5B-ND).
* The jack footprint's locating-post holes are Ø1.2 mm; if a jack won't seat, trim the posts or open
  the holes to 1.6 mm.
* **Left/right:** Kycon jacks put the tip on pad 3. The PCB wires LINE OUT (J2) with tip and ring the
  other way round from LINE IN (J1) and SPKR OUT (J7), so LINE OUT is correct but LINE IN and SPKR OUT
  come out left/right swapped — as on the original build. Swap the speaker plugs if it matters.
* Y1 lies flat; strap its case to the ground pad.

## Notes for the 3D-printed bracket

* **Jacks:** plain Ø6.8 mm plastic nose, no thread or nut — make the holes about 7.0–7.2 mm. The
  opening centres are 6.5 mm above the PCB top surface and 13.46 mm apart (J7, J2, J1 in order towards
  the ISA fingers), and each nose ends about 3.0 mm beyond the PCB edge, so keep the wall at the jacks
  under 3 mm (thinner is better) so plugs seat fully.
* **DA-15:** two 4-40 female screwlocks clamp the bracket to J3's threaded inserts. Thread length needed
  ≈ wall + ~1 mm flange + engagement: the listed SFSO4405NR (6.0 mm) suits 1.5–2.5 mm walls;
  SFSO4404NR (5.0 mm, SFSO4404NR-ND) for thinner and SFSO4401NR (7.9 mm, SFSO4401NR-ND) for thicker
  walls.
