# Visual Guide: 1000g Slab Rate Calculation System

## How the Slab System Works

```
┌─────────────────────────────────────────────────────────────┐
│                    1000g SLAB SYSTEM                        │
│                                                             │
│  Every 1000 grams = 1 slab                                 │
│  Total Amount = Number of Slabs × Base Rate                │
└─────────────────────────────────────────────────────────────┘
```

---

## Visual Representation

### Base Rate = ₹50

```
Weight Range          Slab    Calculation           Amount
─────────────────────────────────────────────────────────────
0g - 1000g            1       1 × ₹50              ₹50
│                     │
├─ 500g  ────────────►│       CEIL(500/1000) = 1   ₹50
├─ 800g  ────────────►│       CEIL(800/1000) = 1   ₹50
└─ 1000g ────────────►│       CEIL(1000/1000) = 1  ₹50

1001g - 2000g         2       2 × ₹50              ₹100
│                     │
├─ 1001g ────────────►│       CEIL(1001/1000) = 2  ₹100
├─ 1200g ────────────►│       CEIL(1200/1000) = 2  ₹100
├─ 1500g ────────────►│       CEIL(1500/1000) = 2  ₹100
└─ 2000g ────────────►│       CEIL(2000/1000) = 2  ₹100

2001g - 3000g         3       3 × ₹50              ₹150
│                     │
├─ 2001g ────────────►│       CEIL(2001/1000) = 3  ₹150
├─ 2200g ────────────►│       CEIL(2200/1000) = 3  ₹150
├─ 2500g ────────────►│       CEIL(2500/1000) = 3  ₹150
└─ 3000g ────────────►│       CEIL(3000/1000) = 3  ₹150

3001g - 4000g         4       4 × ₹50              ₹200
│                     │
├─ 3001g ────────────►│       CEIL(3001/1000) = 4  ₹200
├─ 3500g ────────────►│       CEIL(3500/1000) = 4  ₹200
└─ 4000g ────────────►│       CEIL(4000/1000) = 4  ₹200
```

---

## Step-by-Step Calculation

### Example: 1200g with Base Rate ₹50

```
┌──────────────────────────────────────────────────────────┐
│ Step 1: Divide by 1000                                   │
│                                                          │
│   1200 ÷ 1000 = 1.2                                     │
└──────────────────────────────────────────────────────────┘
                    ↓
┌──────────────────────────────────────────────────────────┐
│ Step 2: Round UP (CEIL function)                        │
│                                                          │
│   CEIL(1.2) = 2                                         │
│                                                          │
│   Why? Because 1200g exceeds 1000g,                     │
│   so it needs 2 slabs                                   │
└──────────────────────────────────────────────────────────┘
                    ↓
┌──────────────────────────────────────────────────────────┐
│ Step 3: Multiply by Base Rate                           │
│                                                          │
│   2 × ₹50 = ₹100                                        │
└──────────────────────────────────────────────────────────┘
                    ↓
              ┌─────────┐
              │ ₹100    │
              └─────────┘
```

---

## Comparison: Different Base Rates

### Same Weight (1200g), Different Base Rates

```
Base Rate ₹25:
1200g → CEIL(1200/1000) = 2 → 2 × ₹25 = ₹50

Base Rate ₹50:
1200g → CEIL(1200/1000) = 2 → 2 × ₹50 = ₹100

Base Rate ₹75:
1200g → CEIL(1200/1000) = 2 → 2 × ₹75 = ₹150
```

---

## Real-World Scenario

### Courier: Maruti, City: Mumbai, Base Rate: ₹50

```
Customer 1: Sends 800g package
┌─────────────────────────────────────┐
│ Weight: 800g                        │
│ Calculation: CEIL(800/1000) × 50   │
│ Slab: 1                             │
│ Amount: ₹50                         │
└─────────────────────────────────────┘

Customer 2: Sends 1200g package
┌─────────────────────────────────────┐
│ Weight: 1200g                       │
│ Calculation: CEIL(1200/1000) × 50  │
│ Slab: 2                             │
│ Amount: ₹100                        │
└─────────────────────────────────────┘

Customer 3: Sends 2500g package
┌─────────────────────────────────────┐
│ Weight: 2500g                       │
│ Calculation: CEIL(2500/1000) × 50  │
│ Slab: 3                             │
│ Amount: ₹150                        │
└─────────────────────────────────────┘
```

---

## Why CEIL (Round Up)?

```
Example: 1001g package

If we use FLOOR (round down):
  1001 ÷ 1000 = 1.001
  FLOOR(1.001) = 1
  1 × ₹50 = ₹50
  ❌ Not fair! Package is over 1000g but charged for 1 slab

If we use CEIL (round up):
  1001 ÷ 1000 = 1.001
  CEIL(1.001) = 2
  2 × ₹50 = ₹100
  ✅ Correct! Package exceeds 1000g, so charged for 2 slabs
```

---

## User Interface Flow

```
┌─────────────────────────────────────────────────────────┐
│                    RATES PAGE                           │
│                                                         │
│  1. Select Courier: [Maruti ▼]                        │
│  2. Enter City: [Mumbai]                               │
│  3. Enter Base Rate: [50]                              │
│  4. Click [Save]                                       │
│                                                         │
│  ✅ Rate saved: Maruti → Mumbai → ₹50/1000g           │
└─────────────────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────────────────┐
│                   PARCELS PAGE                          │
│                                                         │
│  1. Select Courier: [Maruti ▼]                        │
│  2. Enter City: [Mumbai]                               │
│  3. Enter Weight: [1200] ← User types here            │
│                                                         │
│     ⏱️ Wait 0.3 seconds (debounce)                     │
│                                                         │
│  4. Amount: [100] ← Auto-calculated! ✨               │
│                                                         │
│  Calculation shown:                                    │
│  CEIL(1200 ÷ 1000) × 50 = 2 × 50 = ₹100              │
└─────────────────────────────────────────────────────────┘
```

---

## Manual Override Option

```
┌─────────────────────────────────────────────────────────┐
│  Auto-Calculation (Default)                            │
│                                                         │
│  Weight: [1200]                                        │
│  Amount: [100] ← Auto-calculated                       │
│  ☐ Use custom amount                                   │
└─────────────────────────────────────────────────────────┘
                    ↓
                [Check box]
                    ↓
┌─────────────────────────────────────────────────────────┐
│  Manual Override (Custom)                              │
│                                                         │
│  Weight: [1200]                                        │
│  Amount: [150] ← User can edit                         │
│  ☑ Use custom amount                                   │
│                                                         │
│  Auto-calculation disabled                             │
└─────────────────────────────────────────────────────────┘
```

---

## Performance Optimization

```
User Types Weight:
  [1] → Wait...
  [12] → Wait...
  [120] → Wait...
  [1200] → Wait 0.3 seconds...
           ↓
        Calculate!
        Amount = ₹100

Why 0.3 seconds?
✅ Prevents lag during typing
✅ Calculates only once after user stops
✅ Smooth, responsive experience
```

---

## Summary Diagram

```
┌──────────────────────────────────────────────────────────┐
│           1000g SLAB RATE CALCULATOR                     │
│                                                          │
│  Input:                                                  │
│    • Courier Company                                     │
│    • City                                                │
│    • Weight (grams)                                      │
│                                                          │
│  Process:                                                │
│    1. Find base rate for courier + city                 │
│    2. Calculate: CEIL(weight ÷ 1000)                    │
│    3. Multiply: slab × base_rate                        │
│                                                          │
│  Output:                                                 │
│    • Total Amount (₹)                                    │
│    • Auto-updates in real-time                          │
│                                                          │
│  Features:                                               │
│    ✅ Instant calculation                                │
│    ✅ No page reload                                     │
│    ✅ Manual override option                             │
│    ✅ Debounced for performance                          │
└──────────────────────────────────────────────────────────┘
```

---

**SAACHI Courier Management System**
Visual Guide - 1000g Slab Rate Calculation
