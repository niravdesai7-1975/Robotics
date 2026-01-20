# EmailJS Troubleshooting - Not Receiving Emails

If you're not receiving emails, check these common issues:

## 1. Check EmailJS Template Configuration

**Most Common Issue:** The recipient email must be set in the template settings, not just as a variable.

1. Go to https://dashboard.emailjs.com/admin/template
2. Click on template `template_hlgp4ne`
3. Check the **"To Email"** field - it MUST be set to: `niravdesai7@gmail.com`
4. Make sure it's NOT set to `{{to_email}}` or any variable

## 2. Verify Template Variables Match

Your template should use these variable names:
- `{{from_name}}` - Sender's full name
- `{{from_email}}` - Sender's email address
- `{{subject}}` - Email subject
- `{{message}}` - Email message
- `{{reply_to}}` - Reply-to email (optional)

## 3. Check Email Service Connection

1. Go to https://dashboard.emailjs.com/admin/integration
2. Click on service `service_y3e7g69`
3. Verify it's connected to your Gmail account
4. Make sure the service is **Active** (not paused)

## 4. Check Browser Console for Errors

1. Open your website
2. Press F12 (or Cmd+Option+I on Mac) to open Developer Tools
3. Click the "Console" tab
4. Submit the form
5. Look for any error messages
6. Check if you see "Email sent successfully!" or error details

## 5. Check EmailJS Dashboard Logs

1. Go to https://dashboard.emailjs.com/admin/log
2. Look for recent email attempts
3. Check if emails are being sent but failing
4. Look for error messages

## 6. Check Spam Folder

- Check your spam/junk folder in `niravdesai7@gmail.com`
- Emails might be filtered as spam

## 7. Verify Template Content

Your EmailJS template should look something like this:

```
Subject: Contact Form: {{subject}}

From: {{from_name}} ({{from_email}})

Subject: {{subject}}

Message:
{{message}}

---
This email was sent from the XMachina contact form.
Reply to: {{reply_to}}
```

## 8. Test EmailJS Service Directly

You can test if EmailJS is working by checking:
- Service status: https://dashboard.emailjs.com/admin/integration
- Recent logs: https://dashboard.emailjs.com/admin/log
- Template test: Use the "Test" button in the template editor

## Quick Fix Checklist

- [ ] Template "To Email" is set to `niravdesai7@gmail.com` (not a variable)
- [ ] Email service is connected and active
- [ ] Template variables match: `from_name`, `from_email`, `subject`, `message`
- [ ] Checked browser console for errors
- [ ] Checked EmailJS dashboard logs
- [ ] Checked spam folder

## Still Not Working?

If emails still aren't arriving:
1. Check the browser console (F12) for specific error messages
2. Check EmailJS dashboard logs for delivery status
3. Try testing the template directly from EmailJS dashboard
4. Verify your Gmail account allows third-party apps (if using Gmail service)
