# A2A Customer Conversation Extension

An extension to the [Agent2Agent (A2A) protocol](https://a2a-protocol.org/) for agents that take part in **customer conversations**: support, sales, or any conversation between a business and a person over chat, email, WhatsApp or voice.

A2A defines how agents exchange messages and tasks. It does not define the conversation around them. This extension adds, through A2A's own `metadata` maps:

- **Conversation context**: the conversation id in the client's system, the customer, the channel.
- **Turn outcome**: whether the agent `answered`, `resolved` the conversation, or `needsHuman`, with a handoff note for the human who takes over.

No new RPC methods, no new task states. An extension-unaware client or agent keeps working as plain A2A.

## Versions

| Version | URI | Spec |
|---|---|---|
| v1 (draft) | `https://cloudhumans.github.io/a2a-customer-conversation-extension/v1` | [v1/index.md](v1/index.md) |

## Quick start

Declare it in your Agent Card:

```json
{
  "capabilities": {
    "extensions": [
      {
        "uri": "https://cloudhumans.github.io/a2a-customer-conversation-extension/v1",
        "required": false
      }
    ]
  }
}
```

Then read the client's conversation context from `Message.metadata` and report each turn's outcome in `Task.metadata`. The [v1 spec](v1/index.md) has the full key list and examples.

## Contributing

Issues and pull requests are welcome. Breaking changes go into a new version folder with a new URI.

## License

[Apache License 2.0](LICENSE), the same license as the A2A protocol.
