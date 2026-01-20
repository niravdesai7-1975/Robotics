# EmailJS Setup Guide

To enable email sending from the contact form, you need to set up EmailJS (free service).

## Step 1: Create EmailJS Account

1. Go to https://www.emailjs.com/
2. Sign up for a free account
3. Verify your email address

## Step 2: Create Email Service

1. In EmailJS dashboard, go to **Email Services**
2. Click **Add New Service**
3. Choose your email provider (Gmail recommended)
4. Connect your Gmail account (niravdesai7@gmail.com)
5. Note your **Service ID** (e.g., `service_xxxxxxx`)

## Step 3: Create Email Template

1. Go to **Email Templates**
2. Click **Create New Template**
3. Use this template:

```
Subject: Contact Form: {{subject}}

From: {{from_name}} ({{from_email}})

Subject: {{subject}}

Message:
{{message}}

---
This email was sent from the XMachina contact form.
```

4. Set **To Email** to: `niravdesai7@gmail.com`
5. Note your **Template ID** (e.g., `template_xxxxxxx`)

## Step 4: Get Public Key

1. Go to **Account** → **General**
2. Copy your **Public Key** (e.g., `xxxxxxxxxxxxx`)

## Step 5: Update index.html

Open `index.html` and replace these placeholders:

1. Replace `YOUR_PUBLIC_KEY` with your Public Key
2. Replace `YOUR_SERVICE_ID` with your Service ID  
3. Replace `YOUR_TEMPLATE_ID` with your Template ID

Look for these lines in the JavaScript section:
```javascript
emailjs.init("YOUR_PUBLIC_KEY");
emailjs.send(
    'YOUR_SERVICE_ID',
    'YOUR_TEMPLATE_ID',
    ...
)
```

## Example:

After setup, your code should look like:
```javascript
emailjs.init("abc123xyz789");
emailjs.send(
    'service_gmail123',
    'template_contact456',
    ...
)
```

## Testing

1. Open your website
2. Click "COMPANY"
3. Fill out the contact form
4. Submit
5. Check niravdesai7@gmail.com for the email

## Troubleshooting

- Make sure all three IDs are correct
- Check EmailJS dashboard for error logs
- Verify your email service is connected
- Make sure the template has the correct variable names
