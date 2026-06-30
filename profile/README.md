## Hi there 👋

> A community-minded collective making **AppSec and ASPM easier for
> developers** — by integrating the best open-source security tools and giving
> back to the people who build them.

This is the *why* behind everything under **kubeek-sec**. Not a product page —
a statement of what we believe and how we work.

We build for the love of the craft. **No commercial goal, no upsell, no "open
core" with the good parts behind a paywall.** The point is to make security a
little less painful for the developers who have to live with it, and to give
back to the open-source community that makes any of this possible.

---

## What we're trying to do

Modern application security is not short on *tools*. It is short on *coherence*.

A serious look at a single codebase can touch a dozen scanners — SAST, SCA,
secrets, IaC, license, malware, DAST, CI/CD — and every one of them has its own
CLI, its own flags, its own output shape, its own idea of what "severity" means,
and its own way of being installed and kept current. Stitching them together is
a tax every team pays again from scratch, and it's a tax that lands hardest on
the developers who just want to ship safe code.

So our mission is deliberately unglamorous:

**Take the best open-source security tools, make them easy to run, make them all
speak the same language, and give the result back to the community.**

That's it. We don't think the world needs another proprietary scanning engine.
It needs the existing ones to be *easier to adopt, easier to trust, and easier
to build on*.

## AppSec and ASPM, made easier

Two ideas guide the work:

- **AppSec** — finding and fixing security issues *in the code and its
  pipeline*, as early and with as little friction as possible. Security that
  shows up where developers already work, instead of as a gate at the end.
- **ASPM** (Application Security Posture Management) — stepping back from a
  single repo to see security across a whole estate: what's exposed, where the
  posture is improving or slipping, and what to fix *first*.

The hard part of both isn't any single scanner — it's the glue. So that's what we
focus on: **standardize the output, standardize the install, standardize the way
in.** When every tool emits the same normalized finding and renders to the same
formats, the dozen-tool tax collapses into a single, predictable workflow — and
posture across an estate becomes something you can actually measure instead of
guess.

## What we believe

A few principles that show up across everything we build:

- **Standardize, don't reinvent.** The detection engines below are the product of
  years of work by others. Our job is to integrate and normalize them, not to
  compete with them. We normalize *to* the standards the ecosystem already agreed
  on — like [SARIF](https://sarifweb.azurewebsites.net/) — instead of inventing a
  private format nobody else reads.
- **Lower the barrier for developers.** Security tooling that's hard to install,
  hard to run, or noisy to read doesn't get used. Less friction beats more
  features.
- **Trustworthy by construction.** A security tool you can't trust is worse than
  none. Tools are pinned and checksum-verified before they run; untrusted code is
  executed with least privilege; nothing silently disappears — a missing tool is
  reported, never skipped in the dark.
- **Deterministic first, AI optional.** The core has to give the same answer
  twice and work with no network and no API key. AI is a convenience for triage
  and prioritization — opt-in, read-only — never a dependency.
- **Auditable by design.** Rule sets and knowledge bases are kept small and
  readable on purpose. If you can't audit it, it's just a different kind of risk.
- **Privacy by default.** We don't phone home with your code. Any telemetry is
  off unless you opt in, and even then it's low-cardinality aggregates only —
  never paths, file contents, or secrets.
- **Open, because trust is.** A security tool you can read is a security tool you
  can trust. Everything is open source (**Apache-2.0**), so the standardization
  is something anyone can build on.

## Standing on the shoulders of the community

Most of what we ship is **glue and good manners** around tools other people
built and maintain. The hard parts — the detection engines, the rule sets, the
years of tuning — are theirs. Our job is to install them safely, run them
consistently, and translate their output into one shared language.

Credit where it's due. The open-source projects this work builds on, each under
its own upstream license:

| Family | Project | Upstream |
|---|---|---|
| SAST | **Opengrep** | <https://github.com/opengrep/opengrep> |
| SAST | **CodeQL** | <https://github.com/github/codeql-cli-binaries> |
| SCA | **Trivy** | <https://github.com/aquasecurity/trivy> |
| SCA | **OSV-Scanner** | <https://github.com/google/osv-scanner> |
| Secrets | **Gitleaks** | <https://github.com/gitleaks/gitleaks> |
| Secrets | **TruffleHog** | <https://github.com/trufflesecurity/trufflehog> |
| Secrets | **Nosey Parker** | <https://github.com/praetorian-inc/noseyparker> |
| Secrets | **Titus** | <https://github.com/praetorian-inc/titus> |
| Secrets | **BetterLeaks** | <https://github.com/betterleaks/betterleaks> |
| Secrets | **Kingfisher** | <https://github.com/mongodb/kingfisher> |
| IaC | **Checkov** | <https://github.com/bridgecrewio/checkov> |
| Malware | **ClamAV** | <https://www.clamav.net> |
| Malware | **YARA** | <https://github.com/VirusTotal/yara> |
| DAST | **Nuclei** | <https://github.com/projectdiscovery/nuclei> |
| DAST | **OWASP ZAP** | <https://www.zaproxy.org> |
| CI/CD | **Plumber** | <https://github.com/getplumber/plumber> |

And the broader shoulders: [SARIF](https://sarifweb.azurewebsites.net/) as the
interchange standard, [tree-sitter](https://tree-sitter.github.io/tree-sitter/)
and [NetworkX](https://networkx.org) for code-graph analysis, and the many rule
sets the security community publishes openly.

If you maintain one of these projects and want an integration changed, pinned
differently, or removed — just ask. We'll make it right.

## What "giving back" means here

Open source isn't a license file to us, it's the whole point:

- **Upstream first.** A bug in a scanner's *detection* belongs upstream — we'll
  help file it. A bug in how *we* install or run a tool is ours to fix.
- **A reusable normalization layer.** If all you want is "many scanners → one
  standard report," take that and run with it. That's a feature, not a leak.
- **Measurable, honest detection.** We test against deliberately-vulnerable
  targets with published ground truth, so quality is something you can verify
  instead of take on faith.
- **Documentation that explains the *why*, not just the *what*** — so the next
  person doesn't have to reverse-engineer the design to improve it.

## Get involved

This is meant to be a place for **technical exchange**, so the door is open:

- **Use it, and tell us where it's wrong.** Disagreement about how a finding
  *should* be modeled is exactly the conversation we want to have.
- **Improve a normalization, a rule set, or a severity mapping**, or just make a
  report read better.
- **Help us integrate another great open-source tool** — the more the ecosystem
  speaks one language, the better for everyone.
- **Share what you learned.** Patterns, pitfalls, a better way to do something —
  that exchange is the reason this is open in the first place.

One ground rule, because this is security: **no malicious or destructive code,
ever.** Proof-of-concept and remediation examples must be harmless.

---

*kubeek-sec is non-commercial, community-first, and Apache-2.0. It's a labor of
love and an invitation — use it, break it, improve it, and tell us what you
learned.*
