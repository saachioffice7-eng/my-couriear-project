# Auto Rate Calculation - Fixed! ✅

## Problem Solved

The auto rate calculation now works perfectly with the **1000g slab system**. When you enter weight, the amount updates automatically without page reload.

---

## How It Works

### Formula
```javascript
slab = Math.ceil(weight / 1000)
totalAmount = slab * baseRate
```

### Calculation Logic

1. **Divide weight by 1000**
2. **Round UP to next whole number** (using Math.ceil)
3. **Multiply by base rate**

---

## Examples

### Example 1: Base Rate = ₹50

| Weight | Calculation | Slab | Amount |
|--------|-------------|------|--------|
| 800g | CEIL(800 ÷ 1000) × 50 | 1 | ₹50 |
| 1000g | CEIL(1000 ÷ 1000) × 50 | 1 | ₹50 |
| 1001g | CEIL(1001 ÷ 1000) × 50 | 2 | ₹100 |
| 1200g | CEIL(1200 ÷ 1000) × 50 | 2 | ₹100 |
| 2000g | CEIL(2000 ÷ 1000) × 50 | 2 | ₹100 |
| 2001g | CEIL(2001 ÷ 1000) × 50 | 3 | ₹150 |
| 2200g | CEIL(2200 ÷ 1000) × 50 | 3 | ₹150 |
| 3500g | CEIL(3500 ÷ 1000) × 50 | 4 | ₹200 |

### Example 2: Base Rate = ₹25

| Weight | Calculation | Slab | Amount |
|--------|-------------|------|--------|
| 500g | CEIL(500 ÷ 1000) × 25 | 1 | ₹25 |
| 1200g | CEIL(1200 ÷ 1000) × 25 | 2 | ₹50 |
| 2500g | CEIL(2500 ÷ 1000) × 25 | 3 | ₹75 |
| 4800g | CEIL(4800 ÷ 1000) × 25 | 5 | ₹125 |

---

## How to Use

### Step 1: Set Up Base Rate

1. Go to **Rates** page
2. Click **"Add Rate"**
3. Select **Courier Company**
4. Enter **City** name
5. Enter **Base Rate** (e.g., 50)
6. Click **"Create"**

**Example**:
```
Courier: Maruti
City: Mumbai
Base Rate: ₹50
```

### Step 2: Add Parcel with Auto-Calculation

1. Go to **Parcels** page
2. Click **"Add Parcel"**
3. Select **Courier Company** (e.g., Maruti)
4. Enter **City** (e.g., Mumbai)
5. Enter **Weight** (e.g., 1200)
6. **Wait 0.3 seconds** → Amount auto-fills to ₹100! ✨

---

## Features

### ✅ Automatic Calculation
- Amount updates automatically when you enter weight
- Uses 300ms debounce to prevent lag
- No page reload needed

### ✅ Real-Time Updates
- Change weight → Amount updates
- Change courier → Amount recalculates
- Change city → Amount recalculates

### ✅ Manual Override
- Check "Use custom amount" checkbox
- Enter your own amount
- Auto-calculation disabled

### ✅ No Errors
- "Failed to Save" errors fixed
- Rates save successfully
- Calculation works instantly

---

## Technical Implementation

### Database Changes
- Added `base_rate` column to `courier_rates` table
- Stores base rate per 1000g slab
- Backward compatible with existing data

### Calculation Function
```typescript
export function calculatePriceFromRates(weight: number, rates: CourierRate[]): number {
  if (!weight || weight <= 0) return 0;
  if (!rates || rates.length === 0) return 0;
  
  const baseRate = rates[0]?.base_rate || rates[0]?.price || 0;
  if (baseRate <= 0) return 0;
  
  // Calculate slab: divide weight by 1000 and round up
  const slab = Math.ceil(weight / 1000);
  
  // Calculate total amount: slab * base rate
  const totalAmount = slab * baseRate;
  
  return Number(totalAmount);
}
```

### React Integration
- Uses `useDebounce` hook with 300ms delay
- Prevents page freezing during typing
- Optimized with `useCallback` for performance
- Updates form field automatically

---

## Testing

### Test Case 1: Basic Calculation
```
Setup:
- Courier: Maruti
- City: Mumbai
- Base Rate: ₹50

Test:
1. Enter weight: 800g
   Expected: ₹50 ✅
   
2. Enter weight: 1200g
   Expected: ₹100 ✅
   
3. Enter weight: 2200g
   Expected: ₹150 ✅
```

### Test Case 2: Different Base Rates
```
Setup:
- Courier: Delhivery
- City: Delhi
- Base Rate: ₹25

Test:
1. Enter weight: 500g
   Expected: ₹25 ✅
   
2. Enter weight: 1500g
   Expected: ₹50 ✅
   
3. Enter weight: 3000g
   Expected: ₹75 ✅
```

### Test Case 3: Manual Override
```
Test:
1. Enter weight: 1200g
   Auto-calculated: ₹100
   
2. Check "Use custom amount"
   
3. Enter amount: ₹150
   Expected: Amount stays ₹150 (not auto-calculated) ✅
```

---

## Troubleshooting

### Amount Not Calculating?

**Check:**
1. ✅ Base rate is configured for that courier + city
2. ✅ Weight is entered (greater than 0)
3. ✅ "Use custom amount" is NOT checked
4. ✅ Wait 0.3 seconds after typing

**Solution:**
- Go to Rates page
- Add rate for your courier + city combination
- Enter base rate (e.g., 50)
- Save and try again

### "Failed to Save" Error?

**Fixed!** ✅
- Database schema updated
- All fields properly configured
- Rates now save successfully

### Calculation Wrong?

**Verify:**
1. Check the base rate in Rates page
2. Use formula: CEIL(weight ÷ 1000) × base_rate
3. Example: 1200g with ₹50 base = CEIL(1.2) × 50 = 2 × 50 = ₹100

---

## Benefits

### 1. Simple System
- One base rate per courier + city
- No complex weight ranges
- Easy to understand and configure

### 2. Fast Performance
- Instant calculation
- No page lag
- Debounced for smooth typing

### 3. Accurate Pricing
- Consistent slab-based pricing
- No calculation errors
- Automatic updates

### 4. User-Friendly
- Visual examples in Rates page
- Real-time feedback
- Manual override option

---

## Rate Configuration Examples

### Courier: Maruti, City: Mumbai
```
Base Rate: ₹50

Pricing:
- 0-1000g = ₹50
- 1001-2000g = ₹100
- 2001-3000g = ₹150
- 3001-4000g = ₹200
- And so on...
```

### Courier: Delhivery, City: Delhi
```
Base Rate: ₹30

Pricing:
- 0-1000g = ₹30
- 1001-2000g = ₹60
- 2001-3000g = ₹90
- 3001-4000g = ₹120
- And so on...
```

### Courier: Blue Dart, City: Bangalore
```
Base Rate: ₹75

Pricing:
- 0-1000g = ₹75
- 1001-2000g = ₹150
- 2001-3000g = ₹225
- 3001-4000g = ₹300
- And so on...
```

---

## Summary

✅ **Auto-calculation working**
✅ **1000g slab system implemented**
✅ **No page freezing**
✅ **Real-time updates**
✅ **Manual override available**
✅ **"Failed to Save" errors fixed**
✅ **Simple and accurate**

The courier rate calculator now works exactly as required! Enter weight, get instant amount calculation based on the 1000g slab formula.

---

**SAACHI Courier Management System**
Auto Rate Calculation - Version 2.0 ✅
