# 📋 GoDaddy Website Builder Setup Guide
## For smartkitchenforme.com

This guide will walk you through adding the recipe share page to your GoDaddy website.

---

## 📌 Prerequisites

- GoDaddy account with active website
- Access to GoDaddy Website Builder
- The HTML templates provided

---

## 🚀 Method 1: Using HTML Section (Recommended)

This method works with GoDaddy's Website Builder (the drag-and-drop editor).

### Step 1: Log in to GoDaddy

1. Go to [https://www.godaddy.com](https://www.godaddy.com)
2. Click **Sign In** (top right)
3. Enter your credentials
4. You'll land on your Dashboard

### Step 2: Open Website Builder

1. From the Dashboard, find **My Products**
2. Locate your website (smartkitchenforme.com)
3. Click **Manage** or **Edit Website**
4. This opens the GoDaddy Website Builder

### Step 3: Create a New Page for "Share"

1. In the editor, look at the left sidebar
2. Click **Pages** (or the pages icon)
3. Click **+ Add Page**
4. Name it: `share`
5. For Page URL/Slug, enter: `share`
   - This makes it accessible at: `smartkitchenforme.com/share`
6. Click **Done** or **Create**

### Step 4: Add HTML Section

1. With your new "share" page selected
2. Click **+ Add Section** (usually a button on the page)
3. Scroll down to find **HTML** or **Embed Code** or **Custom Code**
   - In some GoDaddy versions it's called:
     - "HTML"
     - "Embed"
     - "Custom Code"
     - "Code Block"
4. Click to add it to your page

### Step 5: Paste the Share Page Code

1. Click on the HTML section you just added
2. Click **Edit** or **Edit Code** or the `</>` icon
3. A code editor window will open
4. **Delete any existing code** in the box
5. **Copy the ENTIRE content** of `share-page.html`
6. **Paste it** into the code editor
7. Click **Done** or **Apply** or **Save**

### Step 6: Adjust Section Settings

1. Click on the HTML section
2. Look for **Section Settings** or **Layout**
3. Set the section to **Full Width** if available
4. Remove any padding/margins if the option exists
5. This ensures the page looks correct

### Step 7: Hide the Header/Footer (Optional)

Since the share page has its own design, you may want to hide GoDaddy's default header/footer:

1. Click on the page settings (gear icon)
2. Look for **Show Header** → Toggle OFF
3. Look for **Show Footer** → Toggle OFF
4. This gives a cleaner, app-like experience

### Step 8: Publish

1. Click **Preview** to check how it looks
2. Test on both desktop and mobile views
3. If everything looks good, click **Publish**
4. Your page is now live at: `smartkitchenforme.com/share`

---

## 🚀 Method 2: Using File Manager (For Full Control)

This method uploads raw HTML files directly.

### Step 1: Access File Manager

1. Log in to GoDaddy
2. Go to **My Products**
3. Find **Web Hosting** (if you have it) or **Manage** your website
4. Look for **File Manager** or **cPanel**
5. Click to open it

### Step 2: Navigate to Public Folder

1. In File Manager, find the `public_html` folder
   - Or it might be called `www` or `htdocs`
2. Double-click to open it

### Step 3: Upload HTML Files

1. Click **Upload** button (usually at the top)
2. Select `share-page.html` from your computer
3. Wait for upload to complete
4. Rename the file to `share.html` (remove "-page")
   - Right-click → Rename → `share.html`

### Step 4: Test the Page

1. Open a new browser tab
2. Go to: `https://smartkitchenforme.com/share.html`
3. The page should display

### Step 5: Set Up URL Redirect (Optional)

To make `smartkitchenforme.com/share` work (without .html):

1. Create a file called `.htaccess` in public_html
2. Add this content:
```
RewriteEngine On
RewriteRule ^share$ share.html [L]
```
3. Save the file

---

## 🚀 Method 3: Using GoDaddy's Websites + Marketing

If you're using GoDaddy's newer "Websites + Marketing" builder:

### Step 1: Open Your Site

1. Go to GoDaddy Dashboard
2. Click on your website
3. Click **Edit Site** or **Edit Website**

### Step 2: Add a Blank Page

1. Click the **Pages** panel (left side)
2. Click **Add Page**
3. Choose **Blank Page**
4. Name it "Share Recipe"
5. Set URL to "share"

### Step 3: Add HTML Block

1. On your new page, click **Add Section**
2. Find and select **HTML** or **Embed**
3. Click the section to edit
4. Paste the share-page.html code
5. Save

### Step 4: Configure Page Settings

1. Click the gear icon on the page
2. Under "Page Settings":
   - Title: "Share Recipe - Smart Kitchen For Me"
   - URL: share
   - Show in Navigation: OFF (optional)
3. Save

### Step 5: Preview and Publish

1. Click **Preview** (eye icon)
2. Test the page
3. Click **Publish** when ready

---

## ✅ Testing Your Share Page

After publishing, test that the integration works:

### Test 1: Direct Access
1. Open: `https://smartkitchenforme.com/share`
2. You should see the "No Recipe Found" empty state
3. This confirms the page is working

### Test 2: With Recipe Data
1. Open this test URL (copy the entire line):
```
https://smartkitchenforme.com/share?recipe=%7B%22title%22%3A%22Test%20Chicken%20Recipe%22%2C%22time%22%3A%2220%20min%22%2C%22difficulty%22%3A%22Easy%22%2C%22ingredients%22%3A%5B%22Chicken%22%2C%22Garlic%22%2C%22Soy%20Sauce%22%5D%2C%22instructions%22%3A%5B%22Cut%20chicken%22%2C%22Cook%20in%20pan%22%2C%22Add%20sauce%22%5D%2C%22mealType%22%3A%22dinner%22%7D
```
2. You should see the recipe displayed with:
   - Title: "Test Chicken Recipe"
   - Time: 20 min
   - Difficulty: Easy
   - Ingredients: Chicken, Garlic, Soy Sauce
   - Instructions: 3 steps

### Test 3: From the App
1. Open your Smart Kitchen app
2. Go to Cook tab
3. Find a recipe
4. Tap the 📤 Share button
5. Select "Share to Community"
6. The website should open with your recipe

---

## 🔧 Troubleshooting

### Problem: Page shows raw HTML code
**Solution:** Make sure you're using the HTML/Embed section, not a regular text section.

### Problem: Page looks broken/unstyled
**Solution:** 
- Ensure you copied the ENTIRE file including `<style>` tags
- Check that no code was cut off
- Try Method 2 (File Manager) instead

### Problem: Recipe doesn't appear
**Solution:**
- Check the browser console for errors (F12 → Console)
- Ensure the URL has `?recipe=` parameter
- Verify the JSON data is properly encoded

### Problem: Rating doesn't save
**Solution:** 
- Currently ratings save to browser localStorage (demo mode)
- For persistent storage, set up Google Form integration (see below)

### Problem: Can't find HTML section in GoDaddy
**Solution:**
- GoDaddy changes their interface often
- Try searching for: "Embed", "Code", "Custom Code", "HTML"
- Or use Method 2 (File Manager)

---

## 📊 Adding Google Form for Ratings (Optional)

To permanently save ratings and comments:

### Step 1: Create Google Form

1. Go to [https://forms.google.com](https://forms.google.com)
2. Click **+ Blank** to create new form
3. Add these questions:
   - **Recipe Name** (Short answer)
   - **Rating** (Multiple choice: 1, 2, 3, 4, 5)
   - **Comment** (Paragraph)
   - **Date** (Short answer)

### Step 2: Get Form Details

1. Click **Send** button
2. Click the link icon (🔗)
3. Copy the form URL
4. Click the 3 dots menu → **Get pre-filled link**
5. Fill in test data and click **Get Link**
6. From this URL, extract the `entry.XXXXXXX` IDs for each field

### Step 3: Update share-page.html

Find this section in the code and uncomment/update it:

```javascript
function submitToGoogleForm(data) {
  const formUrl = 'https://docs.google.com/forms/d/e/YOUR_FORM_ID/formResponse';
  const formData = new FormData();
  formData.append('entry.XXXXXX', data.recipe);   // Recipe name field ID
  formData.append('entry.XXXXXX', data.rating);   // Rating field ID  
  formData.append('entry.XXXXXX', data.comment);  // Comment field ID
  formData.append('entry.XXXXXX', data.timestamp); // Date field ID
  
  fetch(formUrl, {
    method: 'POST',
    mode: 'no-cors',
    body: formData
  });
}
```

### Step 4: View Responses

1. In Google Forms, click **Responses** tab
2. Click the Google Sheets icon to create a spreadsheet
3. All ratings will be collected there!

---

## 📱 Setting Up Home Page (Optional)

To also use the home page template:

1. Follow the same steps as above
2. Edit your **main/home page** instead of creating new
3. Paste the `index.html` content
4. Or selectively copy sections you want

---

## 🎉 You're Done!

Your smartkitchenforme.com is now integrated with the Smart Kitchen app!

### What Users Can Do:
- ✅ Share recipes from the app to the website
- ✅ View recipe details beautifully formatted
- ✅ Rate recipes (1-5 stars)
- ✅ Leave comments
- ✅ Share to Facebook, WhatsApp, Twitter
- ✅ Copy recipe link

### Next Steps:
1. Customize colors/branding to match your style
2. Add more pages (About, Contact, etc.)
3. Set up Google Form for persistent ratings
4. Promote your website!

---

## 📞 Need Help?

If you encounter issues:
1. Check GoDaddy's help documentation
2. Contact GoDaddy support
3. Review this guide again

Good luck with your Smart Kitchen For Me website! 🍳
