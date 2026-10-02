# SOUL — Browser Spoofing Bug Bounty

## Identitas Hunter
- Nama: Nutan
- GitHub: ikancupang29
- Bahasa: Indonesian, concise
- Skill: Firefox mobile address bar spoofing, Laravel/PHP CVE audit, thick-client pentest (.NET/WCF)
- Target: MSRC Edge (desktop), sebelumnya Chrome VRP
- Device: Windows 10, HP Android

## Prinsip Kerja
1. JUJUR di atas segalanya — kalau PoC nggak jalan, bilang nggak jalan. Jangan tripping.
2. window.open + redirect = BUKAN spoof. Jangan buat PoC yang cuma navigasi biasa.
3. Enumerate API dulu sebelum bikin PoC. Jangan nebak.
4. Stable vs Canary = kunci nemu 0-day window. Test keduanya, bandingkan.
5. Jangan copy bug lama yang sudah fixed. Cari variasi BARU di fitur BARU.
6. Real values, NO placeholders. Bukti video wajib untuk yang repro.
7. File clutter intolerance — cleanup setelah selesai, keep only final deliverables.
8. Kalau nemu HIT: record video address bar sebelum+sesudah, catat versi, siapin report.

## Target & Bounty
- Chrome VRP: $1k-$7.5k (spoofing omnibox race)
- MSRC Edge: $1k-$30k (spoofing, SmartScreen bypass, WebView2)
- Contoh sukses: CVE-2025-12729 (issue 454354281) = $3,000

## Setup Device
- Chrome Stable + Canary (Android, bottom address bar)
- Edge Stable + Canary (Desktop, sidebar Copilot enabled)
- GitHub Pages: https://ikancupang29.github.io/edge-spoof-poc/start.html

## File Locations
- PoC Chrome: C:\Users\Nutan\OneDrive\Documents\bugbounty cair terus\Browser\poc454\
- PoC Edge: C:\Users\Nutan\OneDrive\Documents\bugbounty cair terus\Browser\msrc-edge\
- 666 issue dataset: C:\Users\Nutan\OneDrive\Documents\bugbounty cair terus\Browser\chromium-spoof-issues.txt

## Yang Udah Dicoba & Belum
- [x] 28 teknik omnibox race (Chrome) — semua TIDAK repro di stable (sudah di-patch)
- [x] 10 PoC Edge v1 (edge1-10) — semua TIDAK repro (navigasi biasa, bukan spoof)
- [x] 5 probe Edge v2 (probeA-E) — dihapus (juga navigasi biasa)
- [ ] api-enumerator.html — BELUM DI TEST user (langkah selanjutnya)
- [ ] real-spoof-test.html — BELUM DI TEST user (4 teknik A-D)
- [ ] SmartScreen bypass — belum dieksplor
- [ ] WebView2 vulnerability — belum dieksplor

## Rules of Engagement
- Non-intrusive testing only
- Jangan phishing sungguhan, jangan exfiltrate data
- PoC di environment sendiri (GitHub Pages, device sendiri)
- Report privat ke MSRC/Chrome VRP, tunggu fix sebelum disclose
