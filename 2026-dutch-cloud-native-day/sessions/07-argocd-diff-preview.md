# Stop Merging Blind: Argo CD Previews That Make a DIFFerence!

- **Speakers:** Dag Bjerre Andersen, Tibo Beijen
- **Time / room:** 14:00–14:30, Mission 1
- **Agenda:** [Agenda](https://www.dutchcloudnativeday.nl/agenda/)

## Key takeaways (from my photos)
- The starting point was Terraform. The plan → review → approve → apply habit has proven effective over many years, and the GitOps equivalent is to show the *rendered* Argo CD diff in the pull request ("What You See Is What You Get").
- How argocd-diff-preview works: a pull request triggers CI, which starts a cluster running Argo CD. Argo CD renders both branches, the tool extracts the diff, and it posts the diff as a PR comment. The demos covered an Argo CD upgrade and an ApplicationSet refactor ("no changes = perfect refactor").
- There are two cluster options. An *ephemeral* cluster is simple and fully isolated, at the cost of startup time (about 45 seconds on the slide). A *pre-configured* cluster starts instantly but is more complex to set up and secure.
- It was compared with the Argo CD Source Hydrator + GitOps Promoter. The challenges listed for that approach were workflow changes, state visibility (more branches and PRs to check) and release-cycle entanglement.
- Extended pipeline: pull both branches → argocd-diff-preview → static analysis with Kyverno on the rendered manifests → optional Renovate automerge labeler → LLM review → post a comment on the PR.

![Diff preview flow](../images/07-argocd-diff-preview-flow.jpg)
![Ephemeral vs pre-configured cluster](../images/07-argocd-diff-preview-cluster-options.jpg)
![Review pipeline](../images/07-argocd-diff-preview-pipeline.jpg)

## Worth exploring
- argocd-diff-preview: https://github.com/dag-andersen/argocd-diff-preview
- Argo CD Source Hydrator: https://argo-cd.readthedocs.io/en/stable/user-guide/source-hydrator/
- GitOps Promoter: https://github.com/argoproj-labs/gitops-promoter
- Kyverno: https://kyverno.io
