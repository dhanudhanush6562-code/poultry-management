# COMPLETE TEST - Send Data to Supervisor

## STEP-BY-STEP GUIDE

### STEP 1: Clean Test (Delete Old Data - Optional)

Go to Firebase Console:
1. https://console.firebase.google.com/
2. Select: poutry-management
3. Click: Firestore Database
4. Delete all documents in `dailyData` collection (to start fresh)

---

### STEP 2: Create/Verify Supervisor Account

1. Open browser at: `http://localhost:3000/signup`
2. Sign up with:
   - Email: `newu8752@gmail.com`
   - Password: (your choice)
   - User Type: **SUPERVISOR** (very important!)
   - Fill other fields
3. Click Sign Up
4. Logout

---

### STEP 3: Send Data as User

1. Go to: `http://localhost:3000/login`
2. Login with a **USER** account (NOT supervisor)
3. You'll be at User Dashboard

4. **Fill the form COMPLETELY:**
   ```
   Batch ID: TEST-BATCH-001
   Batch Number: 1
   Date: (select today)
   Egg Count: 100
   Mortality: 2
   Feed (kg): 50.5
   Vaccination: Test vaccine
   Medicine: Test medicine
   Supervisor Email: newu8752@gmail.com  ← VERY IMPORTANT!
   ```

5. **Open Console (F12)** - Keep it open!

6. Click **"Save Data"** button
   - Wait for: "Data saved successfully!"
   - Console should show: "Data saved with ID: xxx"

7. **IMPORTANT:** Make sure these fields are STILL filled:
   - Batch ID: TEST-BATCH-001
   - Date: (today's date)
   - Supervisor Email: newu8752@gmail.com

8. Click **"Send to Supervisor"** button

9. **Check Console Messages:**
   You should see:
   ```
   Sending 1 record(s) to supervisor: newu8752@gmail.com
   Updating document: xxx with supervisor email: newu8752@gmail.com
   Document data: {userId: "...", batchId: "TEST-BATCH-001", ...}
   All documents updated successfully
   Supervisor should query for: supervisorEmail == newu8752@gmail.com && sentToSupervisor == true
   ```

10. **Check "Your Data History" table:**
    - Should show: **"✓ Sent"** in green

---

### STEP 4: View Data as Supervisor

1. **Open NEW incognito/private window** (or logout first)
2. Go to: `http://localhost:3000/login`
3. Login with: `newu8752@gmail.com` (supervisor account)
4. You'll be at Supervisor Dashboard

5. **Open Console (F12)**

6. Click **"🔄 Refresh Data"** button

7. **Check Console Output:**
   ```
   Querying all dailyData for supervisor: newu8752@gmail.com
   Total records in dailyData collection: X
   Document xxx:
     - sentToSupervisor: true
     - supervisorEmail: newu8752@gmail.com
     - userName: (user name)
     - batchId: TEST-BATCH-001
     ✓ MATCH! Adding to allData
   Records for newu8752@gmail.com: 1
   ```

8. **Check Dashboard Display:**
   - Statistics should show: Total Users: 1, Total Batches: 1
   - Scroll to "User Data by Batches"
   - You should see a card with user's name
   - Click to expand and see batch data

---

## TROUBLESHOOTING

### Problem: Console shows "Sending 0 record(s)"
**Solution:** 
- Make sure you filled Batch ID and Date
- Make sure you clicked "Save Data" FIRST
- The form should have the same Batch ID and Date you just saved

### Problem: Console shows "No data found to send"
**Solution:**
- You need to save the data first with "Save Data" button
- Then keep the Batch ID and Date fields filled
- Then click "Send to Supervisor"

### Problem: Supervisor sees "Records for email: 0"
**Check:**
1. Did you use EXACT email: `newu8752@gmail.com`?
2. Is supervisor account userType = 'supervisor'?
3. Look at console - what's in the documents?

### Problem: Console shows "✗ NO MATCH - supervisorEmail is undefined"
**Solution:**
- User didn't enter supervisor email before clicking "Send to Supervisor"
- Delete the data and try again, making sure to fill supervisor email field

---

## VERIFY IN FIREBASE CONSOLE

1. Go to: https://console.firebase.google.com/
2. Project: poutry-management
3. Firestore Database
4. Open `dailyData` collection
5. Click on a document
6. **Check these fields:**
   - `sentToSupervisor`: should be `true`
   - `supervisorEmail`: should be `newu8752@gmail.com`
   - `userId`: should have a value
   - `batchId`: should be `TEST-BATCH-001`

If these are correct, the supervisor WILL see the data!

---

## IMPORTANT NOTES

✅ **Save Data FIRST** - Always click "Save Data" before "Send to Supervisor"
✅ **Keep Form Filled** - Don't clear Batch ID and Date after saving
✅ **Exact Email Match** - Supervisor email must match exactly
✅ **Supervisor Type** - Supervisor account must have userType: 'supervisor'
✅ **Refresh** - Click "🔄 Refresh Data" in supervisor dashboard to reload

---

**Try this complete process now and tell me what you see in the console!**
