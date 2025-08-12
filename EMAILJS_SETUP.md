# EmailJS Setup Guide for Portfolio Contact Form

## 🚀 Quick Setup Steps

### 1. Create EmailJS Account
1. Go to [EmailJS.com](https://www.emailjs.com/)
2. Sign up for a free account
3. Verify your email address

### 2. Add Email Service
1. In EmailJS dashboard, go to "Email Services"
2. Click "Add New Service"
3. Choose "Gmail" (or your preferred email provider)
4. Connect your Gmail account (as8759111@gmail.com)
5. Note down the **Service ID** (e.g., `service_abc123`)

### 3. Create Email Template
1. Go to "Email Templates"
2. Click "Create New Template"
3. Use this template:

**Template Name:** `portfolio_contact`

**Subject:** `New Contact from Portfolio: {{subject}}`

**Email Content:**
```html
<h2>New Contact Form Submission</h2>

<p><strong>Name:</strong> {{from_name}}</p>
<p><strong>Email:</strong> {{from_email}}</p>
<p><strong>Subject:</strong> {{subject}}</p>

<h3>Message:</h3>
<p>{{message}}</p>

<hr>
<p><em>This message was sent from your portfolio contact form.</em></p>
```

4. Save the template and note down the **Template ID** (e.g., `template_xyz789`)

### 4. Get Public Key
1. Go to "Account" → "API Keys"
2. Copy your **Public Key** (e.g., `user_def456`)

### 5. Update JavaScript Code
Replace the placeholders in `js/main.js`:

```javascript
// Replace these values:
emailjs.init("YOUR_PUBLIC_KEY"); // Your actual public key
emailjs.send('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', templateParams) // Your actual IDs
```

**Example:**
```javascript
emailjs.init("user_def456");
emailjs.send('service_abc123', 'template_xyz789', templateParams)
```

## 📧 Email Template Variables

The contact form sends these variables to your email template:
- `{{from_name}}` - Visitor's name
- `{{from_email}}` - Visitor's email
- `{{subject}}` - Message subject
- `{{message}}` - Message content
- `{{to_email}}` - Your email (as8759111@gmail.com)

## 🔧 Features Included

✅ **Form Validation** - Checks for required fields and valid email
✅ **Loading State** - Shows spinner while sending
✅ **Success/Error Messages** - Clear feedback to users
✅ **Auto-reset** - Form clears after successful submission
✅ **Responsive Design** - Works on all devices

## 🎯 How It Works

1. **Visitor fills form** → Form validates input
2. **Clicks Send** → Shows loading spinner
3. **EmailJS sends email** → To your Gmail (as8759111@gmail.com)
4. **Success message** → Form resets, shows confirmation
5. **You receive email** → With visitor's contact details

## 🆓 Free Plan Limits

- **200 emails per month** (free)
- **2 email templates** (free)
- **1 email service** (free)

## 🚨 Troubleshooting

**Form not sending emails:**
1. Check browser console for errors
2. Verify EmailJS keys are correct
3. Ensure Gmail service is connected
4. Check email template variables

**Emails not received:**
1. Check spam folder
2. Verify Gmail connection in EmailJS
3. Test with EmailJS dashboard

## 📱 Testing

1. Fill out the contact form on your portfolio
2. Submit with test data
3. Check your email (as8759111@gmail.com)
4. Verify all information is received correctly

## 🔒 Security Notes

- Public key is safe to expose in frontend code
- EmailJS handles email sending securely
- No sensitive data stored on your server
- All communication is encrypted

---

**Need Help?** Check EmailJS documentation or contact their support team.
