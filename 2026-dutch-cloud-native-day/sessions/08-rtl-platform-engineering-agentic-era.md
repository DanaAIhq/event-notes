# Platform Engineering in the Agentic Engineering Era at RTL Netherlands

- **Speaker:** Anna Kosek
- **Time / room:** 14:40–15:10, Progress
- **Agenda:** [Agenda](https://www.dutchcloudnativeday.nl/agenda/)

## Key takeaways (from my photos)
My photos end around 15:00, so the last part of the talk is not covered.
- 68% of 4,277 merged pull requests in 30 days were written by an AI agent. "Velocity is not the bottleneck anymore. Safe delivery is."
- One platform sits under every RTL product (Videoland, RTL Nieuws, Buienradar), used by developers and agents alike. The slide listed 17 teams, 15 Kubernetes clusters, 1,300 Argo CD applications and 5,349 GitOps changes in 30 days.
- Changes reach production through one path for both apps and infrastructure. The path is pull request, CI checks, review, GitOps repo, Argo CD, then AKS/EKS. OpenTofu plans cover infrastructure, Gatekeeper decides what gets in, and Grafana LGTM watches every step.
- Agents need room to break things, while production needs the opposite: every change reviewed and in Git, and rollback in one step.
- The coding-agent sandbox is a fresh pod per task with no root and a default-deny network. Git access is read-only while working, with a token scoped to push its own branch. Egress is allowlisted via Cilium or Squid, and pods are deleted after an hour at most. "The agent can break the pod, but nothing outside it."
- There is one preview environment per pull request, driven by CUE intent and an ApplicationSet PR generator.
- Agents do the first review pass and a human approves ("A human approves. Agent reviewer cannot.").
- Agent skills run as CI checks with read-only tools and no LLM secret. They are advisory first, then a finding becomes a gate.

![Agent-written PRs](../images/08-rtl-agent-written-prs.jpg)
![Inside the code sandbox](../images/08-rtl-code-sandbox.jpg)
![Review: first pass on every PR](../images/08-rtl-review-flow.jpg)

## Worth exploring
- Cilium: https://cilium.io
- CUE: https://cuelang.org
- Crossplane: https://www.crossplane.io
