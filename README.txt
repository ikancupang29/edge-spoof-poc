# MSRC EDGE HUNTING — PANDUAN

## CHANNEL YANG HARUS INSTALL
1. Microsoft Edge Stable (https://www.microsoft.com/edge/download)
2. Microsoft Edge Canary (https://www.microsoft.com/edge/download — scroll ke "Edge Canary")

Cek versi: ketik `edge://version` di address bar.

## CARA TEST (sama kayak Chrome, beda browser)
1. Test PoC di Edge STABLE → catat hasil (REPRO / TIDAK)
2. Test PoC SAMA di Edge CANARY → catat hasil
3. VERDICT:
   - Stable=REPRO + Canary=TIDAK = HIT (0-day window, layak report!)
   - Stable=REPRO + Canary=REPRO = bug aktif, juga layak
   - Stable=TIDAK = skip

## FITUR UNIK EDGE YANG DI-TEST (attack surface baru)
1. Sidebar (Copilot panel) — panel kanan yang muncul, origin bisa spoof
2. Vertical tabs — address bar position beda
3. Immersive reader — reading mode, URL bisa beda
4. Web capture — screenshot tool, origin bisa spoof
5. Collections — fitur bookmark, UI bisa spoof
6. Edge kids mode — permission prompt beda

## MOBILE VS DESKTOP
- DESKTOP: mulai sini (lebih gampang test, fitur unik lebih banyak)
- MOBILE: test juga setelah nemu di desktop (Edge Android ada bottom bar)

## REPORT KE MSRC
- URL: https://msrc.microsoft.com/report
- Pilih: "Microsoft Edge" sebagai produk
- Isi: repro steps, PoC HTML, video bukti, versi Edge (stable + canary)
- Dampak: jelaskan kenapa spoofing ini security bug (bukan UI glitch)
