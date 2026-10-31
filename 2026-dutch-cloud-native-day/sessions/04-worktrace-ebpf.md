# Worktrace: Real-Time Threat Detection for Kubernetes Workspaces Using eBPF

- **Speakers:** Tomas Vitvar, Jan Hlaváč
- **Time / room:** 11:05–11:35, Mission 1
- **Agenda:** [Agenda](https://www.dutchcloudnativeday.nl/agenda/)

## Key takeaways (from my photos)
- Privilege levels for workspace containers go from standard up to privileged Podman. The guiding rule: "as little as possible, as much as the workspace workload needs".
- Workspace containers run, but escapes stop. Tetragon eBPF probes detect use of host namespaces, and the k8shell API server then stops the whole workspace at once.
- Architecture: detection rules (ConfigMap/YAML) drive one controller, which feeds a detector on every node. Results go to a provisioner (stop the workspace) and to storage.
- Three detection pipelines run on one stream of Tetragon events. *Direct* uses YAML rules on process, file or syscall. *Correlation* finds steps of an attack path within a sliding time window. *Behavioral* compares against a baseline of binaries, paths and syscalls per node.
- Coverage: 57 attacks, 145 rules and 37 attack paths in 10 categories, tested with real attack scenarios mapped to MITRE ATT&CK techniques.
- The project is open source (AGPL) under the k8shell-io GitHub organisation.

![Worktrace architecture](../images/04-worktrace-architecture.jpg)
![Worktrace coverage](../images/04-worktrace-coverage.jpg)

## Worth exploring
- k8shell on GitHub: https://github.com/k8shell-io
- Tetragon: https://tetragon.io
