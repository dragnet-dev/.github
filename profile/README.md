<p align="center">
  <img src="https://raw.githubusercontent.com/dragnet-dev/.github/main/profile/icon-128-hull-text.png" width="80" height="67" alt="Dragnet" />
</p>

<h3 align="center">dragnet.dev</h3>

<p align="center">
  Open source threat intelligence.<br/>
  Detection rules, IOC feeds, and hunting queries for every major SIEM.<br/>
  Free. No account. No friction.
</p>

<p align="center">
  <a href="https://dragnet.dev">dragnet.dev</a> &nbsp;·&nbsp;
  <a href="https://github.com/dragnet-dev/haul">Rules & Feeds</a> &nbsp;·&nbsp;
  <a href="https://dragnet.dev/feeds">IOC Feeds</a> &nbsp;·&nbsp;
  <a href="https://github.com/dragnet-dev/dragnet">Docs</a>
</p>

<br/>

Dragnet monitors threat intelligence sources across supply chain, malware, ransomware, and actively exploited CVEs. When a new incident is detected (a compromised npm package, a new malware family, a ransomware C2) it automatically generates detection rules for every platform and publishes IOC feeds. Everything updates every 6 hours with no manual intervention.

Rules are generated across three detection layers per incident: **exposure** (do you have the affected package or software?), **IOC hunting** (have you seen the domains, IPs, or file hashes?), and **behavioural hunting** (are the attack TTPs present regardless of known IOCs?). Multi-source confidence scoring means you always know how much to trust each rule.

**Repos**

| | |
|---|---|
| [dragnet](https://github.com/dragnet-dev/dragnet) | The Go CLI engine. Syncs sources, enriches IOCs, and generates rules via GitHub Actions |
| [haul](https://github.com/dragnet-dev/haul) | The live data. Detection rules, IOC feeds, and STIX bundles updated every 6 hours |
| [port](https://github.com/dragnet-dev/port) | The website. Source for dragnet.dev |
| [trawl](https://github.com/dragnet-dev/trawl) | GitHub Action. Checks lockfiles against Dragnet on every PR. No setup required. |
| [scope](https://github.com/dragnet-dev/scope) | VS Code extension. Hover over an import to see if a package is compromised. |
| [buoy](https://github.com/dragnet-dev/buoy) | MCP server. Native Dragnet awareness for Claude Code, Cursor, Windsurf and any MCP-compatible agent. |

**Supported platforms**

Sigma · Microsoft Sentinel · KQL · Splunk · Elastic · Wazuh · CrowdStrike (LogScale + Falcon IOC) · Google Chronicle · Suricata · Snort · IBM QRadar · Datadog

**Consuming the feeds**

No setup needed. Use the raw GitHub URLs directly in your tools:

```
# Combined feeds (all modules)
https://raw.githubusercontent.com/dragnet-dev/haul/main/feeds/domains.txt
https://raw.githubusercontent.com/dragnet-dev/haul/main/feeds/ips.txt
https://raw.githubusercontent.com/dragnet-dev/haul/main/feeds/sha256.txt
https://raw.githubusercontent.com/dragnet-dev/haul/main/feeds/stix/bundle.json
https://raw.githubusercontent.com/dragnet-dev/haul/main/feeds/crowdstrike.json

# Supply chain only
https://raw.githubusercontent.com/dragnet-dev/haul/main/supply/feeds/domains.txt
https://raw.githubusercontent.com/dragnet-dev/haul/main/supply/feeds/unified.json
```

For Microsoft Sentinel connect your workspace directly via Content Hub > Repositories > `dragnet-dev/haul`. Rules deploy automatically on every update.

For all other platforms browse incidents and copy rules at [dragnet.dev](https://dragnet.dev).

**Protect your developer workflow**

Add Dragnet to your CI pipeline in three lines:

```yaml
- uses: dragnet-dev/trawl@v1
```

Install the VS Code extension to catch compromised packages at the point of writing the import:

```
ext install dragnet-dev.scope
```

Give your AI coding agent native supply chain awareness:

```bash
npx @dragnet-dev/buoy install
```

**Contributing**

Spotted an incident not in Dragnet? Add an incident YAML to [haul](https://github.com/dragnet-dev/haul) and open a PR. Posts from trusted sources auto-merge within 60 minutes. Everything else gets a human review. The [dragnet](https://github.com/dragnet-dev/dragnet) repo covers the full incident schema including IOC types, confidence scoring, and detection layer structure.
