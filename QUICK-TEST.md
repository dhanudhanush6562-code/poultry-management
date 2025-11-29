# 🧪 QUICK FUNCTIONALITY TEST

## Before Demo - Run These Tests (5 minutes)

### Test 1: Landing Page ✅
1. Open `http://localhost:3000/`
2. Should see: "Welcome to Poultry Management System"
3. Click "Login" and "Sign Up" buttons - both should work

**Expected:** Landing page loads, navigation works

---

### Test 2: Sign Up (User) ✅
1. Go to `http://localhost:3000/signup`
2. Fill form:
   - Email: `testuser@demo.com`
   - Password: `Test123!`
   - Confirm Password: `Test123!`
   - Farm Name: `Demo Farm`
   - User Type: **User**
3. Click "Sign Up"

**Expected:** Redirect to user dashboard, no errors

---

### Test 3: User Dashboard ✅
1. Should be at `http://localhost:3000/user-dashboard`
2. Check these elements exist:
   - ✅ "Daily Poultry Data Entry" form
   - ✅ Supervisor Email field (highlighted)
   - ✅ All input fields (Batch ID, Date, Eggs, etc.)
   - ✅ "💾 Save Data" button
   - ✅ "📤 Send to Supervisor" button
   - ✅ "Your Data History" section

**Expected:** Dashboard loads completely, all elements visible

---

### Test 4: Save Data ✅
1. Fill form:
   - Supervisor Email: `supervisor@demo.com`
   - Batch ID: `TEST-001`
   - Batch Number: `1`
   - Date: Today
   - Egg Count: `1000`
   - Mortality: `3`
   - Feed: `200`
   - Vaccination: `Test Vaccine`
   - Medicine: `Test Medicine`
2. Click "💾 Save Data"

**Expected:** 
- Success message appears
- Data appears in "Your Data History" table
- Browser console shows: "Data saved successfully"

---

### Test 5: Send to Supervisor ✅
1. Click "📤 Send to Supervisor"
2. Confirm the dialog

**Expected:**
- Success message: "Data sent successfully"
- Table shows "✓ Sent" badge
- Browser console shows: "All documents updated successfully"

---

### Test 6: Sign Up (Supervisor) ✅
1. Logout (click profile icon → Logout)
2. Go to `http://localhost:3000/signup`
3. Fill form:
   - Email: `supervisor@demo.com` ⚠️ **Must match what user entered!**
   - Password: `Super123!`
   - Confirm Password: `Super123!`
   - Farm Name: `Manager`
   - User Type: **Supervisor**
4. Click "Sign Up"

**Expected:** Redirect to supervisor dashboard

---

### Test 7: Supervisor Dashboard ✅
1. Should be at `http://localhost:3000/supervisor-dashboard`
2. Click "🔄 Refresh Data"

**Expected:**
- Statistics cards show data (eggs, mortality, etc.)
- "User Data by Batches" section shows data
- See: "testuser@demo.com - Batch: TEST-001"
- "View Details" button appears

---

### Test 8: View Details ✅
1. Click "View Details" on the batch card
2. Modal opens

**Expected:**
- Modal shows complete information
- All fields visible (eggs, mortality, feed, etc.)
- Close button works

---

### Test 9: Charts ✅
1. Scroll down on supervisor dashboard
2. Check charts section

**Expected:**
- 3 charts visible:
  - Egg Production Trend (line chart)
  - Mortality Analysis (bar chart)
  - Feed Consumption (bar chart)
- Charts show data properly

---

### Test 10: Export PDF ✅
1. Click "📥 Export to PDF" button
2. Wait for download

**Expected:**
- PDF file downloads
- PDF contains all data in table format
- No errors in console

---

### Test 11: Google Sign-In ✅
1. Logout
2. Go to Login page
3. Click "Continue with Google"
4. Sign in with Google account

**Expected:**
- Google popup opens
- After signing in, redirects to appropriate dashboard
- User type is set correctly

---

### Test 12: Database Inspector (Optional) 🔍
1. Open `http://localhost:3000/database-inspector`
2. Click "🔄 Load All Documents"
3. Type `supervisor@demo.com` in filter
4. Click "🔍 Filter"

**Expected:**
- Shows all documents
- Filter finds matching documents
- Console shows detailed field information

---

## ✅ All Tests Passed?

If all 12 tests pass, your system is **100% ready for demo!**

---

## 🚨 If Any Test Fails:

### Landing Page doesn't load:
```powershell
cd "c:\vs\poutry management"
npm run dev
```

### Sign Up fails:
- Check Firebase Console → Authentication
- Verify Firebase config in HTML files

### Data doesn't save:
- Check browser console for errors
- Verify Firestore rules are deployed
- Check Firebase Console → Firestore Database

### Supervisor sees no data:
- Verify emails match EXACTLY
- Use Database Inspector to check
- See `CRITICAL-DEBUG-GUIDE.md`

### Charts don't show:
- Make sure there's data in the database
- Check browser console for Chart.js errors
- Try refreshing the page

---

## 📊 Test Results Summary

Date: _________________
Time: _________________

| Test | Status | Notes |
|------|--------|-------|
| 1. Landing Page | ☐ Pass ☐ Fail | |
| 2. Sign Up (User) | ☐ Pass ☐ Fail | |
| 3. User Dashboard | ☐ Pass ☐ Fail | |
| 4. Save Data | ☐ Pass ☐ Fail | |
| 5. Send to Supervisor | ☐ Pass ☐ Fail | |
| 6. Sign Up (Supervisor) | ☐ Pass ☐ Fail | |
| 7. Supervisor Dashboard | ☐ Pass ☐ Fail | |
| 8. View Details | ☐ Pass ☐ Fail | |
| 9. Charts | ☐ Pass ☐ Fail | |
| 10. Export PDF | ☐ Pass ☐ Fail | |
| 11. Google Sign-In | ☐ Pass ☐ Fail | |
| 12. Database Inspector | ☐ Pass ☐ Fail | |

**Overall Status:** ☐ READY ☐ NEEDS FIXES

---

## 🎯 Time Required: ~5 minutes

Run this test the night before or morning of your presentation!

**Your system is ready! Good luck! 🚀**
