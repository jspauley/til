# Post A Message To A Channel

Many Slack Bots are only responding to a certain event happening (a mention, a /command, etc). This is a simple example of how to post a message from an app to a Slack channel in Python using the Slack Bolt Client and Block Kit.

```python
channel_id = 'SLACK_CHANNEL_ID'
user_id = 'BOT_USER_ID'

sender = 'Name'
message = 'Test Message'

slack.client.chat_postMessage(
    channel=channel_id,
    username=user_id,
    blocks=[
        {
            "type": "section",
            "text": {
                "type": "mrkdwn",
                "text": "*Hello There*" + str(sender)
            },
        },
        {
            "type": "section",
            "text": {
                "type": "plain_text",
                "text": str(message)
            },
        }
    ],
    text=message
)
```

Notice we also include the `text` argument. This is recommended as a fallback
should rendering the Block Kit blocks fail.
