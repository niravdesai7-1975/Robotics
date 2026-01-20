# Fix EmailJS Template - Send Form Data Instead of Auto-Reply

## The Problem
You're receiving an auto-reply message ("We've received your message") instead of the actual form data.

## Solution: Update Template Content

### Step 1: Go to Template Editor
1. Go to: https://dashboard.emailjs.com/admin/template
2. Click on template `template_erq64ic` (Contact Us)

### Step 2: Update the Content Tab

**In the Content Editor, replace ALL content with this:**

```
A message has been received from the contact form.

From: {{from_name}}
Email: {{from_email}}

Subject: {{subject}}

Message:
{{message}}

---
Reply to: {{reply_to}}
This email was sent from the XMachina contact form.
```

### Step 3: Verify Settings

**In the right panel, make sure:**
- **"To Email"**: `niravdesai7@gmail.com` (your email to receive submissions)
- **"From Name"**: `{{from_name}}` or `XMachina Contact Form`
- **"From Email"**: Use Default Email Address (checked)
- **"Reply To"**: `{{reply_to}}` or `{{from_email}}`

### Step 4: Disable Auto-Reply

1. Click the **"Auto-Reply"** tab
2. Make sure Auto-Reply is **DISABLED** or **OFF**
3. If it's enabled, turn it off

### Step 5: Save

1. Click **"Save"** button at the top right
2. Wait a few seconds for it to save

### Step 6: Test

1. Go back to your website
2. Submit the contact form with test data
3. Check `niravdesai7@gmail.com`
4. You should now see the actual form data (name, email, subject, message)

## What Should Happen

When someone fills out the form with:
- Name: John Doe
- Email: nirav@nvibe.ai
- Subject: Test
- Message: Hello

You should receive an email at `niravdesai7@gmail.com` that shows:
- From: John Doe
- Email: nirav@nvibe.ai
- Subject: Test
- Message: Hello

NOT an auto-reply saying "We've received your message".
