# MendOS

### MEND your Operating System. One line. Windows or Mac.

```powershell
irm 'https://mendos.heliosprima.com/win' | iex
```

```bash
/bin/bash -c "$(curl -fsSL https://mendos.heliosprima.com/mac)"
```

> *A [Helios Prima](https://heliosprima.com) product. The DNA-helix that repairs your operating system.*

---

## Why this exists

There's a moment every computer user knows. Something breaks — the audio cuts out, the WiFi won't reconnect, the printer says it's offline even though it's clearly on, Okta won't stop asking for verification — and you suddenly have to become a person you're not. You're a graphic designer. You're a parent on a video call. You're a salesperson trying to close a deal. You're a retiree video-chatting your grandkids. You didn't sign up to learn what a DNS cache is or why the print spooler service crashed.

So you call someone. Maybe it's your company's IT desk. Maybe it's your son who lives three states away. Maybe it's the 1-800 number on the back of the laptop, which routes you to a script-reading agent halfway around the world. You go on hold. When someone picks up, you try to describe a screen they can't see. They ask you to read error messages out loud. They ask you to right-click things and you don't know which right is right. Maybe they fix it. Maybe they escalate. Maybe they tell you to restart, and you do, and it doesn't help, and you have to start over.

It shouldn't be this hard. Most of what tech support does on the other end of that call is the same handful of commands, over and over: clear a cache, flush DNS, restart a service, sign out and back in, toggle a setting. They've memorized the playbook. You haven't. That's the whole gap.

**MendOS closes the gap.** It hands you the playbook in a window with buttons. You paste one line. A scanner runs. It tells you, in plain language, what's wrong. You click Fix. It fixes it. No phone call, no hold music, no ticket, no waiting.

## The name

**Mend**OS — written with **Mend** in bold and OS in light, like the helix of your operating system has two strands that need to align. When something breaks, MendOS reads the strands, finds the broken segment, and stitches it back together. Your OS isn't a black box you have to apologize to; it's a structure you can read and repair.

The name has two parts:

- **Mend** — the action. To repair, to heal, to make whole again.
- **OS** — the thing being mended. Your operating system. Your daily-driver computer. The reason you can't get your work done right now.

Pronounced *mend-OH-S*. Built by [FR4NTZ0N](https://github.com/PH30N1X-PR1Me), shipped under [Helios Prima](https://heliosprima.com).

## Who it's for

**The parent or grandparent** who calls a family member every time something goes wrong, and feels guilty about it. You shouldn't have to feel guilty. Run the one-liner, click the issue, click Fix. If it doesn't work, the tool exports a diagnostic file your tech-savvy relative can actually read.

**The student or freelancer** whose laptop is everything — coursework, income, social life, panic at 2am the night before a deadline when Chrome won't load. You're not going to wait for IT to open in the morning. You need the fix now, free, no install, no signup.

**The small business owner** running a five-person shop without a real IT team. You ARE the IT team, except you also have a business to run. Stop spending Saturday morning fixing what should be a five-minute click.

**The IT pro running help desk operations** at a real company. You know the truth: most of your tickets are the same fifty things. You don't have time for them. You have actual problems to solve. Hand your users this tool with your branding on it, and watch your ticket queue drop overnight.

## Where this came from

I work in tech support. I started as a regular agent — not the most technically inclined person on the floor — and got promoted into the technical side because I was good at staying calm with frustrated people. The job put me in a position where I had to fix things I barely understood myself, walking users through PowerShell commands to clear cache, flush DNS, reset services, while they were already stressed and short on patience.

Trying to explain *"open PowerShell as an administrator and paste this exact command"* to someone who's never seen a black window with white text before — that's a uniquely demoralizing experience for both of you. They feel stupid. You feel useless. The actual fix takes thirty seconds and the call takes thirty minutes.

I built MendOS so the people I was helping could help themselves. Then I realized the same script could help anyone, anywhere — not just the agents on my floor. So here it is, open source, free for personal use, and built to grow.

## What it does today

One paste, one window, one click per fix. Specifically:

- **Health scan** — checks 7 things on Windows / 6 on Mac in under two seconds: uptime, free disk, RAM pressure, days since last security patch, network connectivity, hibernation state, fast startup. Green / yellow / red dots tell you what's healthy and what isn't.
- **22 single-shot fixes** across **12 categories** — DNS flush, audio reset, Bluetooth restart, print spooler, Chrome/Edge cache clear, Slack/Zoom/Teams reset, Okta MFA helper, low-end performance tuning, external monitor re-detection, Outlook repair, WiFi adapter cycle, and more.
- **Search-as-you-type problem picker** — don't see your issue in the dropdown? Type "headphones," "stuck," "frozen," "won't connect" — keyword search across all 22 problems with a live match counter.
- **Audit Mode** — toggle in the header. The tool runs all checks but disables every fix button, just shows you what *would* happen. Perfect for users who want to learn what's wrong without changing anything yet.
- **Undo Last** — every fix that changes a setting gets registered with its inverse. One click reverts the last action. The undo registry persists across launches.
- **Escalate to IT** — when a fix doesn't work, click Escalate. The tool zips up your system info, recent logs, what was tried, and what failed, drops it on your Desktop, and opens an email pre-addressed to your support contact with the ZIP path on your clipboard. The hardest part of asking for help (explaining what's going on) becomes a single click.

## What's coming

This is a v1.0 release. Honest about what's still rough:

- Right now you need to paste a command into PowerShell or Terminal. That's already easier than the old workflow for many people, but **a downloadable installer (`.exe` for Windows, signed `.app` for Mac)** is on the roadmap so your less-technical relatives don't have to know what PowerShell is.
- The fix descriptions are still a little technical. **Plain-English mode** — "this clears your computer's memory of websites it visited so they load fresh next time" instead of "Remove-Item LOCALAPPDATA\Google\Chrome\Cache" — is coming.
- A **"Fix the safe stuff automatically"** big-button mode for people who don't want to read 22 issue descriptions.
- **Scheduled scans** that catch problems before you notice them.
- **Multi-language UI** — Spanish, Tagalog, Hindi, Portuguese — for global use.
- **MSP / IT-team mode** with custom branding, multi-step workflows, MDM/Group-Policy awareness, ticket system integrations (Freshdesk, Zendesk, ServiceNow).
- **Driver, battery, and thermal health** checks for laptops.
- **Browser deep-cleaners** that reset Chrome/Edge/Firefox profiles without losing bookmarks or saved logins.

If something on this list matters to you and you can help build it, **please open an issue or a PR.** This tool gets stronger every time someone adds a fix to the registry, translates a string file, or files a bug report with a real-world scenario. The code is structured to make contributing easy — adding a new fix is about 15 lines of PowerShell or bash. See [`docs/CONTRIBUTING.md`](docs/CONTRIBUTING.md).

## Two tiers

| | Light (free) | Ultimate |
|---|:---:|:---:|
| Health scan | ✅ | ✅ |
| 22 single-shot fixes | ✅ | ✅ |
| Audit mode | ✅ | ✅ |
| Undo every action | ✅ | ✅ |
| Diagnostic bundle export | ✅ | ✅ |
| Multi-step verified workflows | — | ✅ |
| Per-machine license binding | — | ✅ |
| MDM / Group Policy awareness | — | ✅ |
| Multi-language UI | — | ✅ |
| Custom branding via config.json | — | ✅ |
| ITSM integrations | — | ✅ |

Light is fully MIT-licensed and always free for personal use. Ultimate is for organizations that need workflows, branding, and integrations — pricing TBD, contact me for early access.

## For organizations

If you run a call center, a clinic, a small business, an MSP, or any operation where people spend their day on things other than computer troubleshooting — MendOS was built with you in mind too.

Drop a `config.json` into the user's profile (or push it via Group Policy / Intune / Jamf) and the tool reskins itself with your branding:

```json
{
  "client": {
    "name": "Acme Helpdesk",
    "supportContact": "ithelp@acme.example",
    "ticketSystemUrl": "https://acme.freshservice.com/support/tickets/new"
  },
  "environment": {
    "ssoProvider": "okta",
    "ssoUrl": "https://acme.okta.com",
    "managedByMdm": true
  },
  "problems": {
    "exclude": ["network.consumer-router-reset"],
    "custom": [
      { "id": "acme.crm-relaunch", "title": "Sales CRM frozen" }
    ]
  }
}
```

Logo, color, support email, ticket system URL, your apps, your custom problem definitions — all hot-swappable without touching the script. One tool, infinite tenants. An example config showing a healthcare deployment with PHI redaction in the diagnostic bundle lives in [`examples/`](examples/).

The pitch to your finance team is simple: most of your help desk's tickets are repetitive. If MendOS deflects even 30% of them, the time saved pays for itself in the first month, and your IT pros get to work on real problems instead of clearing the same browser cache for the fiftieth time.

## Trust

This tool runs with administrator privileges. That means it can do real damage if you don't trust it. So I'm not asking you to. I'm asking you to read the code.

- **Open source.** Every line of every script that runs on your machine is visible in this repo, pinned to an exact Git commit tag. No minified blobs, no obfuscated functions, no runtime-fetched binaries you can't inspect.
- **SHA-256 hashes** for every release are published on the [Releases](https://github.com/PH30N1X-PR1Me/mendos/releases) page.
- **AMSI stays on.** Windows Defender's anti-malware scanner is never disabled, ever. Every AMSI bypass technique on the internet is a defense-evasion pattern; we use zero of them.
- **No telemetry by default.** It's opt-in. When opt-in, it sends anonymous event names and OS version. No hostnames, no usernames, no IPs.
- **No keylogging, no clipboard reading, no credential harvesting.** Ever. Grep the source for `Get-Clipboard`, `SetWindowsHookEx`, `Get-Credential` — zero matches outside actions you explicitly click.
- **Every change is reversible** via the Undo Last button.
- **Restore points** are created automatically before any multi-step workflow on Windows.
- **A 2017 supply-chain attack** on a similar tool (CCleaner) shipped *signed* malware to 2.27 million users. The takeaway: code signing is necessary but not sufficient. Reproducible builds, commit-pinning, and transparent open source matter more. See [`docs/SECURITY.md`](docs/SECURITY.md) for our full security posture.

If MendOS doesn't pass your security review, I want to hear why. Security feedback is the most valuable PR a project like this can get.

## Try it

```powershell
irm 'https://mendos.heliosprima.com/win' | iex
```

```bash
/bin/bash -c "$(curl -fsSL https://mendos.heliosprima.com/mac)"
```

Paste it. See what it does. If your computer's been fighting you, this is the tool that stops the fight.

## License

MIT for the Light tier. See [`docs/LICENSING.md`](docs/LICENSING.md) for how the Ultimate tier gate works and how the freemium model is implemented.

Copyright (c) 2026 [FR4NTZ0N](https://github.com/PH30N1X-PR1Me) · A [Helios Prima](https://heliosprima.com) product.

---

**MendOS** — *MEND your Operating System.*
