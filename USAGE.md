# SAACHI Courier Management System

A complete professional courier business management web application built with React, TypeScript, Supabase, and shadcn/ui.

## Features

### 📦 Parcel Management
- Add, edit, and delete parcels
- Automatic price calculation based on weight and destination
- Phone number validation (10 digits)
- Pin code validation (6 digits)
- Parcel status tracking (Pending, Dispatched, Delivered, Cancelled)
- Search parcels by tracking ID, customer name, or phone number
- A5 format label printing

### 🚚 Courier Company Management
- Add, edit, and delete courier companies
- Store contact person, phone, and office address
- Automatically available in parcel entry dropdown

### 🏙️ City Management
- Add, edit, and delete cities
- Automatically available in parcel entry dropdown

### 💰 Rate Management
- Configure pricing rules per courier company and city
- Set base weight and base price
- Automatic price calculation: `price = ceil(weight / base_weight) * base_price`
- Example: 800g = ₹25, 1200g = ₹50, 2100g = ₹75 (for 1000g base @ ₹25)

### 💸 Expense Management
- Track business expenses
- Categorize expenses (Fuel, Salary, Office, Courier Charges, Other)
- Add and manage custom expense categories
- Date-based expense tracking

### 📊 Dashboard
- Real-time KPI cards:
  - Total Parcels
  - Dispatched Parcels
  - Pending Parcels
  - Cancelled Parcels
  - Daily/Weekly/Monthly/Yearly Expenses
- Visual charts:
  - Parcel status distribution (Pie chart)
  - Expense overview (Bar chart)

### 📈 Reports & Export
- Filter parcels by:
  - Date range
  - Courier company
  - City
  - Status
- Export options:
  - Excel (.xlsx)
  - PDF
  - Print
- Summary statistics:
  - Total parcels and amount
  - Courier company-wise breakdown
  - Area-wise breakdown

### 🔍 Customer Tracking
- Public tracking page
- Search by tracking ID
- View parcel status and details
- No authentication required

### ⚙️ Settings
- Customize label name for printing
- Fully editable configurations

## Technology Stack

- **Frontend**: React 18 + TypeScript
- **UI Framework**: shadcn/ui + Tailwind CSS
- **Backend**: Supabase (PostgreSQL)
- **Charts**: Recharts
- **Export**: xlsx, jsPDF
- **Routing**: React Router v7
- **Forms**: React Hook Form + Zod validation
- **Build Tool**: Vite

## Getting Started

### Prerequisites
- Node.js 18+ installed
- pnpm package manager

### Installation

1. Clone the repository
2. Install dependencies:
   ```bash
   pnpm install
   ```

3. The application is already configured with Supabase. The database schema includes:
   - `courier_companies` - Courier service providers
   - `cities` - Delivery locations
   - `courier_rates` - Pricing rules
   - `parcels` - Parcel records
   - `expenses` - Business expenses
   - `expense_categories` - Expense categories
   - `settings` - Application settings

### Usage

The application is ready to use with the following features:

#### Initial Setup
1. **Add Courier Companies**: Go to "Courier Companies" and add your courier service providers
2. **Add Cities**: Go to "Cities" and add delivery locations
3. **Configure Rates**: Go to "Rates" and set pricing rules for each courier-city combination

#### Daily Operations
1. **Create Parcels**: 
   - Go to "Parcels" → "Add Parcel"
   - Enter tracking ID, select courier and city
   - Fill customer details (phone must be 10 digits, pin code 6 digits)
   - Enter weight in grams
   - Amount will be auto-calculated based on rates
   - Select status

2. **Print Labels**:
   - Click the printer icon on any parcel
   - Review the A5 label preview
   - Click "Print Label" to print

3. **Track Expenses**:
   - Go to "Expenses" → "Add Expense"
   - Enter title, amount, category, and date
   - Manage categories via "Manage Categories" button

4. **View Reports**:
   - Go to "Reports"
   - Apply filters (date range, courier, city, status)
   - View summary statistics
   - Export to Excel or PDF

5. **Customer Tracking**:
   - Share the "Track Parcel" page with customers
   - Customers can search by tracking ID
   - View real-time parcel status

## Pricing Formula

The system uses a weight-based pricing calculation:

```
price = ceil(weight / base_weight) * base_price
```

**Example**:
- Base Weight: 1000 grams
- Base Price: ₹25

| Weight | Calculation | Price |
|--------|-------------|-------|
| 800g   | ceil(800/1000) × 25 | ₹25 |
| 1200g  | ceil(1200/1000) × 25 | ₹50 |
| 2100g  | ceil(2100/1000) × 25 | ₹75 |

## Validation Rules

- **Phone Number**: Exactly 10 digits
- **Pin Code**: Exactly 6 digits
- **Weight**: Must be greater than 0
- **Amount**: Auto-calculated, can be manually adjusted

## Dark Mode

The application supports dark mode by default. Toggle between light and dark themes using the theme switcher in the header.

## Database Schema

### Tables
- `courier_companies` - Courier service providers
- `cities` - Delivery locations
- `courier_rates` - Pricing configuration (unique per courier-city pair)
- `parcels` - Parcel records with tracking
- `expenses` - Business expense tracking
- `expense_categories` - Expense categorization
- `settings` - Application configuration

### Security
- Row Level Security (RLS) enabled on all tables
- Public access policies (no authentication required)
- Can be extended with authentication if needed

## Support

For issues or questions, please refer to the application's built-in help or contact your system administrator.

## License

© 2026 SAACHI Courier Management System
