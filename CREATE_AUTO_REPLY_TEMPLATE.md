# Create New Auto-Reply Template

Since the existing auto-reply template can't be updated, create a new one:

## Step 1: Create New Template
1. Go to: https://dashboard.emailjs.com/admin/template
2. Click "Create New Template" or "+ New Template"
3. Name it: "Contact Form Auto-Reply"

## Step 2: Configure the Template

**Content Tab:**
- **Subject**: `Thank you for contacting XMachina`
- **Content**: 
  ```
  Hi {{from_name}},
  
  Thank you for reaching out to us! We have received your message and will get back to you as soon as possible.
  
  Best regards,
  The XMachina Team
  ```

**Right Panel:**
- **To Email**: `{{from_email}}` (sends to form submitter)
- **From Name**: `XMachina Team`
- **From Email**: Use Default Email Address (checked)
- **Reply To**: Leave empty or use `niravdesai7@gmail.com`

## Step 3: Save and Get Template ID
1. Click "Save"
2. Copy the Template ID from the URL (it will look like `template_xxxxxxx`)
3. Share it with me to update the code

## Step 4: Link It (Optional)
If you want EmailJS to send it automatically:
1. Go to your Contact Us template: https://dashboard.emailjs.com/admin/templates/bpe9ngw
2. Click "Auto-Reply" tab
3. Select your new auto-reply template from the dropdown
4. Save

OR we can send both emails manually in the code (which is what we'll do).
