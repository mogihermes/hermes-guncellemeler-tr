# Hermes Agent `main` geliştirme özeti — 21 Ekim 2026

> **Kararlılık durumu:** Bu bir sürüm notu değildir. Resmî son sürüm [`v0.22.2`](https://github.com/NousResearch/hermes-agent/releases/tag/v0.22.2); aşağıdakiler `main` dalında bulunan, henüz yeni bir sürüm etiketiyle yayımlanmamış geliştirmelerdir.

- **Karşılaştırma:** [`v0.22.2...main`](https://github.com/NousResearch/hermes-agent/compare/v0.22.2...main)
- **Kapsam:** 20 Ekim özetinden sonra görülen kullanıcıyı etkileyen resmî `main` commitleri.

## Öne çıkan geliştirmeler

- **Sıkıştırılmış oturumlarda yinelenen yanıtlar:** `/compress` sonrasında veya oturum sürdürülürken bir önceki yanıtın iki kez görünmesine neden olan durum düzeltiliyor. Aynı düzeltme dışa aktarımlar ile Desktop/REST transkript listesini de kapsıyor. [oturum görünümü commit'i](https://github.com/NousResearch/hermes-agent/commit/a59ed658aa853922f2d02a6d5c0eab4e60b3d48a) · [dışa aktarım ve transkript commit'i](https://github.com/NousResearch/hermes-agent/commit/c8aa61b78830091ab74e652dda14519053dd70fd)
- **Gateway yeniden başlatmada profil ve Desktop güvenilirliği:** `restart --all --detach` kök profilde yanlışlıkla etkin profili başlatmıyor; `--force` korunuyor ve eski çalışma zamanları `--detach` seçeneğini tanımazsa Desktop yeniden deniyor. Ayrıca hizmet kurulmamış bir sistemde Desktop’ın "Restart Hermes" çağrısı kendi sürecini gateway’e dönüştürüp zaman aşımına düşmüyor. [yeniden başlatma commit'i](https://github.com/NousResearch/hermes-agent/commit/c1c8543a1339c9608071a0a874b2753e94db7487) · [kök profil commit'i](https://github.com/NousResearch/hermes-agent/commit/9ec17f7f4fe52bfa290a6cd015e9be2abf241b2b) · [Desktop commit'i](https://github.com/NousResearch/hermes-agent/commit/f40965b2003e670631a0fec58aa8c8748bd31b87)
- **Paylaşılan metrikler için daha yalın izin:** Desktop, dashboard ve terminalde ilk kurulumdaki üç seçenek, "Share with Nous" veya "No thanks" olmak üzere iki seçeneğe indiriliyor; Desktop **Settings > Privacy** ve `hermes setup telemetry` aynı aç/kapat davranışına yaklaşıyor. Daha önce yalnız yerelde toplama seçeneğini kullanan profiller yeniden sorulmuyor ve veri göndermiyor. [resmî shared-metrics commit'i](https://github.com/NousResearch/hermes-agent/commit/d7c48548a972d7689eeeefe1b66282f392957f77)
- **Eklenti terminal ortamları:** Eklenti terminal arka uçları isteğe bağlı başlangıç dizini ve akış desteği tanımlayabiliyor; destekleyen ortamlar Bot Desktop’ı terminalle birlikte barındırabiliyor. Hiçbirini tanımlamayan eklentilerin davranışı değişmiyor. [resmî terminal commit'i](https://github.com/NousResearch/hermes-agent/commit/e166392fec120c8ceeb541d68bdde9c6ed0c835c)

## Kullanıcı için amacı

Bu etiketlenmemiş çalışma; sıkıştırılmış sohbetlerde temiz geçmiş görünümünü, gateway/desktop yeniden başlatmalarının daha güvenilir olmasını, telemetri izninin netleşmesini ve eklenti tabanlı terminal ortamlarının yeteneklerini hedefliyor.

## Kaynak

Bu özet yalnızca NousResearch/hermes-agent deposunun açık `main` dalındaki ilgili commitlere ve [karşılaştırma görünümüne](https://github.com/NousResearch/hermes-agent/compare/v0.22.2...main) dayanır. Kararlı ürün davranışı için asıl kaynak [resmî GitHub yayın notlarıdır](https://github.com/NousResearch/hermes-agent/releases).
