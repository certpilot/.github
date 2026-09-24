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

At 47 days, ten thousand certificates renewed on their last day need **over 200
renewals a day**, continuously, and nearer 320 when each is renewed with a third
of its life left. Anything with a human in the loop stops working well before
then.

### What it is for

Issuing a certificate is a solved problem, and open-source tools like certbot,
lego, cert-manager and step-ca solve it well. CertPilot is aimed at the view
across all of them: what you already have, where it is installed, whether it
complies with your policy, and getting a renewed certificate onto the machine
that serves it. Commercial certificate lifecycle platforms do much of this too;
[how CertPilot compares](https://certpilot.github.io/certpilot-docs/comparison)
says where, from their own documentation.

CertPilot watches **authorities first and certificates second**, because an
expiring issuing CA takes down everything it ever signed and no amount of
certificate automation helps once that has happened.

### Evaluating it

Start with the [evaluation](https://certpilot.github.io/certpilot-docs/evaluation):
a released stack in about twenty seconds, one certificate issued and renewed, and
a list of what the evaluation cannot show you. Then read
[how it compares](https://certpilot.github.io/certpilot-docs/comparison) with
Keyfactor Command, Next-Generation Trust Security and DigiCert Trust Lifecycle
Manager, including when one of them fits better.

### Repositories

| | |
|:--|:--|
| **[certpilot](https://github.com/certpilot/certpilot)** | The control plane and the console |
| **[certpilot-agent](https://github.com/certpilot/certpilot-agent)** | The host agent. Generates keys on the host and installs certificates where the server reads them |
| **[certpilot-gateway-acme](https://github.com/certpilot/certpilot-gateway-acme)**, **[-vault](https://github.com/certpilot/certpilot-gateway-vault)**, **[-selfsigned](https://github.com/certpilot/certpilot-gateway-selfsigned)** | One gateway per kind of CA, each with its own release |
| **[certpilot-gateway-sdk](https://github.com/certpilot/certpilot-gateway-sdk)**, **[certpilot-agent-sdk](https://github.com/certpilot/certpilot-agent-sdk)** | The two published contracts, for writing a gateway or an agent of your own |
| **[certpilot-docs](https://github.com/certpilot/certpilot-docs)** | The [documentation site](https://certpilot.github.io/certpilot-docs/): the evaluation, walkthroughs, guides, and an API reference generated from the router |

### Status

**Early development. Not production ready.**

Everything marked ✅ in the
[implementation status](https://github.com/certpilot/certpilot/blob/main/docs/status.md)
has been run end to end against real certificate authorities, a real database
and real servers. Everything marked 🧪 is built but has only ever met a fake.
Anything not listed does not exist. The status page and the
[roadmap](https://github.com/certpilot/certpilot/blob/main/ROADMAP.md) are kept
honest rather than aspirational, and both say plainly what does not work yet.

### Helping

The most useful contribution right now is running this against a real
certificate authority and reporting what breaks.

After that, the [open issues](https://github.com/certpilot/certpilot/issues) are
filed with the reasoning attached rather than as one-line tickets. Writing a
gateway for a CA that does not have one yet, starting with Microsoft AD CS, is
the best-isolated work in the project.

<p align="center"><sub>Apache 2.0 · self-hosted · no paid tier</sub></p>
