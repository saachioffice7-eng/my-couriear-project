# SAACHI Courier Management System - User Guide

## 🚀 Quick Start

Welcome to SAACHI Courier Management System! This guide will help you get started with the newly upgraded system.

---

## 📦 Adding a Parcel (New Smart Features!)

### Step 1: Open Parcel Form
1. Go to **Parcels** page
2. Click **"Add Parcel"** button

### Step 2: Enter Basic Information
- **Tracking ID**: Enter unique tracking number (e.g., PKG-2024-001)
- **Courier Company**: Select from dropdown
- **Customer Name**: Enter customer's full name
- **Phone**: Enter 10-digit phone number (only numbers allowed)

### Step 3: Smart Address Entry

#### Option A: Use PIN Code Auto-Fill (Recommended) ⚡
1. Enter **6-digit PIN code** (e.g., 400064)
2. Wait 1 second - the system will automatically fill:
   - ✅ City (e.g., Mumbai)
   - ✅ State (e.g., Maharashtra)
   - ✅ Country (e.g., India)
   - ✅ District
3. You'll see a success message: "Location auto-filled"
4. Edit any field if needed

#### Option B: Manual City Selection
1. Click on **City** dropdown
2. Start typing city name (e.g., "Mum")
3. Select from suggestions that appear
4. Enter State and Country manually

### Step 4: Enter Weight

**Important**: This is where the magic happens! ✨

1. Enter weight in grams (e.g., 1200)
2. **Wait 0.3 seconds** - the amount will auto-calculate!
3. The system finds the matching rate for:
   - Your selected courier company
   - Your selected city
   - The weight you entered

**Example**:
```
Courier: Maruti
City: Mumbai
Weight: 1200g

If your rates are:
- 0-1000g = ₹25
- 1000-2000g = ₹50

Amount will auto-fill: ₹50
```

### Step 5: Amount (Auto or Manual)

**Auto-Calculation (Default)**:
- Amount automatically calculates based on weight
- Updates as you type (with small delay to prevent lag)
- Uses rates configured in Rates page

**Manual Override**:
1. Check ☑️ "Use custom amount"
2. Amount field becomes editable
3. Enter your custom amount
4. Auto-calculation is disabled

### Step 6: Select Status
- Pending (default)
- Dispatched
- Delivered
- Cancelled

### Step 7: Save
Click **"Create Parcel"** button

---

## 💡 Pro Tips

### 1. PIN Code Auto-Fill
- ✅ **DO**: Enter PIN code first - it saves time!
- ✅ **DO**: Wait for the loading indicator to finish
- ❌ **DON'T**: Enter invalid PIN codes (must be 6 digits)

### 2. Weight Entry
- ✅ **DO**: Enter weight in grams (not kg)
- ✅ **DO**: Wait 0.3 seconds for auto-calculation
- ❌ **DON'T**: Type too fast - the system debounces for performance

### 3. City Search
- ✅ **DO**: Type at least 2 characters for suggestions
- ✅ **DO**: Use keyboard arrows to navigate suggestions
- ✅ **DO**: Press Enter to select

### 4. Custom Amounts
- ✅ **DO**: Use custom amount for special cases
- ✅ **DO**: Remember to check the override checkbox
- ❌ **DON'T**: Forget to configure rates first for auto-calculation

---

## ⚙️ Setting Up Rates (Required for Auto-Calculation)

Before auto-calculation works, you need to configure rates:

### Step 1: Go to Rates Page
Click **"Rates"** in the sidebar

### Step 2: Add Rate
1. Click **"Add Rate"**
2. Select **Courier Company**
3. Enter **City** name
4. Enter **Min Weight** (in grams, e.g., 0)
5. Enter **Max Weight** (in grams, e.g., 1000)
6. Enter **Price** (e.g., 25)
7. Click **"Create"**

### Step 3: Add More Rates
Create multiple rate ranges for each courier + city combination:

**Example for Maruti → Mumbai**:
```
Rate 1: 0-1000g = ₹25
Rate 2: 1000-2000g = ₹50
Rate 3: 2000-3000g = ₹75
```

### Step 4: Test
1. Go back to Parcels page
2. Add a parcel with:
   - Courier: Maruti
   - City: Mumbai
   - Weight: 1500g
3. Amount should auto-fill to ₹50 ✅

---

## 🔍 Searching Parcels

Use the search bar to find parcels by:
- Tracking ID
- Customer Name
- Phone Number

Just start typing - results filter instantly!

---

## 🖨️ Printing Labels

1. Find the parcel in the table
2. Click the **Printer icon** (🖨️)
3. Label preview appears
4. Click **"Print"** button
5. Label prints on A5 size paper

**Label includes**:
- SAACHI header
- Tracking ID
- Courier company
- Customer details
- Address with city, state, PIN
- Weight and amount
- Date

---

## ✏️ Editing Parcels

1. Click the **Pencil icon** (✏️) on any parcel
2. Form opens with existing data
3. Make changes
4. Click **"Update Parcel"**

**Note**: Auto-calculation still works when editing!

---

## 🗑️ Deleting Parcels

1. Click the **Trash icon** (🗑️)
2. Confirm deletion
3. Parcel is permanently removed

---

## 📊 Dashboard

The dashboard shows:
- Total Parcels
- Dispatched Parcels
- Pending Parcels
- Cancelled Parcels
- Daily/Weekly/Monthly/Yearly Expenses
- Charts and graphs

---

## 🚚 Managing Courier Companies

### Add Courier Company:
1. Go to **Courier Companies** page
2. Click **"Add Courier Company"**
3. Enter:
   - Company Name (e.g., Maruti, Delhivery)
   - Contact Person
   - Phone
   - Office Address
4. Click **"Create"**

### Edit/Delete:
- Use the action buttons in the table

---

## 💰 Managing Expenses

### Add Expense:
1. Go to **Expenses** page
2. Click **"Add Expense"**
3. Enter:
   - Title (e.g., "Fuel for delivery van")
   - Amount
   - Category (Fuel, Salary, Office, etc.)
   - Date
4. Click **"Create"**

Dashboard automatically updates with expense totals!

---

## 📈 Reports

Generate reports by:
1. Go to **Reports** page
2. Select filters:
   - Date range
   - Courier company
   - City
   - Status
3. Click **"Generate Report"**
4. Export as:
   - Excel
   - PDF
   - CSV

---

## 🎨 Theme

Toggle between light and dark modes using the theme button in the header.

**Default**: Dark mode with burgundy accent (#a0001e)

---

## ❓ Troubleshooting

### "Amount not auto-calculating"
- ✅ Check if rates are configured for that courier + city
- ✅ Make sure weight is entered
- ✅ Verify "Use custom amount" is NOT checked
- ✅ Wait 0.3 seconds after typing weight

### "City suggestions not appearing"
- ✅ Type at least 2 characters
- ✅ Check internet connection
- ✅ Try refreshing the page

### "PIN code not auto-filling"
- ✅ Enter exactly 6 digits
- ✅ Use valid Indian PIN codes only
- ✅ Wait for loading indicator
- ✅ Check internet connection

### "Page is slow/freezing"
- ✅ This should NOT happen anymore!
- ✅ If it does, refresh the page
- ✅ Clear browser cache
- ✅ Check internet speed

### "Phone/PIN validation errors"
- ✅ Phone: Must be exactly 10 digits
- ✅ PIN: Must be exactly 6 digits
- ✅ Only numbers allowed
- ✅ No spaces or special characters

---

## 🎯 Best Practices

1. **Always enter PIN code first** - saves time with auto-fill
2. **Configure rates before adding parcels** - enables auto-calculation
3. **Use search to find parcels quickly** - faster than scrolling
4. **Print labels immediately** - don't forget!
5. **Update status regularly** - keeps tracking accurate
6. **Export reports weekly** - for backup and analysis

---

## 🔐 Security

- All data is protected by authentication
- Only you can see your parcels
- Secure API calls through Supabase
- No data shared with third parties

---

## 📞 Support

For issues or questions:
1. Check this user guide
2. Review the PERFORMANCE_UPGRADE.md file
3. Check the QUICK_START.md file

---

## 🎉 Enjoy Your Upgraded System!

The SAACHI Courier Management System is now faster, smarter, and more efficient than ever!

**Key Features**:
- ⚡ Lightning-fast performance
- 🤖 Smart auto-fill from PIN code
- 💰 Automatic price calculation
- 🔍 Intelligent city search
- ✅ Real-time validation
- 🖨️ Professional label printing

Happy shipping! 📦🚚
