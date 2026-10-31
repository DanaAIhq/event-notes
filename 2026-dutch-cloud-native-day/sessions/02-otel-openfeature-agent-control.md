# Two Standards Walk Into an Agent: Runtime Agent Control with OpenTelemetry and OpenFeature

- **Speaker:** Simon Schrottner
- **Time / room:** 10:10–10:25, Progress
- **Agenda:** [Agenda](https://www.dutchcloudnativeday.nl/agenda/)

## Key takeaways (from my photos)
- Agent control as a loop: OpenTelemetry *senses*, an agent watches, decides and sets a flag, and OpenFeature is the *muscle*.
- Candidate areas: incident response, progressive delivery, capacity and cost, policy enforcement. The question asked was "which decisions can safely become reflexes?"
- "The boundary must be portable." The wires are increasingly shared (MCP, A2A, Open Responses), while the rules (permissions, guardrails, audit) are still trapped in individual products.
- "OpenTelemetry and OpenFeature happened at the same table. This one can too." This was a call for a shared standard for agent control.

![OpenTelemetry senses, OpenFeature acts](../images/02-otel-openfeature-senses-muscles.jpg)
![The boundary must be portable](../images/02-otel-openfeature-portable-boundary.jpg)

## Worth exploring
- OpenTelemetry: https://opentelemetry.io
- OpenFeature: https://openfeature.dev
- Model Context Protocol: https://modelcontextprotocol.io
- A2A protocol: https://a2a-protocol.org
