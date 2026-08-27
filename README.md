# Indonesia Shadowrocket rules

**Shadowrocket subscribe / import URL:**

```
https://raw.githubusercontent.com/dhava-gautama/shadowrocket-rules-id/main/shadowrocket_id.conf
```

Public host for Indonesia-optimized Shadowrocket routing + adblock.  
Host publik untuk aturan Shadowrocket Indonesia (routing + adblock).

This is **routing and adblock only** — not app unlocks, VIP cracks, or piracy modules.  
Ini **bukan** modul unlock / VIP / bajakan.

## What it does / Apa isinya

| Traffic | Policy |
|---|---|
| Indonesian banks, e-wallets, superapps, `.go.id` / government, telcos, WhatsApp, ID IPs, GEOIP ID | **DIRECT** (`🇮🇩 Indonesia Direct`) |
| Ads (AdvertisingLite) | **REJECT** |
| Streaming, social, AI, remaining foreign | **Proxy groups** |

Local banking and superapps stay on the Indonesian network so they do not break behind a VPN egress IP. Ads are blocked. Streaming and other foreign services go through selectable proxy groups.

Aplikasi bank/superapp lokal tetap DIRECT supaya tidak gagal di IP VPN. Iklan di-REJECT. Streaming dan layanan luar negeri lewat grup proxy.

## Import in Shadowrocket

1. Copy the raw URL at the top of this README.
2. Shadowrocket → **Config** → **+** → Download from URL.
3. Paste, download, then set it as the active config.

Cara pakai: salin URL di atas → Shadowrocket → Config → + → unduh dari URL → aktifkan.

## Files

- `shadowrocket_id.conf` — main profile (RULE-SET URLs on this public `main`)
- `rule/Indonesia*.list` / `rule/Indonesia*.rule` — banks, finance, superapps, media, gov, telco, WhatsApp, core `.id`, IP ranges, plus a wider `IndonesiaMax` set
- `js/ai.list` — small AI domain list (OpenAI / Bing / Bard / related CDNs)

Third-party RULE-SETs (blackmatrix7, ACL4SSR) stay on their public remotes.
