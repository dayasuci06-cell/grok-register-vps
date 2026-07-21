# Grok Auto Register - GitHub Actions VPS

Full otomatis register akun Grok (x.ai) pakai GitHub Actions Windows VPS.

## Cara Pakai

1. **Fork** repo ini (klik tombol Fork di atas)
2. Buka tab **Actions** di repo fork Anda
3. Klik **"Grok Auto Register - Full Otomatis"**
4. Klik **"Run workflow"**
5. Isi:
   - **register_count**: jumlah akun (misal: 5)
   - **email_provider**: pilih `duckmail` (gratis) atau `mailtm`
6. Tunggu selesai (30-60 menit per akun)
7. Download hasil dari tab **Artifacts**

## Hasil

| File | Isi |
|------|-----|
| `accounts_*.txt` | email----password----SSO_Token |
| `tokens.txt` | Daftar token SSO |
| `cpa_auths/` | Kredensial CPA untuk 9Router |

## Spesifikasi VPS

- Windows Server (GitHub Actions runner)
- 2-core Intel Xeon (AVX2 support)
- 7 GB RAM
- Chrome browser otomatis
- Python 3.14.3

## Limitasi

- Max 6 jam per run (GitHub Actions limit)
- Gratis 2000 menit/bulan (akun GitHub free)
- Max 20 concurrent jobs

## Error

Jika `grok_core.pyd` error, kemungkinan:
- Akun x.ai limit registrasi dari IP GitHub
- Cloudflare block registration
- Coba ganti email_provider ke `cloudflare`
