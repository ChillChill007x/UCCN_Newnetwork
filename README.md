# UCCN Simulator
**Universal Causal Communication Network — Research Simulator**
**Version:** 4.0 | **Phase:** 0 — Research & Foundation (2024–2035)

---

## ภาพรวม / Overview

UCCN Simulator เป็นเครื่องมือวิจัยสำหรับจำลองเครือข่ายการสื่อสารระหว่างดาวที่คงความสอดคล้องเชิงสาเหตุ (causally-consistent interstellar communication network) โดยบูรณาการ:

- **4 Signal Modes:** Photon, Neutrino, Graviton, DTN
- **Physics Engine:** Shannon Capacity, Lorentz γ, DTN Bundle Protocol v2
- **DAFT State Machine:** O₄, O₆, DARS — Dynamic Asymmetry Risk Score
- **Paradox Prevention:** Grandfather, Causal Loop, Bootstrap
- **Ethics/HITL:** EU AI Act Art.13/14 + Thai PDPA §26 compliance

---

## การใช้งาน / Quick Start

1. เปิด `demo.html` ในเบราว์เซอร์ (Chrome แนะนำ)
2. กด **DEMO** เพื่อโหลด 5 โหนดตัวอย่าง
3. เลือก Signal Mode (เลือกได้หลายอันพร้อมกัน)
4. เลือก Source/Destination Node
5. กด **TRANSMIT** เพื่อส่ง packet

---

## โครงสร้างโปรเจกต์ / Project Structure

```
uccn-simulator/
├── demo.html                    # Simulator (single-file app)
├── README.md                    # ไฟล์นี้
│
├── docs/
│   ├── Architecture_Spec.md     # สถาปัตยกรรมระบบ
│   ├── Book_Theoretical.md      # รากฐานทางทฤษฎี
│   ├── DAFT-Extended-Edition.md # DAFT Theory ขยาย
│   ├── Edition-Comparison.md    # เปรียบเทียบ Sprint
│   ├── Formalization.md         # Formal Specification
│   ├── Implementation_Plan.md   # แผนการพัฒนา
│   └── special-edition.md       # Design decisions & notes
│
├── planning/
│   ├── Role_and_Responsibility.md # RACI Matrix
│   └── Sprint_Plan.md             # Sprint planning
│
└── tests/
    ├── Coding.md                # Coding standards & test cases
    └── test_results.md          # Sprint 4 test report
```

---

## Key Concepts

| Term | คำอธิบาย |
|------|---------|
| **T-Offset** | Temporal Offset — ตำแหน่งเชิงเวลา วัดเป็น light-years |
| **DARS** | Dynamic Asymmetry Risk Score = O₄/O₆ |
| **O₄** | Causal Asymmetry = \|TX−RX\| / (TX+RX) |
| **O₆** | Causal Distance = avg link distance |
| **DAFT State** | PURE / CONSTRUCTIVE / DESTRUCTIVE / BOUNDARY |
| **HITL** | Human-in-the-Loop (3 levels) |
| **Causal Hash** | CRC32-based packet/node ID |

---

## Roadmap

| Phase | Years | Status |
|-------|-------|--------|
| Phase 0: Research & Foundation | 2024–2035 | 🔵 **NOW** |
| Phase 1: Limited Testing | 2036–2050 | ○ Planned |
| Phase 2: Solar System Network | 2051–2100 | ○ Future |
| Phase 3: Interstellar Bridge | 2101–2200 | ○ Future |
| Phase 4: Galactic Network | 2201–2500 | ○ Future |
| Phase 5: Universal UCCN | 2501–3000+ | ○ Future |

---

## License

© UCCN Research Project — Phase 0 Research Prototype

---

*Built with Vanilla JavaScript + HTML5 Canvas — No dependencies required*
