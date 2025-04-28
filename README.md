# Postmark Plugin for Dify

**Author:** Harry Wang (https://harrywang.me/)  
**Version:** 0.0.1  
**Type:** Tool Plugin  

## Description

The Postmark plugin for Dify allows you to send emails using the Postmark API directly from your Dify applications. This plugin enables your AI applications to communicate with users via email, send notifications, deliver reports, and more.

## Features

- Send emails with text and/or HTML content
- Support for CC and BCC recipients
- Configurable default sender email address
- Detailed success and error messages

## Installation

1. Install the plugin in your Dify instance
2. Configure the plugin with your Postmark server token and default sender email

## Configuration

The plugin requires the following credentials:

- **Server Token**: Your Postmark server token (required)
- **Default From Email**: The default sender email address to use when no from_email is provided in the tool parameters (required)

Both the server token and the default from email must be configured for the plugin to work properly.

## Usage

The plugin provides a single tool: `Send Email`

### Parameters

- **to_email**: The recipient's email address (required)
- **subject**: The subject line of the email (required)
- **html_body**: The HTML content of the email (required)
- **cc**: Carbon copy recipients (optional)
- **bcc**: Blind carbon copy recipients (optional)

Note: The sender's email address (From) is automatically set to the default from email configured in the plugin credentials.

### Example Prompt

```
Send an email to john@example.com with the subject "Meeting Reminder" and the HTML body "<p>Don't forget our meeting tomorrow at 2pm.</p>"
```

## Requirements

- A valid Postmark account with API access
- At least one verified sender signature in your Postmark account
- Python 3.10 or higher

## Troubleshooting

- **Authentication Errors**: Make sure your server token is correct and has the necessary permissions
- **Sender Not Verified**: Ensure that the from_email address is a verified sender signature in your Postmark account
- **Missing Required Fields**: Check that all required parameters (to_email, subject, and html_body) are provided

## Support

For issues or feature requests, please contact the plugin author or submit an issue on the plugin's repository.

## License

MIT License

## Development

Quick notes for development based on https://docs.dify.ai/plugins/quick-start/develop-plugins:

```
brew tap langgenius/dify
brew install dify

dify version
dify plugin init

# get REMOTE_INSTALL_KEY from https://cloud.dify.ai/plugins
# update REMOTE_INSTALL_KEY=xxx in .env, test using the command below
python -m main

# package the plugin
cd ..
dify plugin package ./dify-postmark-plugin
```

Now you can upload the plugin file `dify-postmark-plugin.difypkg to Dify to use.

If running into issues like "plugin verification has been enabled, and the plugin you want to install has a bad signature", see https://docs.dify.ai/learn-more/faq/plugins