# Changelog — Kgotso Koete's Build Fork

> **Fork**: [Kgotso-Koete/pilomar](https://github.com/Kgotso-Koete/pilomar)  
> **Upstream**: [Short-bus/pilomar](https://github.com/Short-bus/pilomar)  
> **Purpose**: Personal build fork to track my own observatory build progress, sourcing decisions, and local modifications. Not intended as upstream contributions.  
> **Format**: [Keep a Changelog](https://keepachangelog.com/en/1.0.0/)

---

## [Unreleased] — 2 November 2026

### Added
- `docs/BUILD_TRACKER.md` — live build tracker with Mermaid diagrams: build stage overview, hardware config, power architecture, DRV8825 current reference, wire size guide, drive train layout, 3D print progress, OS/software setup sequence, open questions, and build log
- `docs/BILL_OF_MATERIALS.md` — full engineering BOM with status columns, verified SA supplier links, ZAR pricing, quantity discrepancy flags, and gap-fills from community sheet
- `CHANGELOG.md` — this file

### Changed / Renamed
- `docs/Electronics Project BOMS - Pi-Lomar Mini Observatory.pdf` → `docs/OBSOLETE_Legacy_Bill_of_Materials.pdf`
- `docs/Electronics Project BOMS - Pi-Lomar Mini Observatory.csv` → `docs/OBSOLETE_Legacy_Bill_of_Materials.csv`
- Community BOM saved as `docs/OBSOLETE_Reference_BOM.csv`

### Build Progress
- **Electronics**: PCB-2023-12-14 (Tiny + DRV8825) built and tested ✅ — Pilomar running on Raspberry Pi 5 (8GB), both NEMA17 motors responded
- **DRV8825 VREF**: U1 = 0.33V (0.66A) · U2 = 0.35V (0.70A)
- **Bore size**: 5mm decided — M5 STL variants used throughout
- **`B.13.2.AzimuthDriveM5`**: ✅ Printed — PETG · Ender 3 V2 · ~3h24m
- **`AG.13.6.RingGear`**: 🖨️ Printing — PETG · ~15h34m
- **250mm Lazy Susan bearing**: ✅ Arrived — [Perfect Tech SA](https://perfecttech.co.za) · Order #6910 · 18 May 2026 · R200.00
- **Power wiring**: 1.0mm² Helukabel FLRY-B decided — Communica CAB28524 (red) + CAB28522 (black) · ❌ not yet purchased

### Decisions & Rationale
- **Bore**: 5mm over 6mm — M5 hardware more common in SA market
- **OS**: Trixie 64-bit confirmed viable — `buildpilomar_trixie` script exists in repo
- **Power wire**: 1.0mm² minimum on 12V rail — 22 AWG signal wire not adequate for motor power
- **PSU**: Mean Well LRS-100-12 (8.5A) — 8.5A is capacity, actual tracking draw ~1.5–2.5A

---

## [v1.3.0-build.0] — Prior to 2 November 2026

> Build commits made before CHANGELOG was introduced.

### My Commits
| Commit | Description |
|--------|-------------|
| `cfdb1b0` | Merge upstream Short-bus/pilomar into my fork |
| `c7b7b41` | Untrack large hip_main.dat file |
| `cb35c3f` | Get Pilomar working on Raspberry Pi 5 Trixie 64-bit OS 8GB |

---

## Upstream Syncs (Short-bus/pilomar)

> Upstream changes merged into this fork. Not my own work.

| Upstream version | Commit | Description |
|-----------------|--------|-------------|
| v1.3.0 | `df60a73` | Merge PR #125 — Messier and NGC json files updated |
| v1.3.0 | `a4c24fc` | Messier and NGC json files updated |
| v1.3.0 | `346ecc3` | Trixie-specific build script added |
| v1.3.0 | `869125a` | Pilomar 1.3.0 update |

---

## Planned (next actions)

- [ ] Order 1:60 worm gear sets, 5mm bore ×2 (AliExpress)
- [ ] Contact FDM3D Benoni (083 395 1909) — confirm they can cut 5mm D-shaft to 110mm
- [ ] Purchase Communica power wire — CAB28524 red + CAB28522 black, 5–6m each + crimp terminals
- [ ] Complete 3D print queue — Foundation section next
- [ ] Watch Step 7 assembly video before printing platform — resolve DaM4/DaM5 quantity discrepancy
- [ ] Confirm: Tiny2040 or Tiny2350 on PCB
- [ ] Confirm: OS on Pi 5 — Trixie or Bookworm
- [ ] Decide inner wall version: P.14.0 or P.13.6
