# Kara onclite Kernel Build Action

Automated kernel build for **Xiaomi Redmi 7 / Y3 (onclite)** using GitHub Actions.

## Fitur

- Source: [gen69x/kernel_xiaomi_onclite](https://github.com/gen69x/kernel_xiaomi_onclite) (branch `los`)
- Defconfig: `onclite-perf_defconfig`
- Toolchain: **Proton Clang** ([kdrag0n/proton-clang](https://github.com/kdrag0n/proton-clang))
- Packaging: [AnyKernel3](https://github.com/gen69x/AnyKernel3)
- Auto Release ke GitHub Releases
- Notifikasi Telegram (sebelum build & sesudah selesai + kirim file ZIP)

## Konfigurasi Saat Ini

| Item              | Nilai                                              |
|-------------------|----------------------------------------------------|
| Kernel Source     | https://github.com/gen69x/kernel_xiaomi_onclite    |
| Branch            | `los`                                              |
| Defconfig         | `onclite-perf_defconfig`                           |
| Arch              | `arm64`                                            |
| Toolchain         | Proton Clang                                       |
| AnyKernel3        | https://github.com/gen69x/AnyKernel3               |
| Auto Release      | Ya                                                 |
| Telegram Notif    | Ya                                                 |

## Cara Pakai

1. Fork atau clone repo ini.
2. Tambahkan **Secrets** di Settings → Secrets and variables → Actions:

   | Secret          | Keterangan                          |
   |-----------------|-------------------------------------|
   | `TG_BOT_TOKEN`  | Token bot Telegram                  |
   | `TG_CHAT_ID`    | Chat ID / Channel ID tujuan notif   |

3. Buka tab **Actions** → pilih workflow **Build Kernel Kara onclite (Proton Clang)** → **Run workflow**.
4. Tunggu sampai selesai. Hasil build akan:
   - Diupload sebagai Artifact
   - Dibuat GitHub Release
   - Dikirim ke Telegram (file ZIP + info)

## Tips Troubleshooting (Kernel 4.9)

Kernel Onclite berbasis **Linux 4.9** (sangat lama). Jika build gagal:

1. **LTO error**  
   Uncomment baris berikut di workflow:
   ```yaml
   disable-lto: true

•Credits

 *Kernel: gen69x/kernel_xiaomi_onclite

 *AnyKernel3: gen69x/AnyKernel3

 *Toolchain: kdrag0n/proton-clang

 *Build Action: https://github.com/dabao1955/kernel_build_action
