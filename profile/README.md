<p align="center">
  <img src="https://raw.githubusercontent.com/dragnet-dev/port/main/public/icon-128.svg" width="80" height="67" alt="Dragnet" />
</p>

<h3 align="center">dragnet.dev</h3>

<p align="center">
  Open source threat intelligence.<br/>
  Detection rules and IOC feeds for every major SIEM. Free. No account.
</p>

<p align="center">
  <a href="https://dragnet.dev">Website</a> ·
  <a href="https://github.com/dragnet-sh/haul">Rules & Feeds</a> ·
  <a href="https://dragnet.dev/feeds">IOC Feeds</a>
</p>

---

## What's here

| Repo | What it is |
|---|---|
| [dragnet](https://github.com/dragnet-sh/dragnet) | The engine — Go CLI that syncs threat intel sources and generates detection rules |
| [haul](https://github.com/dragnet-dev/haul) | The data — live detection rules, IOC feeds, STIX bundles updated every 6 hours |
| [port](https://github.com/dragnet-dev/port) | The site — source for dragnet.dev |

---

## Consume the feeds

No account needed. Point your tools directly at these URLs:

```
# All modules combined
https://raw.githubusercontent.com/dragnet-sh/haul/main/feeds/domains.txt
https://raw.githubusercontent.com/dragnet-sh/haul/main/feeds/ips.txt
https://raw.githubusercontent.com/dragnet-sh/haul/main/feeds/sha256.txt
https://raw.githubusercontent.com/dragnet-sh/haul/main/feeds/stix/bundle.json
https://raw.githubusercontent.com/dragnet-sh/haul/main/feeds/crowdstrike.json

# Supply chain only
https://raw.githubusercontent.com/dragnet-sh/haul/main/supply/feeds/domains.txt
https://raw.githubusercontent.com/dragnet-sh/haul/main/supply/feeds/unified.json
```

---

## Connect your SIEM

**Microsoft Sentinel** — connect your workspace directly via Content Hub → Repositories → `dragnet-sh/haul`

**All other platforms** — browse incidents and copy rules at [dragnet.dev](https://dragnet.dev)

---

## Contribute

Spotted an incident not in Dragnet? Open a PR on [haul](https://github.com/dragnet-sh/haul) with an incident YAML. Trusted sources auto-merge within 60 minutes. See the [schema docs](https://github.com/dragnet-sh/dragnet) for the format.
