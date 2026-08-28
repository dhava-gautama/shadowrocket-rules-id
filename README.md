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
| Indonesian banks, e-wallets, logistics/mobility, local media, government, telcos, WhatsApp, ID IPs, `GEOIP,ID` | **DIRECT** (`🇮🇩 Indonesia Direct`) |
| Ads (AdvertisingLite) | **REJECT** |
| Streaming, social, AI, remaining foreign | **PROXY** (selectable proxy groups) |

Indonesian rules are evaluated before foreign-service rules and `FINAL`, so local traffic stays on the Indonesian network. Ads are blocked. Foreign streaming, social, AI, and other services use selectable proxy groups.

Aplikasi bank/superapp lokal tetap DIRECT supaya tidak gagal di IP VPN. Iklan di-REJECT. Streaming dan layanan luar negeri lewat grup proxy.

## Import in Shadowrocket

1. Copy the raw URL at the top of this README.
2. Shadowrocket → **Config** → **+** → Download from URL.
3. Paste, download, then set it as the active config.

Cara pakai: salin URL di atas → Shadowrocket → Config → + → unduh dari URL → aktifkan.

## Connection hardening / Penguatan koneksi

### English

- **Encrypted DNS:** The profile uses DoH and `hijack-dns = :53` because many Indonesian ISPs hijack or redirect UDP/TCP port 53, and some blackhole plaintext `1.1.1.1` / `8.8.8.8` or DoH hostnames. Cloudflare and Google DoH go through `#proxy`; BebasID Unfiltered is a local Indonesian resolver. `[Host]` pins Cloudflare, Google, and Quad9 bootstrap IPs so `0.0.0.0` answers cannot poison DoH bootstrap. System DNS is no longer used.
- **Home Wi-Fi Scene (UI only):** Shadowrocket → Home → Global Routing → Scene. Set the Home SSID to routing **Direct**, Cellular to routing **Config** (this profile), then set Global Routing to **Scene**. Location permission may be required for SSID matching.
- **UDP fallback:** `udp-policy-not-supported-behaviour = DIRECT` keeps voice/video calls working when the selected node is TCP-only.
- This remains routing + adblock only, with no unlocks, VIP/cracks, or premium MITM modules.

### Bahasa Indonesia

- **DNS terenkripsi:** Profil memakai DoH dan `hijack-dns = :53` karena banyak ISP Indonesia membajak atau mengalihkan UDP/TCP port 53, dan sebagian memblokir diam-diam DNS polos `1.1.1.1` / `8.8.8.8` atau hostname DoH. DoH Cloudflare dan Google melewati `#proxy`; BebasID Unfiltered adalah resolver lokal Indonesia. `[Host]` memasang IP bootstrap Cloudflare, Google, dan Quad9 agar jawaban `0.0.0.0` tidak meracuni bootstrap DoH. DNS sistem tidak lagi dipakai.
- **Scene Wi-Fi rumah (hanya UI):** Shadowrocket → Home → Global Routing → Scene. Atur SSID rumah ke routing **Direct**, Cellular ke routing **Config** (profil ini), lalu atur Global Routing ke **Scene**. Izin lokasi mungkin diperlukan agar SSID dapat dicocokkan.
- **Fallback UDP:** `udp-policy-not-supported-behaviour = DIRECT` menjaga panggilan suara/video tetap berfungsi saat node yang dipilih hanya mendukung TCP.
- Profil ini tetap hanya untuk routing + adblock, tanpa unlock, VIP/crack, atau modul MITM premium.

## Files

- `shadowrocket_id.conf` — main profile (RULE-SET URLs on this public `main`)
- `rule/Indonesia*.list` / `rule/Indonesia*.rule` — banks, finance, logistics/mobility, media, government, telco, WhatsApp, core `.id`, IP ranges, plus the compact `IndonesiaMax` union
- `js/ai.list` — compact AI routing list for ChatGPT/OpenAI, Claude/Anthropic, Gemini, Grok, Perplexity, and related hosts

Third-party RULE-SETs (blackmatrix7, ACL4SSR) stay on their public remotes.
