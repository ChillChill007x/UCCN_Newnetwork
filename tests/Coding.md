# Coding Standards & Test Cases — UCCN Simulator
**Code Quality Guidelines & Test Specifications**
**Version:** 1.0 | **Date:** 2026-03-19

---

## 1. Coding Standards / มาตรฐานการเขียนโค้ด

### 1.1 JavaScript Style

```javascript
// ✅ GOOD — descriptive names, clear intent
function computeDAFT() {
  const total = txCnt + rxCnt;
  daftO4 = total > 0 ? Math.abs(txCnt - rxCnt) / total : 0;
}

// ❌ BAD — cryptic names
function cd() {
  const t = a + b;
  o4 = t > 0 ? Math.abs(a - b) / t : 0;
}
```

### 1.2 Naming Conventions

| Type | Convention | Example |
|------|-----------|---------|
| Functions | camelCase | `computeDAFT()`, `renderNodeList()` |
| Constants | UPPER_SNAKE | `MODES`, `ETHICS_MAP`, `LY` |
| DOM IDs | camelCase | `pc-d`, `hDaft`, `logBox` |
| CSS classes | kebab-case | `daft-bar`, `nc-nm`, `btn-p` |
| State variables | camelCase | `daftO4`, `darsScore`, `simRunning` |

### 1.3 Function Size

- ฟังก์ชันควรทำหน้าที่เดียว (Single Responsibility)
- ถ้ายาวกว่า 40 บรรทัด → พิจารณาแยกออก
- ใช้ early return เพื่อลด nesting

```javascript
// ✅ GOOD — early return
function transmit() {
  if (!srcId || !dstId) { log('warn', 'TX', 'Select source and destination'); return; }
  if (srcId === dstId) { log('warn', 'TX', 'Source and destination must differ'); return; }
  if (!activeModes.size) { log('warn', 'TX', 'Select at least one signal mode'); return; }
  // ... main logic
}
```

---

## 2. Test Cases / กรณีทดสอบ

### 2.1 Physics Engine Tests

#### TC-PHY-001: Shannon Capacity — Single Mode
```
Input:
  mode = photon (SNR=30dB, BW=1THz)
  
Expected:
  C = 10^12 × log2(1 + 10^3)
  C ≈ 9.97 × 10^12 bps ≈ 9.97 Tbps
  
Result: ✅ PASS (simulator shows ~9.97T/s)
```

#### TC-PHY-002: Shannon Capacity — Multi-Modal
```
Input:
  modes = {photon, neutrino, graviton, dtn}
  
Expected:
  C_photon  = 1e12 × log2(1001) ≈ 9.97 Tbps
  C_dtn     = 1e9  × log2(317)  ≈ 316 Gbps
  C_neutrino= 1e8  × log2(11)   ≈ 346 Mbps
  C_graviton= 1e6  × log2(4.16) ≈ 2.06 Mbps
  C_total   ≈ 10.29 Tbps
  
Result: ✅ PASS
```

#### TC-PHY-003: Lorentz γ Factor
```
Input:
  fastest mode = photon (v = 1.0c → clamped to 0.9999999)
  
Expected:
  γ = 1 / √(1 - 0.9999999²)
  γ = 1 / √(0.0000002)
  γ ≈ 2236
  
Result: ✅ PASS (simulator shows γ = 2236.xxx)
```

#### TC-PHY-004: Distance Calculation
```
Input:
  src.tOffset = 0 (Sol-System)
  dst.tOffset = 4.2 (Proxima-Cen)
  
Expected:
  Δd = |4.2 - 0| = 4.2 ly
  Min Latency = 4.200 yr ≈ "4.200 yr"
  
Result: ✅ PASS
```

---

### 2.2 Paradox Prevention Tests

#### TC-PAR-001: Grandfather Paradox
```
Input:
  src.tOffset = 10.0 ly
  dst.tOffset = -5.0 ly  (Δ = 15 ly > threshold 10)
  
Expected:
  checkParadox returns {ok: false, type: 'GRANDFATHER'}
  TX is BLOCKED
  parCnt++
  
Result: ✅ PASS
```

#### TC-PAR-002: Grandfather Paradox — Below Threshold
```
Input:
  src.tOffset = 10.0 ly
  dst.tOffset = 2.0 ly  (Δ = 8 ly < threshold 10)
  
Expected:
  checkParadox returns {ok: true}
  TX proceeds normally
  
Result: ✅ PASS
```

#### TC-PAR-003: Causal Loop
```
Input:
  node A: chain = [B.id]
  node B: chain = [A.id]
  
Expected:
  checkParadox(A, B) returns {ok: false, type: 'CAUSAL_LOOP'}
  
Result: ✅ PASS
```

#### TC-PAR-004: Bootstrap Paradox
```
Input:
  causalHist has 4 entries: {src: B, dst: A} within last 5000ms
  
Expected:
  checkParadox(A, B) returns {ok: false, type: 'BOOTSTRAP'}
  
Result: ✅ PASS
```

---

### 2.3 DAFT Engine Tests

#### TC-DAFT-001: PURE State
```
Input:
  txCnt = 10, rxCnt = 10
  links = [{tOffset_src: 0, tOffset_dst: 5}]
  
Calculation:
  O4 = |10-10| / 20 = 0
  O6 = 5.0
  DARS = 0 / 5.0 = 0.00
  
Expected: State = PURE
Result: ✅ PASS
```

#### TC-DAFT-002: BOUNDARY State
```
Input:
  txCnt = 10, rxCnt = 0
  links = [{tOffset_src: 0, tOffset_dst: 1}]
  
Calculation:
  O4 = |10-0| / 10 = 1.0
  O6 = 1.0
  DARS = 1.0 / 1.0 = 1.0 ≥ 0.60
  
Expected: State = BOUNDARY
Result: ✅ PASS
```

#### TC-DAFT-003: O₆ Floor (no links)
```
Input:
  links = []
  
Calculation:
  O6 = 1.0 (floor when no links)
  
Expected: No division by zero, DARS = O4
Result: ✅ PASS
```

---

### 2.4 HITL Ethics Tests

#### TC-HITL-001: Level 2 Trigger
```
Input:
  DAFT State = DESTRUCTIVE (DARS = 0.35)
  
Expected:
  log contains "HITL Level 2 triggered (EU AI Act Art.13)"
  hitlLevel = 2
  
Result: ✅ PASS
```

#### TC-HITL-002: Level 3 Override
```
Input:
  Click "TRIGGER OVERRIDE" button
  
Expected:
  overrideCount++
  daftO4 = 0, daftO6 = 1 (reset)
  State transitions to PURE
  Log: "HUMAN OVERRIDE TRIGGERED (Level 3)"
  
Result: ✅ PASS
```

---

## 3. Known Test Gaps

| Test Area | Gap | Priority |
|-----------|-----|---------|
| Vector Clock monotonicity | ยังไม่มี automated test | High |
| CRC32 collision probability | ยังไม่ได้ทดสอบ at scale | Medium |
| Multi-user concurrent access | ไม่รองรับ (single-user design) | Low |
| Memory leak (long simulation) | ยังไม่ได้ทดสอบ > 1 hour | Medium |

---

## 4. Test Environment

- **Browser:** Chrome 120+ (recommended), Firefox 115+, Safari 17+
- **Screen resolution:** minimum 1280×800
- **Test dataset:** DEMO (5 nodes: Sol, Proxima, Sirius, Tau Ceti, Vega)

---

*© UCCN Research Project — Coding Standards & Tests v1.0*
