# Hermes Agent v0.23.4 — 24 Kasım 2026

**Resmi etiket:** `v0.23.4`
**Yayın tarihi:** 24 Kasım 2026
**Resmî kaynak:** [NousResearch/hermes-agent v0.23.4 yayın notu](https://github.com/NousResearch/hermes-agent/releases/tag/v0.23.4)
**Tam değişiklik karşılaştırması:** [v0.23.3...v0.23.4](https://github.com/NousResearch/hermes-agent/compare/v0.23.3...v0.23.4)

## Bu sürümde öne çıkanlar

- **Patch release:** Bu sürüm, v0.23.3'ün kat ettiği ~229 PR'yi ve 1,122 non-merge commit'i içeren kararlı (stable) sürümdir. 1,316 changed files'da toplam +96,873 / −6,703 değişiklik yapılmıştır.
- **Plugin katalogu güncellemesi:** Plugin kataloğu deployed'ı artık canlı kataloğu kullanıyor; girişte hata vermeden yeni eklentiler bulunup kurabiliyor.
- **MCP araçları:** Fiyat etiketleme özelliği eklendi; her çağrının maliyetini ve chatın çalışan toplamını bildiriyor.
- **Geliştirilmiş yetkinlik seti:** 58'den 44 temelbeceri; `microsoft-office` becerisi eklendi; 12 nichebeceri opsiyonel eklenti.
- **Beceri kilitleme:** `hermes curator lock <beceri>` ile beceri değişir; `--yolo` altında bile geçersiz kılınmaz.
- **Şifre yöneticileri:** Doğrulandı şifre yöneticisi eklentileri, tarayıcıya oturum açma bilgileri göndermeden önceki kullanıcılarının görünmesini engeller.
- **Türkiye Gateway desteği:** Grup sohbetleri gateway'lerde çalışabilir; farklı makinelerden botlar içerebilir.
- **Görüntü terminalde:** CLI ve TUI'de gerçek piksel çizimi; kitty, Ghostty, iTerm2, WezTerm, Konsole ve VS Code terminali destekleniyor.
- **Sohbet geri al (rewind):** TUI/klasik CLI'de Esc iki kez veya `/rewind` ile önceki mesaj geri alınabilir.
- **Tek gateway, tüm sohbet:** Tek bir gateway her oturumu yönetir; tüm floor'lar aynı kaynağa bağlanır.
- **Bellek performansı:** Uzun hayatlı gateway'ler kapatılan oturumların belleğini serbest bırakır; cron işleri prompt önbelleği paylaşır.
- **Geliştirilmiş delegasyon:** Varsayılan delegasyon artık eklenebilir; advanced-delegation eklentisi ile her alt görev nomi verilen modele veya ayrı profile gönderilebilir.
- **Plugin docstring güvenlik:** Docstring'lar artık "safe" yerine "caution" olarak değerlendiriliyor; yanlış "safe" etiketlenmesi önleniyor.
- **SSRF/secret-URL refusals:** @url referanslarındaki güvenlik uyarıları uygulanmış.
- **Gateway attachment handling:** Attachments ekleri reconnected adapter'a taşınıyor.
- **Plugin catalog entries:** Giriş/belgeledi eklentiler güncellenmiş/delisteden çıkartılmış.
- **Auth/fallback improvements:** Farklı auth ve fallback improvements yapılmıştır.

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

Bu patch release, plugin kataloğunun çalışmasını sağlamasa da, workspace'ları tarayıcıda açmaya, tek gateway tüm oturumları yönetmeye ve kullanıcıların sohbet geri alma yeteneğine odaklanmaktadır. Özellikle uzun yerel model istekleri kesilmeden tamamlanmalı ve gateway'ler daha güvenilir şekilde başlatılmalı.

## Kaynak

Bu yazı, resmî yayın notunun Türkçe bilgilendirme amaçlı özetidir. Teknik ayrıntıların asıl kaynağı: [Hermes Agent v0.23.4](https://github.com/NousResearch/hermes-agent/releases/tag/v0.23.4).