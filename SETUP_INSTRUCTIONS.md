# ParcelFlow - Setup Instructions

## 🚀 Getting Started

### Step 1: Register Your Account

1. Open the application
2. You will be automatically redirected to the **Login** page
3. Click on **"Register"** link at the bottom
4. Fill in the registration form:
   - **Full Name**: Your full name
   - **Business Name**: Your courier business name
   - **Email**: Your email address
   - **Phone**: Your phone number (optional)
   - **Password**: Choose a strong password (at least 6 characters)
   - **Confirm Password**: Re-enter your password
5. Click **"Create Account"**
6. You will be automatically logged in and redirected to the Dashboard

### Step 2: Login (For Future Sessions)

After registration, for future logins:

1. Go to the application (you'll be redirected to `/login` if not logged in)
2. Enter your **Email** and **Password**
3. Click **"Sign In"**
4. You will be redirected to the Dashboard

### Step 3: Set Up Your System

#### 3.1 Add Courier Companies

1. Go to **Courier Companies** page from the sidebar
2. Click **"Add Courier Company"** button
3. Fill in the details:
   - Company Name (e.g., "Delhivery", "Blue Dart")
   - Contact Person
   - Phone Number
   - Office Address
4. Click **"Save"**

#### 3.2 Set Up Courier Rates

1. Go to **Rates** page from the sidebar
2. Click **"Add Rate"** button
3. Fill in the pricing details:
   - **Courier Company**: Select from dropdown
   - **City**: Enter city name (free text)
   - **Min Weight**: Minimum weight in grams (e.g., 0)
   - **Max Weight**: Maximum weight in grams (e.g., 1000)
   - **Price**: Price for this weight range
4. Click **"Save"**

**Example Rate Setup:**
- Delhivery → Mumbai → 0-1000g → ₹25
- Delhivery → Mumbai → 1000-2000g → ₹50
- Delhivery → Mumbai → 2000-5000g → ₹100

#### 3.3 Add Expense Categories (Optional)

1. Go to **Expenses** page
2. The system comes with default categories:
   - Fuel
   - Salary
   - Office
   - Courier Charges
   - Other
3. You can add more categories as needed

### Step 4: Start Using the System

#### Adding Parcels

1. Go to **Parcels** page
2. Click **"Add Parcel"** button
3. Fill in the parcel details:
   - **Tracking ID**: Unique identifier (manual entry)
   - **Courier Company**: Select from dropdown
   - **Customer Name**: Recipient name
   - **Phone**: 10-digit phone number
   - **Address**: Full address
   - **Country**: Select country
   - **State/City/District/Area**: Location details
   - **Pin Code**: 6-digit pin code
   - **Weight**: Weight in grams
   - **Amount**: Auto-calculated based on rates (or enter custom)
   - **Status**: Pending/Dispatched/Delivered/Cancelled
4. Click **"Save"**

**Note**: The amount is automatically calculated based on:
- Selected courier company
- Selected city
- Entered weight
- Configured rates

#### Printing Labels

1. Go to **Parcels** page
2. Find the parcel you want to print
3. Click the **Print** icon (printer button)
4. A print dialog will open with A5-sized label
5. Print the label

#### Tracking Parcels (Public)

1. Go to **Track Parcel** page (accessible without login)
2. Enter the **Tracking ID**
3. Click **"Track"**
4. View parcel status and details

#### Managing Expenses

1. Go to **Expenses** page
2. Click **"Add Expense"** button
3. Fill in:
   - **Title**: Expense description
   - **Amount**: Expense amount
   - **Category**: Select category
   - **Date**: Expense date
   - **Notes**: Additional notes (optional)
4. Click **"Save"**

#### Viewing Reports

1. Go to **Reports** page
2. Apply filters:
   - **Date Range**: Start and end date
   - **Courier Company**: Filter by company
   - **City**: Filter by city
   - **Status**: Filter by status
3. Click **"Generate Report"**
4. Export options:
   - **Excel**: Download as .xlsx file
   - **PDF**: Download as PDF
   - **CSV**: Download as CSV
   - **Print**: Direct print

### Step 5: Settings

1. Go to **Settings** page
2. Update your profile:
   - Name
   - Business Name
   - Default Currency
   - Default Country
3. Click **"Save Changes"**

## 🔐 User Roles

### Admin (First User)

- The **first user** to register automatically becomes an **Admin**
- Admin has full access to all features
- Can manage all data

### Regular Users

- All subsequent users are **Regular Users**
- Can only see and manage their own data
- Cannot access other users' parcels, expenses, etc.

## 🎨 Theme

- The application uses a **dark burgundy theme** (#a0001e)
- You can toggle between light and dark modes using the theme toggle in the header

## 📊 Dashboard

The dashboard shows:
- **Total Parcels**: Count of all parcels
- **Dispatched Parcels**: Count of dispatched parcels
- **Pending Parcels**: Count of pending parcels
- **Cancelled Parcels**: Count of cancelled parcels
- **Expense KPIs**: Daily, Weekly, Monthly, Yearly expenses
- **Charts**: Visual representation of data

## 🔒 Security

- All data is protected by Row Level Security (RLS)
- Users can only access their own data
- Authentication is required for all operations except tracking
- OTP-based login for enhanced security

## 💡 Tips

1. **Set up rates before adding parcels** - This ensures automatic price calculation
2. **Use consistent city names** - This helps with filtering and reporting
3. **Add expense categories** - Organize your expenses for better tracking
4. **Regular backups** - Export reports regularly for backup
5. **Track everything** - Add all parcels to maintain accurate records

## 🆘 Troubleshooting

### "Failed to save" errors

**Cause**: You are not logged in or your session expired

**Solution**:
1. Refresh the page
2. You will be redirected to login
3. Log in again with your email and password
4. Try saving again

### "Failed to load" errors

**Cause**: Authentication issue or network problem

**Solution**:
1. Check your internet connection
2. Refresh the page
3. Log in again if needed

### Cannot login / "Invalid credentials"

**Solution**:
1. Make sure you're using the correct email and password
2. Password is case-sensitive
3. If you forgot your password, you'll need to register a new account (password reset coming soon)

### Registration fails

**Solution**:
1. Make sure all required fields are filled (marked with *)
2. Password must be at least 6 characters
3. Passwords must match
4. Email must be valid format
5. Try using a different email if the error persists

## 📞 Support

For any issues or questions, please contact your system administrator.

---

**ParcelFlow** - Professional Courier Management System
