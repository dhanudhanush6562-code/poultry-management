# 💰 Income Feature - User Guide

## New Feature Added: Income Tracking

Your poultry management system now includes a comprehensive **Income Tracking** module in the User Dashboard!

---

## 🎯 Features

### 1️⃣ Income Tab
- New "💰 Income" tab in the menu bar
- Switch between "Daily Data" and "Income" seamlessly

### 2️⃣ Add Income Entry Form
- **Income Type Dropdown:**
  - 🥚 Egg Sale
  - 🍗 Meat Sale
- **Fields:**
  - Date (required)
  - Batch ID (optional)
  - Quantity (required)
  - Unit (e.g., eggs, kg, pieces)
  - Amount in ₹ (required)
  - Notes (optional)

### 3️⃣ Income History List View
- View all income entries in a table
- **Columns:**
  - Date
  - Type (with icons)
  - Batch ID
  - Quantity with unit
  - Amount (₹)
  - Actions (View/Delete)

### 4️⃣ Real-time Summary Cards
- **Total Income:** Shows combined egg + meat sales
- **Egg Sales:** Total from egg sales only
- **Meat Sales:** Total from meat sales only

### 5️⃣ Advanced Filtering
- Filter by income type (Egg Sale / Meat Sale)
- Filter by date range (From - To)
- Apply filters to see specific data

### 6️⃣ Monthly Income Graph
- Click **"📈 View Monthly Income Graph"** button
- Beautiful chart showing monthly trends
- Separate bars for Egg Sales and Meat Sales
- Hover for exact amounts

---

## 🚀 How to Use

### Adding an Income Entry:

1. **Go to User Dashboard**
   - Login as a user
   - Click the **"💰 Income"** tab

2. **Fill the Form:**
   ```
   Income Type: Select "Egg Sale" or "Meat Sale"
   Date: Select the sale date
   Batch ID: (Optional) Enter batch ID
   Quantity: Enter quantity sold
   Unit: Enter unit (e.g., eggs, kg)
   Amount: Enter total income in ₹
   Notes: (Optional) Add any notes
   ```

3. **Click "💾 Save Income Entry"**
   - Entry is saved to database
   - Appears in Income History table
   - Summary cards update automatically

### Viewing Income History:

1. Scroll down to **"Income History"** section
2. See all your income entries in a table
3. View **Total Income Summary** cards at the top

### Filtering Data:

1. Use the filter options:
   - **Filter by Type:** Select Egg Sale or Meat Sale
   - **From Date:** Select start date
   - **To Date:** Select end date
2. Click **"Apply Filter"**
3. Table updates with filtered results

### Viewing Details:

1. Click **"View"** button on any entry
2. Modal opens with complete details
3. Click **×** or outside modal to close

### Deleting Entries:

1. Click **"Delete"** button on any entry
2. Confirm deletion
3. Entry is removed (soft delete with timestamp)

### Viewing Graph:

1. Click **"📈 View Monthly Income Graph"** button
2. Modal opens with interactive chart
3. See monthly trends for Egg and Meat sales
4. Hover over bars for exact amounts

---

## 📊 Data Structure

Income entries are stored in Firestore with:

```javascript
{
  userId: "user-id",
  userEmail: "user@example.com",
  userName: "User Name",
  farmName: "Farm Name",
  incomeType: "Egg Sale" or "Meat Sale",
  date: "2025-11-29",
  batchId: "BATCH-001",
  quantity: 1000,
  unit: "eggs",
  amount: 5000.00,
  notes: "Optional notes",
  createdAt: "2025-11-29T10:30:00.000Z"
}
```

---

## 🔒 Security

- Income data is protected by Firestore rules
- Users can only see their own income entries
- Create, Read, Update, Delete operations require authentication
- UserId validation ensures data ownership

---

## 📱 Responsive Design

- Works on mobile, tablet, and desktop
- Tab navigation adapts to screen size
- Tables scroll horizontally on small screens
- Charts are responsive

---

## 🎨 UI Features

- **Tab Navigation:** Smooth switching between Daily Data and Income
- **Icons:** Visual indicators for income types (🥚/🍗)
- **Color Coding:**
  - Total Income: Green
  - Egg Sales: Blue
  - Meat Sales: Red
- **Animations:** Smooth fade-in effects
- **Modals:** Clean popups for details and graphs

---

## 💡 Use Cases

### Egg Sales Tracking:
```
Type: Egg Sale
Quantity: 1500 eggs
Amount: ₹6,000
Date: Daily basis
```

### Meat Sales Tracking:
```
Type: Meat Sale
Quantity: 100 kg
Amount: ₹15,000
Date: When birds are sold
```

### Monthly Analysis:
- View graph to see income trends
- Identify peak sale months
- Compare egg vs meat revenue
- Make business decisions

---

## 🐛 Troubleshooting

### Income tab not showing?
- Refresh the page
- Clear browser cache
- Check if you're logged in as a user

### Data not saving?
- Check all required fields (marked with *)
- Verify internet connection
- Check browser console for errors

### Graph not loading?
- Make sure you have income entries
- Check if Chart.js is loaded
- Refresh and try again

### Filters not working?
- Clear filters and try again
- Make sure date format is correct
- Check if data exists for selected criteria

---

## ✅ Testing Checklist

- [x] Tab switching works
- [x] Form saves data
- [x] History table displays entries
- [x] Summary cards update
- [x] Filters work correctly
- [x] View details modal opens
- [x] Delete functionality works
- [x] Monthly graph displays
- [x] Responsive on mobile
- [x] Data persists in Firestore

---

## 🎉 Benefits

1. **Track Revenue:** Know exactly how much you're earning
2. **Separate Categories:** Egg sales vs meat sales
3. **Monthly Trends:** Visualize income patterns
4. **Historical Data:** Keep records for accounting
5. **Easy Analysis:** Filter and view specific periods
6. **Professional Reports:** Export and analyze data

---

## 📞 Quick Reference

**Access:** User Dashboard → 💰 Income Tab

**Add Entry:** Fill form → Save

**View History:** Scroll to Income History section

**Filter:** Select criteria → Apply Filter

**Graph:** Click "📈 View Monthly Income Graph"

---

**Your poultry management system now has complete income tracking! 🚀🐔💰**
