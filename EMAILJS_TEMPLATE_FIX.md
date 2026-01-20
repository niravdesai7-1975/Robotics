# Fix EmailJS Template - Step by Step

## The Problem
Your template is currently set up as an auto-reply template, which sends a confirmation message. Instead, you need it to send the FORM DATA to you.

## Solution: Update Your Template

### Step 1: Go to EmailJS Template Editor
1. Go to: https://dashboard.emailjs.com/admin/template
2. Click on template `template_hlgp4ne` (Contact Us)

### Step 2: Update "To Email" Field
- In the "To Email" field, enter: `niravdesai7@gmail.com`
- Make sure it's NOT a variable like `{{to_email}}` or `{{from_email}}`
- It should be the actual email address: `niravdesai7@gmail.com`

### Step 3: Update Subject Line
Replace the subject with:
```
Contact Form: {{subject}}
```

### Step 4: Replace the Email Body Content
Delete all the current content and replace it with:

```
From: {{from_name}}
Email: {{from_email}}

Subject: {{subject}}

Message:
{{message}}

---
Reply to: {{reply_to}}
This email was sent from the XMachina contact form.
```

### Step 5: Save the Template
Click "Save" button

## What This Does
- Sends the form data TO `niravdesai7@gmail.com` (you)
- Shows the sender's name, email, subject, and message
- Allows you to reply directly to the person who filled out the form

## Test
After saving:
1. Submit the contact form on your website
2. Check `niravdesai7@gmail.com` inbox
3. You should see the actual form data (name, email, subject, message)

## Important Notes
- The "To Email" must be `niravdesai7@gmail.com` (hardcoded, not a variable)
- The template variables must match exactly: `{{from_name}}`, `{{from_email}}`, `{{subject}}`, `{{message}}`, `{{reply_to}}`
- This is a NOTIFICATION template (sends to you), not an AUTO-REPLY template (sends to form submitter)
