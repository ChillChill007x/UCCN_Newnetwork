# Role and Responsibility — UCCN Project
**Team Structure & Accountability Matrix**
**Version:** 1.0 | **Date:** 2026-03-19

---

## โครงสร้างทีม / Team Structure

UCCN เป็นโปรเจกต์วิจัย Phase 0 ที่ดำเนินการในรูปแบบ agile research team โดยแต่ละบทบาทมีความรับผิดชอบที่ชัดเจน

---

## RACI Matrix

**RACI Key:**
- **R** = Responsible (ผู้ลงมือทำ)
- **A** = Accountable (ผู้รับผิดชอบผลลัพธ์)
- **C** = Consulted (ผู้ให้คำปรึกษา)
- **I** = Informed (ผู้รับทราบ)

| Activity | Principal Researcher | Physics Advisor | Ethics Officer | Developer |
|----------|---------------------|----------------|----------------|-----------|
| DAFT Theory | A/R | C | I | I |
| Physics Engine | C | A/R | I | R |
| Simulator Dev | A | I | I | R |
| Ethics/HITL Design | C | I | A/R | R |
| Domain Mapping | R | C | I | I |
| Test Planning | A | I | C | R |
| Documentation | A/R | C | C | I |

---

## Role Descriptions / คำอธิบายบทบาท

### 1. Principal Researcher (นักวิจัยหลัก)

**ความรับผิดชอบ:**
- กำหนดทิศทางและ scope ของงานวิจัย
- พัฒนา DAFT theory และ formal specification
- เขียน theoretical documentation
- ตัดสินใจ design trade-offs

**KPIs:**
- เผยแพร่ formal specification ทุก Sprint
- ทบทวน theoretical correctness ของ feature ใหม่ทุกชิ้น

### 2. Physics Advisor (ที่ปรึกษาด้านฟิสิกส์)

**ความรับผิดชอบ:**
- ตรวจสอบความถูกต้องของสูตรฟิสิกส์ (Shannon, Lorentz, etc.)
- ให้คำแนะนำเรื่อง signal mode properties
- ทบทวน relativistic calculations
- ระบุ physical limitations ของแต่ละ mode

**KPIs:**
- Review Physics Engine ทุก Sprint
- ระบุ limitations ใน documentation อย่างชัดเจน

### 3. Ethics Officer (เจ้าหน้าที่จริยธรรม)

**ความรับผิดชอบ:**
- ออกแบบ HITL architecture
- ดูแล EU AI Act compliance
- ดูแล Thai PDPA §26 compliance
- ทบทวน DAFT → Ethics trigger mapping

**KPIs:**
- Compliance checklist ครบตาม EU AI Act Art.9, 13, 14
- Override log ครบทุก BOUNDARY event

### 4. Developer (นักพัฒนา)

**ความรับผิดชอบ:**
- Implement features ตาม sprint plan
- Code review
- Performance optimization
- Canvas rendering และ animation

**KPIs:**
- Feature delivery ตาม sprint commitment
- Zero console errors ใน production build

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
Developer issue → Principal Researcher → Physics/Ethics Advisor
                                        ↓
                               กรณี BOUNDARY state จริง
                               → Ethics Officer review
                               → Human Override required
```

---

*© UCCN Research Project — Role and Responsibility v1.0*
