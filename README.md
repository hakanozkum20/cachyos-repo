# cachyos-repo

KineticWE ISO'su için özel pacman deposu. GitHub Pages üzerinden servis edilir:
`https://hakanozkum20.github.io/cachyos-repo/$arch`

## İçerik

Şu an sadece AUR'dan derlenen paketler (diğer tüm paketler CachyOS/resmi depolardan gelir):

- `noctalia-git` — CachyOS Wayland shell'i

## CI

`.github/workflows/build.yml` AUR paketlerini otomatik derleyip bu repoya pushlar:
- main'e push'ta, haftalık (her pazartesi) ve manuel tetiklenebilir.
- Derlenecek paketler workflow içindeki `AUR_PACKAGES` değişkeninde listelenir.

## Kurulum (GitHub'da)

1. Bu repoyu GitHub'a pushla: `hakanozkum20/cachyos-repo`
2. **Settings → Pages**: Source = `Deploy from a branch`, branch = `main`, folder = `/ (root)`.
3. **Settings → Actions → General**: Workflow permissions = `Read and write permissions`.
4. Actions sekmesinden "Build AUR packages" workflow'unu bir kez manuel çalıştır.
5. Pages yayınlandıktan sonra doğrula:
   ```bash
   curl -s https://hakanozkum20.github.io/cachyos-repo/x86_64/cachyos-repo.db.tar.gz | head
   ```
