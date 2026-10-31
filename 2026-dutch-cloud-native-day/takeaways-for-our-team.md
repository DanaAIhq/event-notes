# Takeaways for our team

*These are suggestions based on my notes, not decisions.*

1. **Pilot argocd-diff-preview** on one GitOps repo so reviewers see rendered manifests instead of raw values changes. Start with an ephemeral cluster, then add Kyverno checks on the rendered output.
2. **Define a sandbox pattern for coding agents**, modelled on RTL's: a fresh pod per task, default-deny network with an egress allowlist, read-only credentials, short lifetime. A human still approves every merge.
3. **Treat agents as platform users.** Ask what tools, permissions, feedback loops and fast hermetic environments they need, the same things that help developers.
4. **Measure GPU utilisation** on any GPU nodes we run or plan, before buying or renting more capacity.
5. **Review our patch lead time** against the shrinking exploit window, and evaluate immutable, image-based node OSes (Kairos, Talos, Flatcar) with A/B upgrades.
6. **Look at OpenTelemetry + OpenFeature** as the base for automated "reflex" decisions (progressive delivery, incident mitigation), with permissions and audit defined up front.
7. **Explore eBPF runtime detection** (Tetragon) for shared or privileged workloads.
8. **Track EU sovereignty** requirements when choosing where data and inference run.
