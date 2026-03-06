# Quick Reference: Auto Rate Calculation

## ✅ Fixed and Working!

The auto rate calculation now works perfectly with the **1000g slab system**.

---

## Formula

```
slab = CEIL(weight ÷ 1000)
amount = slab × base_rate
```

---

## Quick Examples

### Base Rate = ₹50

| Weight | Amount |
|--------|--------|
| 800g | ₹50 |
| 1200g | ₹100 |
| 2200g | ₹150 |
| 3500g | ₹200 |

---

## How to Set Up

### 1. Add Base Rate
```
Rates Page → Add Rate
- Courier: Maruti
- City: Mumbai
- Base Rate: ₹50
- Save
```

### 2. Add Parcel
```
Parcels Page → Add Parcel
- Select Courier: Maruti
- Enter City: Mumbai
- Enter Weight: 1200
- Amount auto-fills: ₹100 ✨
```

---

## Features

✅ **Instant Calculation** - Updates as you type (0.3s delay)
✅ **No Page Reload** - Real-time updates
✅ **Manual Override** - Check "Use custom amount" to enter manually
✅ **No Errors** - "Failed to Save" fixed
✅ **Simple System** - One base rate per courier + city

---

## Calculation Examples

### Example 1: 1200g with ₹50 base rate
```
Step 1: 1200 ÷ 1000 = 1.2
Step 2: CEIL(1.2) = 2 (round up)
Step 3: 2 × 50 = ₹100
```

### Example 2: 2500g with ₹25 base rate
```
Step 1: 2500 ÷ 1000 = 2.5
Step 2: CEIL(2.5) = 3 (round up)
Step 3: 3 × 25 = ₹75
```

### Example 3: 800g with ₹50 base rate
```
Step 1: 800 ÷ 1000 = 0.8
Step 2: CEIL(0.8) = 1 (round up)
Step 3: 1 × 50 = ₹50
```

---

## Troubleshooting

### Amount Not Calculating?

**Check:**
1. Base rate configured for courier + city?
2. Weight entered (> 0)?
3. "Use custom amount" unchecked?
4. Waited 0.3 seconds?

**Fix:**
- Go to Rates page
- Add rate for your courier + city
- Enter base rate
- Try again

---

## Rate Examples

### Maruti → Mumbai
```
Base Rate: ₹50
0-1000g = ₹50
1001-2000g = ₹100
2001-3000g = ₹150
```

### Delhivery → Delhi
```
Base Rate: ₹30
0-1000g = ₹30
1001-2000g = ₹60
2001-3000g = ₹90
```

---

## Summary

✅ Auto-calculation working
✅ 1000g slab system
✅ Real-time updates
✅ No errors
✅ Simple and accurate

**Ready to use!** 🚀
