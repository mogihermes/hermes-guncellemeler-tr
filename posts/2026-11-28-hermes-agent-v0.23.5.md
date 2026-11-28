# Hermes Agent v0.23.5 — 28 Kasım 2026

**Resmi etiket:** `v0.23.5`
**Yayın tarihi:** 28 Kasım 2026
**Resmî kaynak:** [NousResearch/hermes-agent v0.23.5 yayın notu](https://github.com/NousResearch/hermes-agent/releases/tag/v0.23.5)
**Tam değişiklik karşılaştırması:** [v0.23.4...v0.23.5](https://github.com/NousResearch/hermes-agent/compare/v0.23.4...v0.23.5)

## Bu sürümde öne çıkanlar

- **Patch release:** Bu sürüm, v0.23.4'ün kat ettiği ~338 PR'yi ve 1,262 non-merge commit'i içeren kararlı (stable) sürümdir. 1,146 changed files'da toplam +57,989 / −5,346 değişiklik yapılmıştır.
- **OSC 7577 program resume protokolü:** CLI ve TUI, OSC 7577 program resume protokolünü destekliyor.
- **Idle gateway chat tozlanması:** Arka plana malzeme tozlanması; her rotada ve kanala ayrı idle chat'ler tozlandırılıyor.
- **read_file tails with negative offset:** read_file, negatif offset ile tails destekliyor; dizin listeleniyor.
- **search_files content search completeness:** content search, tamamlanmış sonuç bildiriliyor; hangi dosya tamamladığı bildiriliyor.
- **Sınırlı default-plugins preflight:** Yerel gateway başlatılmadan önce bounded default-plugins preflight yapılıyor.
- **Plugin OAuth redirect URI pinning:** Plugin OAuth entries, redirect URI'lerini pin ableyor.
- **Solstice provider stateless Interactions API:** Solstice provider, stateless Interactions API'ye taşınıyor.
- **Yeni plugin API yüzeyleri:** turn origin, session oluşturma yöntemi, cron scheduling, gateway silence helpers eklentileri eklendi.
- **Dashboard "your dashboard is moving" notice:** Dashboard'ta "your dashboard is moving" uyarısı gösteriliyor.
- **Sessions/plugins pickers raw arrow keys:** Sessions ve plugins pickers'da raw arrow keys çalışıyor.
- **Profile rename/move/remove plugin work bounds:** Profili yeniden adlandırdığınıza/taşıdığınızda/aldırdığınızda plugin work'ları doğru profile bağlanıyor.

## Bilinen sorun

- `v0.22.7` gateway'inde çalışan oturlar `v0.23.0`'a geçişte silinemez; önce `v0.23.0`'a güncelleştirilmesi gerekiyor.
- Web uygulaması varsayılan olarak kapalı; `webapp.enabled` açıklandığında tarayıcılara served edilir.
- Desktop macOS 13+ ve 64-bit Windows gerektirir; Electron 44 artık macOS 11, macOS 12 veya 32-bit Windows'da çalışmaz.
- `hermes mcp serve` artık `hermes mcp-serve`; MCP istemeleri komutunu güncellemelere.

## Güncelleme

- **CLI ve installer-script Masaüstü kurulumları:** `hermes update` veya kurulum tek satırını yeniden çalıştırın.
- **Microsoft Store:** Store üzerinden güncelleme.
- **Docker / Hermes Cloud:** `nousresearch/hermes-agent:stable` veya `:latest`.

## Kullanıcı için amaç

Bu patch release, idle gateway chat'lerin arka planda tozlanması, OSC 7577 program resume protokolünün desteklenmesi ve plugin work'larının profille ilgili değişikliklerde korunmasıyla daha stabil ve öngörülebilir bir deneyim sunuyor. Kullanıcılar cron jobları üzerinden çalışan job'ları daha güvenilir bir şekilde yönetebilecek ve dashboard bildirimleri ile daha iyi uyum sağlayacak.

## Kaynak

Bu yazı, resmî yayın notunun Türkçe bilgilendirme amaçlı özetidir. Teknik ayrıntıların asıl kaynağı: [Hermes Agent v0.23.5](https://github.com/NousResearch/hermes-agent/releases/tag/v0.23.5).