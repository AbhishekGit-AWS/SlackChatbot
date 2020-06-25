### SlackChatbot
Using Lambda, CloudWatch and SNS.

## Steps:
# 1. Slack:

1. Create a [Slack] account: (https://slack.com/)

2. Create Incoming WebHooks:
  Incoming Webhooks are a simple way to post messages from external sources into Slack.
  They make use of normal HTTP requests with a JSON payload, which includes the message and a few other optional details.
  - Go to Apps - Incoming WebHooks - Add - Add to Slack
  - Choose #general or a channel of choice.
  - Add Incoming WebHooks integration.
  - Copy the WEbHook URL and save the settings.
  
