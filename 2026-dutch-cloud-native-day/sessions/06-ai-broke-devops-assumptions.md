# AI Broke Your DevOps Assumptions: Privacy, IP and $40k Idle GPUs

- **Speaker:** Dimitris Karakasilis
- **Time / room:** 12:25–12:55, Mission 1
- **Agenda:** [Agenda](https://www.dutchcloudnativeday.nl/agenda/)

## Key takeaways (from my photos)
- The patch clock has collapsed at both ends. An exploit can be ready in about an hour, sometimes before the patch exists. Median figures shown: 38 days until fully fixed versus 5 days until exploited.
- The assumption "our data and models live in a datacenter we control" no longer holds. 34% of datacenter operators run most of their AI inference in colocation, and 26% of employees uploaded sensitive data to hosted AI tools.
- Idle GPUs are costly. A $40,000 GPU works out to about $1.52 per hour, or roughly $1,900 a year spent while it sits idle. Average GPU utilisation in enterprise Kubernetes clusters is 5%.
- What we need instead: patch every machine within days, protect data on hardware we don't control (at rest and in use), and use idle hardware for other work.
- Tooling shown:
  - Immutable, image-based OSes: Bottlerocket, Fedora CoreOS, Flatcar, Kairos, Talos.
  - Rollout: Argo CD, Flux and others.
  - Hardware trust: dm-verity, LUKS+TPM, Secure Boot, TPM measured boot.
  - Confidential computing: AMD SEV-SNP, Intel TDX, confidential containers.
- What immutable systems ask of you: a pipeline that builds and tests OS images, a reboot for every change, and debugging without editing the host.

![Exploit timeline](../images/06-devops-assumptions-exploit-timeline.jpg)
![GPU utilisation](../images/06-devops-assumptions-gpu-utilisation.jpg)
![Immutable tooling](../images/06-devops-assumptions-immutable-tooling.jpg)

## Worth exploring
- Kairos: https://kairos.io (source: https://github.com/kairos-io/kairos)
- Talos Linux: https://www.talos.dev
