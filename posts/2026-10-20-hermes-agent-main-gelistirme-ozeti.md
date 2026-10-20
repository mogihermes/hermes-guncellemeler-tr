# Hermes Agent `main` geliştirme özeti — 20 Ekim 2026

> **Kararlılık durumu:** Bu bir sürüm notu değildir. Resmî son sürüm [`v0.22.2`](https://github.com/NousResearch/hermes-agent/releases/tag/v0.22.2); aşağıdakiler `main` dalında bulunan, henüz yeni bir sürüm etiketiyle yayımlanmamış geliştirmelerdir.

- **Karşılaştırma:** [`v0.22.2...main`](https://github.com/NousResearch/hermes-agent/compare/v0.22.2...main)
- **Kapsam:** 19 Ekim özetinden sonra görülen kullanıcıyı etkileyen resmî `main` commitleri.

## Öne çıkan geliştirmeler

- **`/cron` komutlarının gateway sahipliği:** Klasik CLI’deki `/cron` okuma ve yazma biçimleri, cron deposuna sahip gateway üzerinden çalışıyor. Böylece istemci ve gateway’in aynı cron deposuna ayrı yazıcılar olması önleniyor; `/cron run` da işin gerektirdiği yürütücü havuzunda bekliyor. [sahiplik commit'i](https://github.com/NousResearch/hermes-agent/commit/9ca23c68400fada76e2d15089917eba8e27b023e) · [çalıştırma commit'i](https://github.com/NousResearch/hermes-agent/commit/db481bfadeb1caf2df48284a3e0f0e9b45275887)
- **Yanıt vermeyen gateway’de `/cron` okumaları:** Çalıştırma gerektirmeyen `/cron` ve `/cron list` çağrıları, gateway yanıt vermediğinde uzun yeniden bağlanma süresi yerine yanıt son tarihini koruyor. [resmî CLI commit'i](https://github.com/NousResearch/hermes-agent/commit/a36db282b90523a4f5af47b4f390b6d242c9def7)
- **Tur ortasında `/stop` görünürlüğü:** Klasik CLI’de aktif bir tur sırasında yazılan `/stop`, kesinti ve arka plan işi durdurma sonuçlarını artık terminalde görünür şekilde yazdırıyor. [resmî CLI commit'i](https://github.com/NousResearch/hermes-agent/commit/d87e7536e042a9d0668e88d8762769db41018189)
- **Git ile kurulan eklenti güncellemeleri:** Desktop ve dashboard, git ile kurulan eklentileri CLI’nin güncelleme yolu üzerinden güncelliyor; Desktop’ta güncelleme düğmesi ile güvenlik taraması uyarısı için geçersiz kılma diyaloğu ekleniyor. [güncelleme commit'i](https://github.com/NousResearch/hermes-agent/commit/3ac037670a09cc48a803346223218e2869aad438) · [Desktop commit'i](https://github.com/NousResearch/hermes-agent/commit/17aab768ece43fec64fc637c080b4709cadf8ed0)

## Kullanıcı için amacı

Bu etiketlenmemiş çalışma; cron işlemlerinin tek sahipli ve daha dayanıklı yürütülmesini, tur içi durdurma bilgisinin görünmesini ve git-tabanlı eklentilerin Desktop üzerinden güncellenebilmesini hedefliyor.

## Kaynak

Bu özet yalnızca NousResearch/hermes-agent deposunun açık `main` dalındaki ilgili commitlere ve [karşılaştırma görünümüne](https://github.com/NousResearch/hermes-agent/compare/v0.22.2...main) dayanır. Kararlı ürün davranışı için asıl kaynak [resmî GitHub yayın notlarıdır](https://github.com/NousResearch/hermes-agent/releases).
