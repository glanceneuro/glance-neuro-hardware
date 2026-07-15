# GLANCE carrier board

KiCad design and production files for the **GLANCE** carrier PCB — a custom **4-layer**
carrier for a **MicroZed** (Xilinx Zynq-7020) SOM that interfaces **Intan RHD2000-style**
neural recording headstages. It is the hardware for the
[glance-neuro](https://github.com/glanceneuro/glance-neuro) acquisition system.

- **`glance-carrier.kicad_pro`** — the KiCad project (schematic + 4-layer board).
- **`constraints_and_pin_description/`** — MicroZed JX-connector pinout tables.
- **`ProductionBlobs/`** — fabrication packages (gerbers, BOM, placement) for revisions
  0.11, 1.0, and 1.1.

## License

This board design is licensed under **CERN-OHL-P v2** — see [`LICENSE`](LICENSE).

It is derived from the
[MicroZed carrier board](https://github.com/viktor-nikolov/MicroZed-carrier-board) by
**Viktor Nikolov**, released into the public domain under **CC0-1.0**.

## Revision notes

### Revision 1.1
Fixes a power-supply bug in 1.0 that prevented the 3.3 V and 2.5 V supplies from working.
Adds two ADCs and two DACs, connected to the PL on the VCCIO-34 side.

### Revision 1.0
Fixes the bug in 0.11 and transitions from 2-layer to 4-layer fabrication, allowing a
smaller, more case-friendly layout (digital IO on the same side of the PCB as the
Intan/Omnetics connectors, and USB-C power moved to the same side as the Ethernet
connector).

### Revision 0.11
Initial testing revision. It had an error in the USB-UART bridge connectivity, fixed with
a bodge.

## Credits

Derived from **Viktor Nikolov**'s
[MicroZed carrier board](https://github.com/viktor-nikolov/MicroZed-carrier-board)
(CC0-1.0). Parts and reference material reused from that project:

- **Symbols** (`Viktor_symbols`): `MicroZed_carrier_plug_JX1` (JX1),
  `MicroZed_carrier_plug_JX2` (JX2), `PMOD_socket` (PMODV1, PMODV3).
- **Footprints** (`Viktor`): `BergStak-100pos-plug-61083-101400` (JX1, JX2),
  `PMOD_Socket_Vertical` (PMODV3), `SOT-25-5_L3.0-W1.8-P0.95-LS3.0-BR` (U1).
- The `constraints_and_pin_description/` MicroZed JX pinout tables.

The Rice Owl silkscreen (`ELEC327-Kicad:RICE_OWL`) is from the Rice ELEC327 course library.
