<p align="center">
  <img src="logo.png" alt="" width="96" height="96" />
</p>

<h1 align="center">CertPilot</h1>

<p align="center">
  <strong>Open-source PKI and certificate lifecycle management.</strong><br />
  Watches the CA hierarchy your organisation runs on, and every certificate
  under it, on one clock.
</p>

---

### Why now

The CA/Browser Forum has already voted the schedule through. Maximum TLS
validity falls to **200 days in March 2026, 100 days in March 2027, and 47 days
in March 2029**, with domain validation reuse dropping to 10 days alongside it.

At 47 days, ten thousand certificates is roughly **670 renewals a day**,
continuously. Anything with a human in the loop stops working well before then.

### The gap this fills

Issuing a certificate is a solved problem, and the existing tools solve it well.
What none of them do is tell you what you already have, where it is installed,
whether it complies with your policy, or get the renewed certificate onto the
machine that actually serves it.

CertPilot watches **authorities first and certificates second**, because an
expiring issuing CA takes down everything it ever signed and no amount of
certificate automation helps once that has happened.

### Repositories

| | |
|:--|:--|
| **[certpilot](https://github.com/certpilot/certpilot)** | The control plane, the gateways, the agent and the console |
| **[certpilot-docs](https://github.com/certpilot/certpilot-docs)** | The [API reference](https://certpilot.github.io/certpilot-docs/), generated from the router and the handlers so it cannot drift |

### Status

**Early development. Not production ready.**

Everything listed as built has been run end to end against real certificate
authorities, a real database and real servers. Anything not listed does not
exist. The [implementation status](https://github.com/certpilot/certpilot/blob/main/docs/status.md)
and the [roadmap](https://github.com/certpilot/certpilot/blob/main/ROADMAP.md)
are kept honest rather than aspirational — including a known-gaps section that
says plainly what does not work yet.

### Helping

The most useful contribution right now is running this against a real
certificate authority and reporting what breaks.

After that, the [open issues](https://github.com/certpilot/certpilot/issues) are
filed with the reasoning attached rather than as one-line tickets — the
container work needs somebody with a container runtime, and writing a gateway
for a CA that does not have one is the best-isolated work in the project.

<p align="center"><sub>MIT · self-hosted · no paid tier</sub></p>
