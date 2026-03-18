# Role and Responsibility — UCCN Project
**Team Structure & Accountability Matrix**
**Version:** 1.0 | **Date:** 2026-03-19

---

## การควบคุมเอกสาร / Document Control

| เวอร์ชัน | วันที่ | ผู้จัดทำ | บทบาท | การเปลี่ยนแปลง |
|---------|-------|---------|-------|--------------|
| v1.0 | 22/2/2026 | นายวงศธร ธน.ยอด | สถาปนิกระบบ | จัดทำสถาปัตยกรรมเบื้องต้น |

---

## บทบาททีมพัฒนา / Team Roles

| บทบาท | ชื่อ | ความรับผิดชอบหลัก |
|-------|-----|-----------------|
| สถาปนิกระบบ (Architect) | นายวงศธร ธน.ยอด | ออกแบบระบบโดยรวม, กำหนดเลเยอร์, สร้างข้อตกลงระหว่างส่วนประกอบ |
| วิศวกรเครือข่าย (Engineer) | นายพัชรพล กองแก้ว | พัฒนาโปรโตคอล, พัฒนาจำลองสถานการณ์, เขียนโค้ดหลัก |
| ผู้เชี่ยวชาญเฉพาะด้าน (Specialist) | นายกฤษฎา นามมนต์เทียน | วิจัยความสัมพันธ์เชิงเหตุผล, กฎ Paradox, องค์ความรู้เฉพาะทาง |
| ผู้ดูแลระบบและเครื่องมือ (DevOps) | นายศภกิตติ์ ฟันเฟือย | จัดการสภาพแวดล้อม, CI/CD, บูรณาการ, ดูแลเอกสาร |
| ผู้ทดสอบ/ประกันคุณภาพ (Tester/QA) | นายคมชาญ น้อยเนียม | วางแผนทดสอบ, ออกแบบกรณีทดสอบ, ตรวจสอบคุณภาพ |

---

## RACI Matrix

**RACI Key:**
- **R** = Responsible (ผู้ลงมือทำ)
- **A** = Accountable (ผู้รับผิดชอบผลลัพธ์)
- **C** = Consulted (ผู้ให้คำปรึกษา)
- **I** = Informed (ผู้รับทราบ)

| Activity | Architect (วงศธร) | Engineer (พัชรพล) | Specialist (กฤษฎา) | DevOps (ศภกิตติ์) | Tester/QA (คมชาญ) |
|----------|:-----------------:|:-----------------:|:------------------:|:-----------------:|:-----------------:|
| DAFT Theory | A/R | I | C | I | I |
| Physics Engine | C | A/R | C | I | I |
| Simulator Development | A | R | I | C | I |
| Paradox Rules & Logic | C | C | A/R | I | I |
| Ethics / HITL Design | A | C | C | I | I |
| Domain Mapping | A/R | I | C | I | I |
| CI/CD & Environment | I | I | I | A/R | I |
| Test Planning | C | I | I | I | A/R |
| Documentation | A | I | C | R | C |
| Code Review | A | R | C | R | C |

---

## Role Descriptions / คำอธิบายบทบาท

### 1. สถาปนิกระบบ — นายวงศธร ธน.ยอด

**ความรับผิดชอบ:**
- ออกแบบสถาปัตยกรรมโดยรวมของ UCCN Simulator
- กำหนดเลเยอร์และ component boundaries
- สร้างข้อตกลง (interface contracts) ระหว่างส่วนประกอบ
- ตัดสินใจ design trade-offs หลักทุกอย่าง
- จัดทำ Architecture Specification และ Formal Specification

**KPIs:**
- Architecture Spec อัปเดตทุก Sprint
- Component interfaces ไม่มี breaking change โดยไม่แจ้งล่วงหน้า

---

### 2. วิศวกรเครือข่าย — นายพัชรพล กองแก้ว

**ความรับผิดชอบ:**
- พัฒนา network protocol layer (Signal Modes, Packet Transmission)
- พัฒนา Physics Engine (Shannon Capacity, Lorentz γ, DTN Bundle)
- เขียนโค้ดหลักของ simulator
- Implement multi-modal simultaneous transmission

**KPIs:**
- Physics calculations ถูกต้องตาม test cases
- Code delivery ตาม sprint commitment

---

### 3. ผู้เชี่ยวชาญเฉพาะด้าน — นายกฤษฎา นามมนต์เทียน

**ความรับผิดชอบ:**
- วิจัยและกำหนดกฎ Causal Paradox (Grandfather, Causal Loop, Bootstrap)
- พัฒนา DAFT Theory (O₄, O₆, DARS)
- องค์ความรู้ด้าน Special Relativity และ Information Theory
- Domain Interface Mapping (Bio, Physics, Neuro, Quantum)

**KPIs:**
- Paradox rules ครอบคลุมทุก known paradox type
- DAFT formal specification ถูกต้องทางคณิตศาสตร์

---

### 4. ผู้ดูแลระบบและเครื่องมือ — นายศภกิตติ์ ฟันเฟือย

**ความรับผิดชอบ:**
- จัดการสภาพแวดล้อม development และ deployment
- ดูแล CI/CD pipeline
- บูรณาการ components จาก team members
- ดูแลและจัดระเบียบเอกสารโปรเจกต์
- GitHub repository management

**KPIs:**
- Build pipeline ไม่มี downtime
- เอกสารครบถ้วนและ up-to-date

---

### 5. ผู้ทดสอบ/ประกันคุณภาพ — นายคมชาญ น้อยเนียม

**ความรับผิดชอบ:**
- วางแผนและกำหนด test strategy ในแต่ละ Sprint
- ออกแบบ test cases (Physics, Paradox, DAFT, HITL)
- ทดสอบ regression หลัง integration
- รายงาน defects และ verify fixes
- จัดทำ test results report

**KPIs:**
- Test coverage ≥ 95% ต่อ Sprint
- Regression test pass rate 100%

---

## Communication Protocol / โปรโตคอลการสื่อสาร

### Daily Standup (15 นาที)
- What did I do yesterday?
- What will I do today?
- Any blockers?

### Sprint Review (1 ชั่วโมง)
- Demo ทุก feature ที่เสร็จ
- Acceptance criteria verification
- Stakeholder feedback

### Sprint Retrospective (45 นาที)
- What went well?
- What to improve?
- Action items สำหรับ sprint ถัดไป

---

## Escalation Path / เส้นทางการ Escalate

```
Developer/Tester issue
        ↓
  Engineer (พัชรพล)
        ↓
  Architect (วงศธร) — design decisions
  Specialist (กฤษฎา) — causal/physics issues
  DevOps (ศภกิตติ์) — environment issues
        ↓
  กรณี BOUNDARY state / Ethics issue
  → Specialist + Architect review
  → Human Override required (HITL Level 3)
```

---

*© UCCN Research Project — Role and Responsibility v1.0*
*จัดทำโดย นายวงศธร ธน.ยอด | 22/2/2026*
