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
  
3. Create a Lambda Function:

Encryption:
To encrypt your secrets use the following steps:

  1. Create or use an existing KMS Key - http://docs.aws.amazon.com/kms/latest/developerguide/create-keys.html

  2. Click the "Enable Encryption Helpers" checkbox

  3. Paste <SLACK_CHANNEL> into the slackChannel environment variable

  Note: The Slack channel does not contain private info, so do NOT click encrypt

  4. Paste <SLACK_HOOK_URL> into the kmsEncryptedHookUrl environment variable and click encrypt

  Note: You must exclude the protocol from the URL (e.g. "hooks.slack.com/services/abc123").

  5. Give your function's role permission for the kms:Decrypt action.

     Example:

{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "Stmt1443036478000",
            "Effect": "Allow",
            "Action": [
                "kms:Decrypt"
            ],
            "Resource": [
                "<your KMS key ARN>"
            ]
        }
    ]
}
'''
