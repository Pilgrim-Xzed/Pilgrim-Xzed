<div align="center">

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&height=220&color=0:0f172a,50:155e75,100:0ea5e9&text=Saidu%20Bello&fontColor=f8fafc&fontSize=64&fontAlignY=38&animation=fadeIn&desc=Platform%20%C2%B7%20DevOps%20%C2%B7%20Systems%20Engineering&descSize=20&descAlignY=58" alt="Saidu Bello — Platform · DevOps · Systems Engineering"/>

<a href="https://github.com/Pilgrim-Xzed"><img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=22&duration=3000&pause=900&color=0EA5E9&center=true&vCenter=true&width=700&lines=I+build+the+infrastructure+AI+agents+run+on;Kubernetes+%C2%B7+Terraform+%C2%B7+Rust+%C2%B7+TypeScript+%C2%B7+Go;GitOps+everything+%C2%B7+Keyless+CI+%C2%B7+Zero-trust+by+default;Intel+TDX+confidential+computing%2C+in+production" alt="Typing intro"/></a>

<p>
<a href="https://orgn.com"><img src="https://img.shields.io/badge/Building-orgn.com-0ea5e9?style=flat-square&logo=googlechrome&logoColor=white" alt="orgn.com"/></a>
<a href="https://x.com/the_Pilgrim001"><img src="https://img.shields.io/badge/@the__Pilgrim001-000000?style=flat-square&logo=x&logoColor=white" alt="X"/></a>
<img src="https://komarev.com/ghpvc/?username=Pilgrim-Xzed&style=flat-square&color=0ea5e9" alt="Profile views"/>
</p>

</div>

## 🛰️ About

I'm **Saidu** — a platform engineer who owns the whole path from `terraform plan` to production traffic.

I'm a founding engineer at **[ORGN](https://orgn.com)**, where we build a confidential-compute platform for AI development: hardware-isolated agent sandboxes on **Intel TDX**, an LLM gateway spanning **220+ models**, and the identity, billing, and observability planes that turn all of it into a product rather than a demo.

Nearly all of my work ships in **private org repos** — so instead of green squares, here are the receipts.

## 🧾 Receipts, not vibes

### ☸️ Kubernetes & GitOps — the daily driver
- Operate a **multi-cloud fleet of production clusters** — GKE (Standard + Autopilot) and DigitalOcean — reconciled by **Argo CD app-of-apps**, hub-and-spoke, with phased onboarding and CI-validated RBAC
- Scaled a Coder-based cloud development platform toward **1,000 concurrent developer workspaces**: quota math, warm node pools, DERP/WireGuard networking, auto-stop cost policies
- Executed a **zero-downtime blue-green migration** of a live OAuth identity provider (DigitalOcean + Neon → GKE + Cloud SQL), then decommissioned the old stack
- I root-cause the fun ones: Cloud NAT no-loopback silently killing cache invalidation, WireGuard MTU/conntrack resets against the K8s API, HPA-vs-GitOps self-heal fights

### 🏗️ Terraform & multi-cloud IaC
- **~20k lines of production HCL** across **GCP, DigitalOcean, and Alibaba Cloud**, plus Cloudflare zero-trust access
- Policy-as-code with **OPA/Rego** gates that understand plan semantics — block standalone deletes, allow-and-warn on replacements
- **Keyless CI/CD everywhere**: GitHub Actions → OIDC / Workload Identity Federation, zero long-lived cloud credentials
- Apply pipelines where the applied plan is **byte-identical to the reviewed one** — concurrency fencing, run-attempt rejection, explicit destroy attestation

### 🔐 Security & identity engineering
- Built and operate an **OAuth 2.1 / OIDC authorization server** powering SSO for a product suite — passkeys, org/team RBAC, metered Stripe billing, GitOps-delivered to GKE
- Zero-trust access architecture: **WireGuard + Teleport** identity-aware proxy with session recording and SOC2-oriented audit trails
- Led **external security-assessment remediation end-to-end** across four production services — every fix paired with a regression test, shipped through the same gated CI as feature work
- Details matter: hand-rolled IPv4/IPv6 CIDR trust-chain matching to fix a real rate-limit incident; capability-token git-credential delivery where secrets are returned once and stored only hashed

### 🛡️ Confidential computing
- **Intel TDX in production**: confidential GKE node pools, taint-isolated, scale-to-zero
- Designed and wrote a **per-sandbox remote-attestation service in Go** — node-local broker DaemonSet, public verification gateway, MRTD/RTMR quote decoding
- Extended **Trigger.dev** (internal fork) so every background-job run carries a hardware attestation bound to `SHA-512(runId:attempt)`
- Ship TEE-routed inference across **Intel SGX, Intel TDX, and NVIDIA Confidential Computing** providers

### 🦀 Rust & systems
- Billing engine for a high-throughput LLM gateway that stays **correct under stream cancellation** — Drop guards, reservation tokens, dark-launch rollout behind flags, thoroughly unit-tested
- **microVM networking**: added raw-socket modes (Linux TAP / macOS vmnet) to a libkrun-based sandbox so security tooling gets real L3 without privileged containers
- Distroless **axum** inference gateway behind Kubernetes Gateway API, tuned for hour-long SSE streams

### 🤖 AI / agent infrastructure
- LLM gateway routing **220+ models across 4 providers** — metering, spend caps, subscription rate-limit windows
- **Production remote MCP servers**: Streamable HTTP transport done right, plus a full OAuth 2.1 + PKCE authorization proxy so AI agents authenticate like first-class clients
- Sandbox orchestration at every layer: Daytona, E2B, libkrun microVMs, per-sandbox WireGuard egress isolation
- Founded and gatekeep a **~630k-LOC AI development platform monorepo** — 1,400+ of my commits, 15+ engineers, and the merge button is mine

### 📊 Observability & FinOps
- Prometheus · Grafana · Loki · Tempo · OpenTelemetry as defaults; **ClickHouse** for telemetry at volume; three-zone Grafana HA
- Live migration from ClickHouse Cloud to self-hosted on GKE — automated DDL rewriting, materialized-view-aware ordering, verified read-back
- Identified and executed **50%+ infrastructure cost reductions**: right-sizing, load-balancer consolidation, scale-to-zero pools, workspace auto-stop

## 🛠️ Stack

<div align="center">

<img src="https://skillicons.dev/icons?i=kubernetes,docker,terraform,gcp,cloudflare,githubactions,gitlab,prometheus,grafana,nginx,linux,bash&perline=12" alt="Infrastructure tools"/>
<br/>
<img src="https://skillicons.dev/icons?i=rust,go,ts,nodejs,deno,bun,react,nextjs,remix,postgres,redis,kafka&perline=12" alt="Languages and frameworks"/>

<p>
<img src="https://img.shields.io/badge/Argo%20CD-EF7B4D?style=flat-square&logo=argo&logoColor=white" alt="Argo CD"/>
<img src="https://img.shields.io/badge/Helm-0F1689?style=flat-square&logo=helm&logoColor=white" alt="Helm"/>
<img src="https://img.shields.io/badge/DigitalOcean-0080FF?style=flat-square&logo=digitalocean&logoColor=white" alt="DigitalOcean"/>
<img src="https://img.shields.io/badge/Alibaba%20Cloud-FF6A00?style=flat-square&logo=alibabacloud&logoColor=white" alt="Alibaba Cloud"/>
<img src="https://img.shields.io/badge/ClickHouse-FFCC01?style=flat-square&logo=clickhouse&logoColor=black" alt="ClickHouse"/>
<img src="https://img.shields.io/badge/OpenTelemetry-000000?style=flat-square&logo=opentelemetry&logoColor=white" alt="OpenTelemetry"/>
<img src="https://img.shields.io/badge/Vault-FFEC6E?style=flat-square&logo=vault&logoColor=black" alt="Vault"/>
<img src="https://img.shields.io/badge/Teleport-512FC9?style=flat-square&logo=teleport&logoColor=white" alt="Teleport"/>
<img src="https://img.shields.io/badge/WireGuard-88171A?style=flat-square&logo=wireguard&logoColor=white" alt="WireGuard"/>
<img src="https://img.shields.io/badge/OPA%20Rego-7D9199?style=flat-square&logo=openpolicyagent&logoColor=white" alt="OPA"/>
<img src="https://img.shields.io/badge/Spacelift-131A2C?style=flat-square" alt="Spacelift"/>
<img src="https://img.shields.io/badge/MCP-000000?style=flat-square&logo=modelcontextprotocol&logoColor=white" alt="Model Context Protocol"/>
</p>

</div>

## ⚙️ How I work

- **GitOps everything** — if it isn't in git and reconciled, it doesn't exist
- **Keyless by default** — OIDC federation over exported credentials, every time
- **Tests as receipts** — security fixes, billing paths, and migrations all land with regression tests
- **Write it down** — migration plans, threat models, and runbooks before the change, honest postmortem notes after
- **Fail-open vs fail-closed is a decision, not an accident** — and it's documented at the call site

## 📈 GitHub numbers

> Most of my contributions live in private organization repos — the graphs below undercount by design.

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-stats.vercel.app/api?username=Pilgrim-Xzed&show_icons=true&count_private=true&include_all_commits=true&hide_border=true&theme=github_dark&bg_color=00000000"/>
  <img height="165" src="https://github-readme-stats.vercel.app/api?username=Pilgrim-Xzed&show_icons=true&count_private=true&include_all_commits=true&hide_border=true&bg_color=00000000" alt="GitHub stats"/>
</picture>
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://streak-stats.demolab.com?user=Pilgrim-Xzed&hide_border=true&theme=github-dark-blue&background=00000000"/>
  <img height="165" src="https://streak-stats.demolab.com?user=Pilgrim-Xzed&hide_border=true&background=00000000" alt="GitHub streak"/>
</picture>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Pilgrim-Xzed/Pilgrim-Xzed/output/github-contribution-grid-snake-dark.svg"/>
  <img width="100%" src="https://raw.githubusercontent.com/Pilgrim-Xzed/Pilgrim-Xzed/output/github-contribution-grid-snake.svg" alt="Contribution snake"/>
</picture>

</div>

## 🤝 Let's talk

If you're building something where **infrastructure is the product** — AI platforms, developer tools, confidential computing, or anything where "it works on my machine" isn't good enough — I'd love to hear about it.

<div align="center">

<a href="https://orgn.com"><img src="https://img.shields.io/badge/ORGN-orgn.com-0ea5e9?style=for-the-badge" alt="ORGN"/></a>
<a href="https://x.com/the_Pilgrim001"><img src="https://img.shields.io/badge/X-@the__Pilgrim001-000000?style=for-the-badge&logo=x" alt="X"/></a>

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&height=120&color=0:0f172a,50:155e75,100:0ea5e9&section=footer" alt=""/>

</div>
