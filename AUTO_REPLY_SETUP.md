# Setup Auto-Reply for Contact Form

## Goal
- **Form submitter** (e.g., nirav@nvibe.ai) receives: "We have received your message and will get back to you soon"
- **You** (niravdesai7@gmail.com) receive: The detailed form data (name, email, subject, message)

## Step-by-Step Setup

### Step 1: Configure the Main Template (Contact Us)
1. Go to: https://dashboard.emailjs.com/admin/template
2. Open template `template_erq64ic` (Contact Us)
3. **Content Tab:**
   - Keep the current content (the form data notification)
   - "To Email" should be: `niravdesai7@gmail.com` (you receive form data)
   - This sends form data TO YOU

### Step 2: Configure Auto-Reply Tab
1. Click the **"Auto-Reply"** tab in your template
2. **Enable Auto-Reply:** Turn it ON/Enable it
3. **Auto-Reply Settings:**
   - **"To Email"**: `{{from_email}}` (sends to the form submitter)
   - **Subject**: `Thank you for contacting XMachina`
   - **Content**: Use this template:

```
Hi {{from_name}},

Thank you for reaching out to us! We have received your message and will get back to you as soon as possible.

Best regards,
The XMachina Team
```

4. **From Settings:**
   - **From Name**: `XMachina Team`
   - **From Email**: Use Default Email Address (checked)

### Step 3: Save
1. Click **"Save"** button
2. Make sure both Content and Auto-Reply are saved

## How It Works

**When someone submits the form:**
1. **You receive** (at niravdesai7@gmail.com):
   - Form data: name, email, subject, message
   - This is the notification email

2. **Form submitter receives** (at their email, e.g., nirav@nvibe.ai):
   - Confirmation: "We have received your message and will get back to you soon"
   - This is the auto-reply

## Template Variables for Auto-Reply

The auto-reply can use:
- `{{from_name}}` - The form submitter's name
- `{{from_email}}` - The form submitter's email (use this in "To Email")
- `{{subject}}` - The subject they entered (optional)

## Test

After setup:
1. Submit the contact form with a test email
2. Check YOUR inbox (niravdesai7@gmail.com) - should see form data
3. Check the TEST EMAIL inbox - should see confirmation message
