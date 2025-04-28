# Postmark Plugin User Guide

## Overview

The Postmark plugin for Dify allows you to send emails using the Postmark API directly from your Dify applications. This guide will help you set up and use the plugin effectively.

## Prerequisites

- A Dify account (cloud or self-hosted)
- A Postmark account with API access
- At least one verified sender signature in your Postmark account

## Setup

### 1. Get Your Postmark API Token

1. Log in to your [Postmark account](https://account.postmarkapp.com/)
2. Navigate to the **Servers** tab
3. Select your server or create a new one
4. Find the **API Tokens** section
5. Copy your **Server API Token**

### 2. Verify Sender Signatures

Before you can send emails through Postmark, you need to verify the email addresses you'll be sending from:

1. In your Postmark account, go to **Sender Signatures**
2. Click **Add Domain** or **Add Sender**
3. Follow the verification process

### 3. Install the Plugin in Dify

1. In your Dify dashboard, go to **Plugins**
2. Search for "Postmark" or upload the plugin package
3. Click **Install**

### 4. Configure the Plugin

1. After installation, you'll be prompted to configure the plugin
2. Enter your **Server Token** from Postmark
3. Enter a **Default From Email** (must be a verified sender in your Postmark account)
4. Click **Save**

## Using the Plugin

### Basic Email Sending

The plugin provides a single tool: **Send Email**

#### Required Parameters

- **to_email**: The recipient's email address
- **subject**: The subject line of the email
- **html_body**: The HTML content of the email

#### Optional Parameters

- **cc**: Carbon copy recipients (comma-separated)
- **bcc**: Blind carbon copy recipients (comma-separated)

Note: The sender's email address (From) is automatically set to the default from email configured in the plugin credentials.

### Example Prompts

#### Basic Email

```
Send an email to john@example.com with the subject "Meeting Reminder" and the HTML body "<p>Don't forget our meeting tomorrow at 2pm.</p>"
```

#### HTML Email with Formatting

```
Send an email to customer@example.com with the subject "Your Order Confirmation" and the HTML body "<h1>Thank you for your order!</h1><p>Your order #12345 has been confirmed.</p>"
```

#### Email with CC and BCC

```
Send an email to team@example.com with the subject "Project Update" and the HTML body "<p>The project is on track for completion next week.</p>" CC manager@example.com and BCC director@example.com
```

## Troubleshooting

### Common Issues

#### Authentication Error

**Error Message**: "The server token you provided is invalid."

**Solution**: Double-check your Postmark server token and make sure it has the correct permissions.

#### Sender Not Verified

**Error Message**: "The 'From' address you supplied is not a verified sender signature."

**Solution**: Verify the sender email address in your Postmark account or use a different verified sender.

#### Missing Required Fields

**Error Message**: "To email is required" or "Subject is required" or "HTML body is required"

**Solution**: Make sure all required parameters are provided in your prompt.

## Best Practices

1. **Set a Default From Email**: Configure a default sender in the plugin settings
2. **Use HTML for Rich Content**: Create well-formatted emails with HTML
3. **Test Before Production**: Always test your email sending functionality in a development environment before using it in production

## Support

If you encounter any issues with the Postmark plugin, please contact the plugin author or submit an issue on the plugin's repository.