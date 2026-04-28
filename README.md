# unKover

> *Uncover what's forbidden.*

403 bypass tester by [Brute Logic](https://brutelogic.net).

Part of the **King of Noobs** suite — offensive recon tools built on KISS and the Pareto principle. Simple, fast, and effective.

---

## What It Does

unKover tests a URL returning 403 Forbidden against a set of proven bypass techniques and stops at the first successful one, returning a ready-to-run curl PoC.

Techniques include IP header spoofing, method tampering, protocol headers, path normalization, URL encoding, HTTP/1.0 downgrade, hop-by-hop headers, path suffix injection, and API version prefix bypass.

---

## Why Bash?

No runtime. No pip install. No npm. No supply chain risk.

Bash and curl are already on every Linux system. The script is short, readable, and auditable by anyone in seconds. That's not a limitation — that's the point.

---

## Usage

```bash
bash unkover <URL> [-j|--json] [--prefix /v2]
```

### Arguments

- `URL` — Target URL returning 403 (required)
- `--prefix` — Additional path prefix to test (optional). Some servers protect `/admin` but not `/v2/admin` or `/api/admin`. Provide whatever prefix is relevant to the target.
- `-j|--json` — Output results in JSON format

### Examples

```bash
bash unkover https://target.com/admin
bash unkover https://target.com/admin --prefix /v2
bash unkover https://target.com/admin -j | jq
```

---

## Output

Shows which technique is being tested in real time. On bypass found, outputs technique name, PoC curl command, and result status and size. On no bypass, reports cleanly.

Use `-j` for JSON output with metadata including tool version, timestamp, elapsed time, findings, and baseline.

---

## Testbed

Test unKover against a live target built specifically for this tool:

**https://403.brutelogic.net/access**

Multiple server configurations (nginx, Apache) with different bypass vectors.

---

## 👑 King of Noobs

*We are all eternal noobs.*

This project was born from a simple truth: no matter how deep we go into security, we remain eternal noobs. There is always more to learn, and humility is our greatest advantage.

*"King of Noobs"* was originally thrown at me on X as an insult — because I kept sharing things in the simplest possible way, following KISS and the Pareto principle, instead of gatekeeping behind complexity.

I decided to wear the crown.

Not because I claim to be the best, but because the real elite are those who never stop being students. The ones who stay humble, build useful things, and help others level up without ego.

That's what King of Noobs is about.

### KISS

Originally "Keep It Simple, Stupid!" — used here as **Keep It Simple and Short**. Another K, intentional. The tools are short by design. Short means readable. Readable means auditable. Auditable means trustworthy.

### The K

The **K** in every tool name is the crown. Always uppercase. Always there.

| Tool | Purpose |
|------|---------|
| **reKon** | Master orchestrator — runs the full recon pipeline |
| **disKovery** | Subdomain discovery |
| **reKover** | URL mapping (passive + brute + crawl) |
| **unKover** | 403 bypass / access control evasion |

---

*A [Brute Logic](https://brutelogic.net) project.*

---

## License

MIT
