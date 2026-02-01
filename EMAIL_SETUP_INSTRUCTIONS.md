# Email Notification Setup Instructions

## How to Get Email Notifications When Shruti Clicks "Yes"

I've added EmailJS integration to your Valentine's page. Follow these steps to set it up:

### Step 1: Create a Free EmailJS Account

1. Go to [https://www.emailjs.com/](https://www.emailjs.com/)
2. Click "Sign Up" and create a free account
3. Verify your email address

### Step 2: Set Up Email Service

1. After logging in, go to **Email Services**
2. Click **Add New Service**
3. Choose your email provider (Gmail, Outlook, etc.)
4. Follow the instructions to connect your email
5. Copy the **Service ID** (you'll need this later)

### Step 3: Create Email Template

1. Go to **Email Templates**
2. Click **Create New Template**
3. Set up your template with these fields:
   - **Subject**: `🎉 Shruti Said YES! 💕`
   - **Content**:

     ```
     Hello {{to_name}},

     Great news! {{from_name}} just said YES to being your Valentine! 💕

     {{message}}

     Time: {{current_time}}
     ```

4. Save the template and copy the **Template ID**

### Step 4: Get Your Public Key

1. Go to **Account** → **General**
2. Find your **Public Key** (it looks like: `user_xxxxxxxxxxxxxxxxx`)
3. Copy this key

### Step 5: Update the HTML File

Open `love.html` and replace these three values:

```javascript
// Line ~236: Replace YOUR_PUBLIC_KEY
emailjs.init("YOUR_PUBLIC_KEY"); // ← Paste your Public Key here

// Line ~343-344: Replace these IDs
const serviceID = "YOUR_SERVICE_ID"; // ← Paste your Service ID here
const templateID = "YOUR_TEMPLATE_ID"; // ← Paste your Template ID here
```

### Step 6: Test It!

1. Open `love.html` in your browser
2. Click the "Yes" button
3. Check your email inbox - you should receive a notification!

## Example Configuration

After setup, your code should look like this:

```javascript
emailjs.init("user_abc123xyz456");

const serviceID = "service_gmail123";
const templateID = "template_valentine";
```

## Troubleshooting

- **No email received?** Check your spam folder
- **Console errors?** Make sure all IDs are correct
- **Still not working?** Verify your EmailJS account is active and email service is connected

## Free Tier Limits

EmailJS free tier includes:

- 200 emails per month
- Perfect for this use case!

---

**Note**: Keep your Public Key safe but know that it's designed to be used in client-side code. The Service ID and Template ID can also be public.
