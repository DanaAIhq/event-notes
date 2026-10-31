# No Token Budget: What Breaks When Agentic Software Factories Run on Kubernetes

- **Speaker:** Alex Kotliarskyi (https://frantic.im/)
- **Time / room:** 11:45–12:15, Progress
- **Agenda:** [Agenda](https://www.dutchcloudnativeday.nl/agenda/)

## Key takeaways (from my photos)
- Scale: about 100M tokens per minute was the peak sustained rate of agents running on the same codebase.
- The setup went through stages. "CodexMan" was a single chief-of-staff thread coordinating workers on stateful compute. The third attempt was an agentic system that applies real software engineering, with a mindset shift from coding to operations.
- Principles: agents write, review and ship code; treat the system as continuously evolving; reflection and self-improvement; token indifference. One section was titled "Rust and the art of not looking at the code".
- A hermetic system: self-contained dependencies (OCI registry, observability stack), built in under 2 minutes, working on its own and giving runtime signals. It runs on an actor runtime with a control plane and host plane (NATS/JetStream, TiDB, ClickHouse, WASM, JuiceFS).
- Single Problem Optimization uses a grader loop: problem → agents propose solutions → a grader approves or declines. *Finite* objectives (solve, create, fix) differ from *infinite* ones (keep production error-free, optimise performance, reduce code entropy). Deployment is graded against a baseline.
- Lessons learned:
  - Basics are the best ROI: isolated hermetic environments, a fast feedback loop, and better developer experience leading to better agent experience.
  - Treat agents as developers by giving them tools, permissions, objectives and feedback.
  - Split "brains" from "hands".
  - Fight entropy, and prefer consistency over optimal solutions.
  - Agents adapt to humans faster than humans adapt to agents.

![Actor runtime](../images/05-no-token-budget-actor-runtime.jpg)
![Grader loop (SPO)](../images/05-no-token-budget-grader-loop.jpg)
![Basics are the best ROI](../images/05-no-token-budget-basics-roi.jpg)
