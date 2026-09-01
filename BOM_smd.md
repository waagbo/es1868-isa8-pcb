# Bill of Materials — ISA_ES1868_smd (SMD variant)

BOM for the SMD conversion of the rev 1.2 board (see [SMD_CONVERSION.md](SMD_CONVERSION.md)).
All SMD passives are 0805 with hand-solder footprints. Every DigiKey SKU below was verified on
DigiKey product pages on 2026-09-01 (stock changes — treat quantities as a snapshot). Mouser
cells say *search MPN* where the SKU couldn't be verified (Mouser blocks automated checks);
the MPN finds the part. Machine-readable version: [BOM_smd.csv](BOM_smd.csv).

**Audio path** marks parts where dielectric/type quality audibly matters — see notes at the bottom.

## SMD capacitors (0805)

| Qty | Refs | Value | Type | MPN | DigiKey | LCSC | Audio path |
|----:|---|---|---|---|---|---|---|
| 12 | C1–C7, C11, C17, C40, C41, C53 | 100 nF | X7R 50 V | KEMET C0805C104K5RACTU | 399-C0805C104K5RACTUCT-ND | C1711 (Samsung) | C6 (mic), C40/C41 (Zobel) |
| 10 | C8, C9, C27–C32, C47, C48 | 220 nF | X7R 50 V | KEMET C0805C224K5RACTU | 399-C0805C224K5RACTUCT-ND | C5378 (Samsung) | **yes — all coupling caps** |
| 10 | C18–C21, C23–C26, C38, C39 | 10 nF | **C0G** 50 V | KEMET C0805C103J5GACTU | 399-C0805C103J5GACTUCT-ND | C63849 (FH) | C38/C39 (amp feedback) |
| 3 | C10, C33, C46 | 1 nF | **C0G** 50 V | KEMET C0805C102J5GACTU | 399-C0805C102J5GACTUCT-ND | C1791 (Samsung) | C10/C33 (codec filters) |
| 1 | C22 | 150 pF | **C0G** 50 V | KEMET C0805C151J5GACTU | 399-C0805C151J5GACTUCT-ND | search `0805CG151J500NT` | no |
| 2 | C15, C16 | 10 pF | **C0G** 50 V | KEMET C0805C100J5GACTU | 399-C0805C100J5GAC7800CT-ND | C123640 (Walsin) | no — crystal load |
| 5 | C12, C13, C50–C52 | 10 µF | X5R 25 V | TDK C2012X5R1E106K085AC | 445-14387-1-ND | C15850 (Samsung CL21A106KAYNNNE) | no |

The Samsung CL21A106KAYNNNE (10 µF) was **0-stock at DigiKey** (restock ~2026-10-12) — the TDK
part is the verified in-stock equivalent there; at LCSC the Samsung is the pick (1.9 M pcs).

## Through-hole electrolytics (kept THT on purpose — audio path)

| Qty | Refs | Value | Size | Part (DigiKey pick) | DigiKey | LCSC | Role |
|----:|---|---|---|---|---|---|---|
| 2 | C36, C37 | 10 µF 50/63 V | ø5 · p2 | Rubycon **63PX10MEFC5X11** | 1189-1474-ND (4,999) | **C1579840 (Nichicon Muse FG UFG1H100MDM)** | line-out coupling |
| 2 | C14, C43 | 47 µF 25 V | ø5 · p2 | Rubycon **25PK47MEFC5X11** | 1189-25PK47MEFC5X11-ND (2,999) | C22320 (Chengx, 16 V) | VREF / amp bias |
| 1 | C42 | 100 µF 16 V | ø5 · p2 | Nichicon UVR1C101MDD1TA | 493-6095-1-ND (1,439 — EOL when depleted) | C2960196 (HRK) | amp supply bulk |
| 2 | C34, C35 | 470 µF 16 V | ø8 · p3.5 | Panasonic **ECA-1CM471** | P5141-ND | C43823 (Chengx) | speaker-out coupling |

The audio-grade Nichicons originally suggested here (Muse FG UFG1H100MDM, FW UFW1E470MDD) are
**obsolete at DigiKey** — the Rubycon PX/PK parts above are the verified in-stock same-size subs.
If you want the genuine Muse FG for C36/C37, LCSC still stocks it (C1579840), Mouser lists
647-UFG1H100MDM (stock unverified). Backup for C42: Panasonic ECA-1CM101 (12,750 pcs).

## Resistors (0805, thick film 1 %)

Yageo RC0805FR-07 series (all DigiKey SKUs verified in stock); UNI-ROYAL 0805W8F at LCSC.

| Qty | Refs | Value | Yageo MPN | DigiKey | LCSC |
|----:|---|---|---|---|---|
| 2 | R28, R29 | 2.7 Ω | RC0805FR-072R7L | 13-RC0805FR-072R7LCT-ND | C137450 (5 %, fine here) |
| 4 | R14–R17 | 1 kΩ | RC0805FR-071KL | 311-1.00KCRCT-ND | C17513 |
| 10 | R3–R6, R8–R13 | 2.2 kΩ | RC0805FR-072K2L | 311-2.20KCRCT-ND | C17520 |
| 2 | R1, R2 | 7.5 kΩ | RC0805FR-077K5L | 311-7.50KCRCT-ND | C17807 |
| 3 | R7, R32, R33 | 10 kΩ | RC0805FR-0710KL | 311-10.0KCRCT-ND | C17414 |
| 2 | R30, R31 | 15 kΩ | RC0805FR-0715KL | 311-15.0KCRCT-ND | C17475 |
| 1 | R18 | 22 kΩ | RC0805FR-0722KL | 311-22.0KCRCT-ND | C17560 |
| 2 | R22, R23 | 33 kΩ | RC0805FR-0733KL | 311-33.0KCRCT-ND | C17633 |
| 4 | R24–R27 | 820 kΩ | RC0805FR-07820KL | 311-820KCRCT-ND | C50136 (restocked, 23 k) |
| 4 | R34–R37 | 1 MΩ | RC0805FR-071ML | 311-1.00MCRCT-ND | C17514 |

LCSC 820 k alternates if C50136 dips again: C2771112 (UNI-ROYAL CQ), C7431038 (thin film 0.1 %).

## Ferrite beads (0805)

| Qty | Refs | Part | DigiKey | LCSC | Notes |
|----:|---|---|---|---|---|
| 10 | L1–L9, L12 | Murata **BLM21PG331SN1D** (330 Ω @ 100 MHz, 1.5 A) | 490-5988-1-ND | C74764 | Board previously said `BLM21PG331BH1D` — real Murata PN but not distributor-stocked; SN1D is the stocked equivalent. L1–L3 were axial beads, now identical to the rest. |
| 2 | L10, L11 | TDK **MPZ2012S601AT000** (600 Ω @ 100 MHz, **2 A**) | 445-MPZ2012S601AT000CT-ND (1.1 M) | C1017 (Sunlord GZ2012D601TF, 500 mA) | **Recommended replacement** for the original Würth 742792093 (2.2 kΩ but only 200 mA — marginal vs ~350 mA speaker peaks). Original Würth: 732-1609-1-ND if you want to match rev 1.2 exactly. |

## Semiconductors

| Ref | Part | Package | DigiKey | LCSC | Notes |
|---|---|---|---|---|---|
| U3 | **ES1868F** | LQFP-100 | — | — | NOS only — see alternatives below. |
| U1 | ST L78L05ABUTR | SOT-89 | 497-1181-1-ND | C42738 | Was TO-92; pin functions identical (1=OUT, 2=GND, 3=IN). |
| U2 | TI SN74LS138D | SOIC-16 | **296-3648-5-ND** (direct, 1,179) | C5965 (74HCT138D) | Avoid the Marketplace listing that ranks first in search. Cut tape: SN74LS138DR = 296-14883-1-ND (8,360). Nexperia 74HCT138D,653 is a drop-in modern alternative. |
| U4 | Microchip **93AA66C-I/SN** | SOIC-8 | **93AA66C-I/SN-ND** (3,283) | C153277 | **ORG pin is grounded on this board (×8 org)** → an ORG-selectable **C-variant is required**; never 93LC66A/B (fixed org). 93AA66C runs 1.8–5.5 V, fine at 5 V, deepest stock. Also works: 93LC66C-I/SN (93LC66C-I/SN-ND, 410) and DIP 93LC66C-I/P (93LC66C-I/P-ND, 340). |
| U7 | **LM1877N-9** | DIP-14 THT | obsolete | — | NOS still cheap — see alternatives below. Fit a DIP-14 socket. |
| Y1 | ECS **ECS-143-20-4X** 14.31818 MHz HC-49/US 20 pF | THT | **X1081-ND** (10,892, direct) | C2206 (YXC, 20 pF) | 18 pF option, also DigiKey-direct: Abracon ABLS-14.31818MHZ-B4-T = 535-10222-1-ND (772). The earlier B2-T suggestion was Marketplace-only. |

## Connectors & hardware

| Qty | Refs | Part | DigiKey | Mouser | LCSC | Notes |
|----:|---|---|---|---|---|---|
| 3 | J1, J2, J7 | Same Sky **SJ1-3553NG** 3.5 mm stereo, long bushing | CP1-3553NG-ND (**0 stock — restock ~2026-10-12**) | search MPN | — | Long bushing clears the bracket (per `docs/`). **In stock now:** SJ1-3523N = CP1-3523N-ND (233 k, short bushing), SJ1-3533N = CP1-3533N-ND (11 k, mid bushing), Kycon STX-3100-**3C** = 2092-STX-3100-3C-ND (1,883). LCSC PJ325 is 5-pin — not compatible. |
| 1 | J3 | DA-15 female right-angle (NorComp 182-015-213R531) | 182-15FE-ND | 152-3415 (Kobiconn) | C77835 (CONNFLY) | Check mounting holes vs. the 152-3415 drawing in `docs/`. |
| 1 | J5 | 2×13 header (Sullins PRPC013DAAN-RC) | 35-PRPC013DAAN-RC-ND (639) | search MPN | C2333 (cut 2×40) | Wavetable. |
| 1 | J10 | 2×3 header (PRPC003DAAN-RC) | 35-PRPC003DAAN-RC-ND (2,857) | search MPN | C65114 | Volume buttons. |
| 1 | J9 | 1×3 header (PRPC003SAAN-RC) | 35-PRPC003SAAN-RC-ND (455) | search MPN | C49257 | AUX in (carries audio). |
| 1 | J8 | 1×2 right-angle: snap 2 pins off Sullins PRPC040SBAN-M71RC | S1111EC-40-ND (5,912) | search MPN | C2334 (RA strip) | Dedicated 1×2 RA part is 0-stock at DigiKey. Mic in (carries audio). |
| 1 | — | Keystone **9200-3** ISA bracket | 36-9200-3-ND | search 9200-3 | — | Only the DA-15 cutout is punched — jack holes need drilling or a custom bracket. `docs/` also references Keystone 9204-1. |
| 1 | — | DIP-14 socket for U7 | generic | generic | generic | Strongly recommended — LM1877 scarcity. |

JP1–JP8 are solder jumpers and J11 is the ISA edge — part of the PCB, nothing to buy.

## Obsolete & hard-to-get parts — investigated alternatives

### U7 — LM1877N-9 (dual 2 W amp, obsolete since ~2008)

NOS supply is still healthy and cheap (checked 2026-09-01):

| Source | Status | Price | Confidence |
|---|---|---|---|
| Quest Components | 18 pcs in stock | $14.06 (qty 1) / $9.37 (8+) | verified count, NSC-branded — most credible |
| Jameco #23288 | listed | $3.35 | reputable seller, "Major Brands" house label |
| UTsource | in stock | $2.18 | gray-market broker, authenticity unverified |
| eBay | many singles | ~$3–8 | US/UK surplus singles look genuine; avoid 50-pc CN lots |
| Rochester Electronics | **no listing** | — | — |

Pin-compatible siblings LM377/LM378 are verified pin-identical but equally obsolete and
broker-only — no advantage over buying LM1877 itself.

**If redesigning the amp section** (the speaker jack is ground-referenced, so any replacement
must produce single-ended outputs — BTL/class-D parts are out):

* **Best: 2× TI LM386N-4** (DIP-8, ~$1, active production, DigiKey/Mouser). Rated 5–18 V —
  the only active option comfortably above the 12 V rail — and its default gain (26 dB with
  pins 1/8 open) is exactly what the LM1877 network is set to, so no gain parts are needed.
  ~0.5–0.8 W/ch at 12 V vs the LM1877's 1.3 W — plenty for the use case. Two DIP-8s occupy
  roughly the DIP-14's area.
* **Budget one-chip: UTC TDA2822** (DIP-8, LCSC C73295, $0.09; SOP-8 C73296; HGSEMI TDA2822N
  C20613256). Caveats: 12 V is the *operating maximum* (15 V abs max) on the very rail this
  board provides, and gain is fixed at ~40 dB so the input needs attenuation. Buy UTC/HGSEMI
  branded from LCSC — "ST TDA2822M" from marketplaces is a common counterfeit that dies at 12 V.
* Ruled out: NJM2073D (obsolete at DigiKey/Mouser, weak), TEA2025 clones (12 V limit, DIP-16,
  ≥36 dB gain floor), HXJ8002 (mono), PAM/class-D (BTL-only).

### U3 — ES1868F

* Sourcing today: UTsource ~$16 ("in stock"), AliExpress single pcs and 5-pc lots (~$4–8
  typical, unverified), eBay mostly complete donor cards ($38–50). Buy a spare; broker
  authenticity is never guaranteed.
* **ES1869F is a workable fallback on this exact PCB** — verified by diffing the pin tables of
  `docs/ES1868-ESS.pdf` against `docs/es1869techmanual.pdf`: the PQFP-100 pinout is identical
  except four pins. On this board: pin 60 is tied to GND, which on the ES1869 selects
  MODE=0 = ES1868-compatible pin functions ✔; pin 42's C11 (100 nF to GND) suits both ✔;
  **pin 25 becomes MONO_OUT — JP1 must be left OPEN** (never strap it to VCC/GND) ⚠;
  pin 26 (VDDD on the '68) becomes MONO_IN and sits at 5 V — ugly but muted-by-default, and
  community swap reports (VOGONS) confirm working cards ⚠. With this board's ES1868 EEPROM
  data, Windows needs the ES1868 drivers (ES1869 drivers refuse to load); DOS is unaffected.
* ES688F is **not** a drop-in (earlier generation, no ESFM/PnP, needs companion chips).

### Other risk items

* **U4 EEPROM**: 93AA66C-I/SN has the deepest stock (3,283); onsemi CAT93C66VI-GT3 confirmed
  ORG-compatible but DigiKey-direct stock was 0 (Marketplace only) — skip unless restocked.
* **Y1 crystal**: both listed options are DigiKey-direct and in stock; the earlier
  ABLS-…-B2-T suggestion was Marketplace-only.
* **J1/J2/J7 jacks**: primary long-bushing part is backordered to Oct 2026 — the three
  in-stock alternatives above all fit the footprint (bushing length differs; check bracket fit).
* **820 kΩ at LCSC**: restocked (23 k pcs) with two verified alternates listed above.

## Audio-path capacitor notes

* The original card already used ceramic discs in every small-value audio position, so 0805
  MLCCs are not a downgrade. Use **50 V X7R** for the 100/220 nF coupling positions (voltage
  headroom keeps capacitance-vs-voltage distortion negligible at ~1 Vrms line level) and
  **C0G/NP0** everywhere ≤10 nF. Avoid X5R/Y5V in any audio position.
* The electrolytics that sit **in series with audio** (C36/C37 line out, C34/C35 speaker out)
  stayed through-hole so standard or audio-grade radials can be used — SMD ceramics of these
  values would distort, and THT radials are the easiest parts on the board to solder anyway.
* The five 10 µF that were converted to MLCC (C12, C13, C50–C52) are purely supply/bias
  filters — no audio signal crosses them.
