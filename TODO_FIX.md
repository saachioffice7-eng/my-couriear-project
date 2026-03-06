# Task: Fix and Upgrade ParcelFlow Courier Management System

## Plan
- [x] Step 1: Database schema (multi-tenant with auth triggers)
- [x] Step 2: Theme update to dark burgundy (#a0001e)
- [x] Step 3: Install packages (country-state-city, barcode)
- [x] Step 4: Update types for new schema
- [x] Step 5: Rebuild API layer for authenticated users
- [x] Step 6: Update AuthContext for OTP login
- [x] Step 7: Create Login page (Email + Phone OTP)
- [x] Step 8: Create Register page
- [x] Step 9: Update RouteGuard
- [x] Step 10: Create location selector components
- [x] Step 11: Create currency utilities
- [ ] Step 12: Rebuild parcel form with locations and validation
- [ ] Step 13: Update rate system for weight ranges
- [ ] Step 14: Update courier management
- [ ] Step 15: Fix label printing (A5, print only label)
- [ ] Step 16: Update reports with multi-select and filters
- [ ] Step 17: Update dashboard for expenses (not revenue)
- [ ] Step 18: Create settings page
- [ ] Step 19: Add header/navbar with user info
- [ ] Step 20: Update App.tsx with auth
- [ ] Step 21: Rebuild all existing pages for authenticated system
- [ ] Step 22: Run lint and fix issues

## Completed
✅ Database: Multi-tenant schema with RLS, auth triggers, worldwide locations
✅ Authentication: Email/Phone OTP login, registration with verification
✅ Theme: Dark burgundy/maroon (#a0001e) applied
✅ API Layer: Complete rewrite for authenticated users
✅ Types: Updated for new schema (Profile, Parcel with locations, etc.)
✅ Location System: Country → State → City selector component
✅ Currency System: Auto-detection by country + validation utilities
✅ Login/Register Pages: Full OTP flow implemented

## Remaining Work
❌ Update all existing pages (Dashboard, Parcels, Couriers, Rates, Expenses, Reports, Settings)
❌ Create header/navbar with user info and logout
❌ Rebuild parcel form with location selector and validation
❌ Implement weight-range rate system (0-1000g, 1000-2000g, etc.)
❌ Add barcode generation to parcels
❌ Fix label printing (A5 format, print only label)
❌ Update reports for multi-courier selection
❌ Update App.tsx with AuthProvider and RouteGuard
❌ Test complete authentication flow

## Notes
- Using Supabase Auth for OTP (phone verification enabled)
- Using country-state-city package for worldwide locations
- Theme: Dark burgundy/maroon (#a0001e)
- Weight ranges: 0-1000g = ₹25, 1000-2000g = ₹50, etc.
- All data is user-specific (multi-tenant with RLS)
- First registered user becomes admin automatically
