# Hermes Agent `main` geliştirme özeti — 7 Ekim 2026

> **Kararlılık durumu:** Bu bir sürüm notu değildir. Resmî son sürüm hâlâ [`v2026.9.24`](https://github.com/NousResearch/hermes-agent/releases/tag/v2026.9.24); aşağıdakiler `main` dalında bulunan, henüz yeni bir sürüm etiketiyle yayımlanmamış geliştirmelerdir.

- **Karşılaştırma:** [`v2026.9.24...main`](https://github.com/NousResearch/hermes-agent/compare/v2026.9.24...main)
- **Kapsam:** 6 Ekim 2026 özetinden sonra gelen kullanıcıyı etkileyen resmî commitler.

## Öne çıkan geliştirmeler

- **Dallanmış sohbetlerde yükleme ekranı düzeltmesi:** Açık sohbet dallandırıldığında yeni dal artık yükleme göstergesinde takılı kalmıyor. Yönlendirme bir sonraki render'da güncellendiğinde, devam ettirilen oturumun yeni dalın kendisine ait olduğu korunuyor. [resmî commit](https://github.com/NousResearch/hermes-agent/commit/38241883765f3faf1109566d86be3432988a4f8d)
- **Başlatma sırasındaki Chronos çalıştırmaları:** Gateway başlarken gelen bir Chronos çalıştırması artık adapter'lar olmadan çalışmıyor; adapter'ların hazır olmasını bekliyor. Bekleme, dashboard forwarder zaman aşımının altında tutuluyor ve çalışma 60 saniye sonra yeniden deneniyor. Gateway başlatma sırasında draining durumuna geçerse veya draining ile hazır olursa çalışma reddediliyor. [ilgili başlangıç düzeltmesi](https://github.com/NousResearch/hermes-agent/commit/e574b02570ad43f347d4dded4cb7ccc8ebea97df) · [zaman aşımı ve yeniden deneme](https://github.com/NousResearch/hermes-agent/commit/733ee1e96a69e5ec87f7f9e5732e62537bdf2a44) · [draining reddi](https://github.com/NousResearch/hermes-agent/commit/05d0a910d4e208ca31fe64433ef0a6c28c3655d9)
- **Relay DM teslimatlarında kaynak kullanıcı:** Cron relay DM teslimatları artık kaynak `user_id` bilgisini taşıyor; böylece soğuk yönlendirme önbelleğinde de dışa teslimat yapılabiliyor. [resmî commit](https://github.com/NousResearch/hermes-agent/commit/6cb3bab6b3bf872d365c13e7ed5b4e716f6e6ad1)

## Kullanıcı için amacı

Bu etiketlenmemiş düzeltmeler, Desktop'ta dallanmış sohbetlere güvenilir geçişi ve başlangıç/draining anlarında zamanlanmış işlerin yanlış ya da eksik teslim edilmemesini hedefliyor.

## Kaynak

Bu özet yalnızca NousResearch/hermes-agent deposunun açık `main` dalındaki ilgili commitlere ve [karşılaştırma görünümüne](https://github.com/NousResearch/hermes-agent/compare/v2026.9.24...main) dayanır. Kararlı ürün davranışı için asıl kaynak [resmî GitHub yayın notlarıdır](https://github.com/NousResearch/hermes-agent/releases).
