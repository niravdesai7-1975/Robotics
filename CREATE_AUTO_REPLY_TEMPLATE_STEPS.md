# Create Auto-Reply Template - Step by Step

## Step 1: Create New Template
1. Go to: https://dashboard.emailjs.com/admin/template
2. Click "Create New Template" or "+ New Template"
3. Name it: "Contact Form Auto-Reply"

## Step 2: Configure Content Tab

**Subject:**
```
Thank you for contacting XMachina
```

**Content:**
```
Hi {{from_name}},

Thank you for reaching out to us! We have received your message and will get back to you as soon as possible.

Best regards,
The XMachina Team
```

## Step 3: Configure Right Panel

**To Email:**
```
{{from_email}}
```
(This sends to the form submitter)

**From Name:**
```
XMachina Team
```

**From Email:**
- Check "Use Default Email Address"

**Reply To:**
- Leave empty or use: `niravdesai7@gmail.com`

## Step 4: Save and Get Template ID
1. Click "Save"
2. Copy the Template ID from the URL
   - URL will be: `https://dashboard.emailjs.com/admin/templates/XXXXXXX`
   - The XXXXXX part is your Template ID
   - Full ID format: `template_XXXXXXX`
3. Share the Template ID with me

## Step 5: Test
1. Click "Test It" in EmailJS
2. Fill in:
   - `from_name`: Test User
   - `from_email`: test@example.com
3. Send test
4. Should receive confirmation at test@example.com
