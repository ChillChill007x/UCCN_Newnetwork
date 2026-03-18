# Sprint Plan — UCCN Simulator
**Detailed Sprint Planning & Task Breakdown**
**Version:** 2.0 | **Date:** 2026-03-19

---

## Sprint Planning Overview

### Velocity & Estimation
- Sprint duration: 2 สัปดาห์ต่อ Sprint
- Story points: Fibonacci scale (1, 2, 3, 5, 8, 13)
- Team velocity: ~30 points/sprint (estimated)

---

## Sprint 1 — Foundation
**Duration:** 2 สัปดาห์ | **Status:** ✅ Complete | **Points:** 28/30

### User Stories

| ID | Story | Points | Status |
|----|-------|--------|--------|
| S1-01 | ในฐานะนักวิจัย ฉันต้องการสร้างโหนดเครือข่ายพร้อมระบุตำแหน่งและ T-Offset เพื่อจำลอง network topology | 5 | ✅ |
| S1-02 | ในฐานะนักวิจัย ฉันต้องการส่ง Photon packet ระหว่างสอง node เพื่อดู animation การเดินทาง | 8 | ✅ |
| S1-03 | ในฐานะนักวิจัย ฉันต้องการให้ระบบป้องกัน Grandfather Paradox อัตโนมัติ | 5 | ✅ |
| S1-04 | ในฐานะนักวิจัย ฉันต้องการดู event log แบบ real-time ที่บันทึกทุก causal event | 3 | ✅ |
| S1-05 | ในฐานะนักวิจัย ฉันต้องการ simulation clock เพื่อ track เวลาจำลอง | 2 | ✅ |
| S1-06 | ในฐานะนักวิจัย ฉันต้องการ node ที่มี Causal Hash ID เฉพาะ เพื่อ traceability | 5 | ✅ |

### Sprint 1 Retrospective
- **What went well:** Canvas rendering สมบูรณ์เร็วกว่าคาด
- **What to improve:** CRC32 collision test ยังไม่ครอบคลุม edge cases
- **Action items:** เพิ่ม salt ใน node hash generation (→ ทำแล้วใน Sprint 2)

---

## Sprint 2 — Multi-Modal
**Duration:** 2 สัปดาห์ | **Status:** ✅ Complete | **Points:** 32/30

### User Stories

| ID | Story | Points | Status |
|----|-------|--------|--------|
| S2-01 | ในฐานะนักวิจัย ฉันต้องการส่งผ่าน Neutrino ที่ทะลุผ่านสสารได้ | 5 | ✅ |
| S2-02 | ในฐานะนักวิจัย ฉันต้องการส่งผ่าน Graviton สำหรับจำลอง gravitational wave | 5 | ✅ |
| S2-03 | ในฐานะนักวิจัย ฉันต้องการ DTN Store-and-Forward สำหรับ disruption-tolerant links | 8 | ✅ |
| S2-04 | ในฐานะนักวิจัย ฉันต้องการส่งหลาย mode พร้อมกัน (multi-modal) | 5 | ✅ |
| S2-05 | ในฐานะนักวิจัย ฉันต้องการเห็นค่าฟิสิกส์ (Shannon, Lorentz γ, DTN Bundle) | 5 | ✅ |
| S2-06 | ในฐานะนักวิจัย ฉันต้องการ Vector Clock (Lamport) สำหรับ causal ordering | 3 | ✅ |
| S2-07 | ในฐานะนักวิจัย ฉันต้องการ Link Mode สำหรับเชื่อมโหนดด้วย GUI | 3 | ✅ |

### Sprint 2 Retrospective
- **What went well:** Physics Engine ครบถ้วน, DTN animation สวยงาม
- **What to improve:** Bootstrap Paradox detection ยัง false positive บ้าง
- **Action items:** ปรับ time window จาก 3000ms → 5000ms (→ ทำแล้ว)

---

## Sprint 3 — Intelligence Layer
**Duration:** 2 สัปดาห์ | **Status:** ✅ Complete | **Points:** 35/30

### User Stories

| ID | Story | Points | Status |
|----|-------|--------|--------|
| S3-01 | ในฐานะนักวิจัย ฉันต้องการ DAFT State Machine ที่คำนวณ O₄, O₆, DARS แบบ real-time | 8 | ✅ |
| S3-02 | ในฐานะนักวิจัย ฉันต้องการ Domain Mapping สำหรับ 4 โดเมน (Bio, Phy, Neuro, Quantum) | 8 | ✅ |
| S3-03 | ในฐานะนักวิจัย ฉันต้องการ Quality Metrics Dashboard พร้อม pass/near/risk badges | 5 | ✅ |
| S3-04 | ในฐานะนักวิจัย ฉันต้องการ Causal Graph visualization บน timeline | 5 | ✅ |
| S3-05 | ในฐานะนักวิจัย ฉันต้องการ Roadmap Timeline Phase 0–5 | 3 | ✅ |
| S3-06 | ในฐานะผู้ใช้ ฉันต้องการ 4 UI themes ที่เปลี่ยนได้ | 3 | ✅ |
| S3-07 | ในฐานะนักวิจัย ฉันต้องการ DAFT state ปรากฏบน topbar | 3 | ✅ |

### Sprint 3 Retrospective
- **What went well:** Domain mapping เป็น differentiator ที่น่าประทับใจ
- **What to improve:** O₆ = 0 ทำให้ DARS = Infinity ต้องเพิ่ม floor
- **Action items:** เพิ่ม O₆ floor = 0.01 (→ ทำแล้ว), เพิ่ม updateHeader patch (→ Sprint 4)

---

## Sprint 4 — Ethics & HITL
**Duration:** 2 สัปดาห์ | **Status:** ✅ Complete | **Points:** 29/30

### User Stories

| ID | Story | Points | Status |
|----|-------|--------|--------|
| S4-01 | ในฐานะนักวิจัย ฉันต้องการ Ethics Tab ที่แสดง AI ethics principles และ DAFT → action mapping | 8 | ✅ |
| S4-02 | ในฐานะ compliance officer ฉันต้องการ HITL 3-level indicator ที่ trigger ตาม DAFT state | 8 | ✅ |
| S4-03 | ในฐานะ operator ฉันต้องการ Human Override button ที่ reset ระบบและ log เหตุการณ์ | 5 | ✅ |
| S4-04 | ในฐานะนักวิจัย ฉันต้องการ log panel ที่ resize ได้แบบ VS Code terminal | 5 | ✅ |
| S4-05 | ในฐานะนักวิจัย ฉันต้องการ DAFT state bar แสดงใน right panel ด้วย | 3 | ✅ |

### Sprint 4 Retrospective
- **What went well:** Ethics compliance ครอบคลุม EU AI Act และ Thai PDPA ได้ดี
- **What to improve:** updateHeader patch อาจเกิดปัญหาถ้ามีหลาย patch ซ้อนกัน
- **Action items:** เพิ่ม documentation เรื่อง patching pattern (→ special-edition.md)

---

## Sprint 5 — Advanced Features (Planned)

### Proposed User Stories

| ID | Story | Points | Priority |
|----|-------|--------|---------|
| S5-01 | Adaptive DARS thresholds ตาม topology | 13 | High |
| S5-02 | Hysteresis band ±0.02 per threshold | 5 | High |
| S5-03 | Dijkstra shortest causal path | 8 | Medium |
| S5-04 | Export causal history (JSON/CSV) | 5 | Medium |
| S5-05 | Unit tests สำหรับ Physics Engine | 8 | High |
| S5-06 | Mobile responsive layout | 5 | Low |

**Total estimated:** 44 points → อาจต้องแบ่งเป็น 2 sprints

---

## Definition of Done

Task ถือว่าเสร็จเมื่อ:
1. ✅ Feature ทำงานตาม acceptance criteria
2. ✅ ไม่มี console errors
3. ✅ ทดสอบกับ DEMO dataset (5 nodes)
4. ✅ Log แสดงผลถูกต้อง
5. ✅ ทำงานกับทุก 4 themes

---

*© UCCN Research Project — Sprint Plan v2.0*
