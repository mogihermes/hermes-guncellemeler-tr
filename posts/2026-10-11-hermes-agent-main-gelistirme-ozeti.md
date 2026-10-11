# Hermes Agent `main` geliştirme özeti — 11 Ekim 2026

> **Kararlılık durumu:** Bu bir sürüm notu değildir. Resmî son sürüm [`v0.21.6`](https://github.com/NousResearch/hermes-agent/releases/tag/v0.21.6); aşağıdakiler `main` dalında bulunan, henüz yeni bir sürüm etiketiyle yayımlanmamış geliştirmelerdir.

- **Karşılaştırma:** [`v0.21.6...main`](https://github.com/NousResearch/hermes-agent/compare/v0.21.6...main)
- **Kapsam:** 10 Ekim 2026 özetinden sonra gelen kullanıcıyı etkileyen resmî commitler.

## Öne çıkan geliştirmeler

- **Tarayıcı yerel geri dönüşü:** Bulut tarayıcı sağlayıcısı başarısız olduğunda `browser_exec` artık yerel geri dönüşü kullanıyor. Özel URL rotası da kendi daemon'ında yerel Chromium'a ulaşıyor. [bulut sağlayıcı geri dönüşü](https://github.com/NousResearch/hermes-agent/commit/04eb00cef7d9ac2730ed5fd9039a6f3287eb49ca) · [özel URL rotası](https://github.com/NousResearch/hermes-agent/commit/7cbbb586c367c41c6d7b1121de79b3f5c7d927fd)
- **`main` kanalı güncellemesi:** `main` kanalı, bir R2 kaydını okumadan doğrudan git dalını izliyor. [resmî düzeltme](https://github.com/NousResearch/hermes-agent/commit/4b351c751a3be1eaef0cedff432ed8f72f78c95d)
- **Alibaba içerik koruması:** Alibaba'nın içerik koruması, dört dakikalık yeniden deneme döngüsü yerine turu sonlandırıyor. [resmî düzeltme](https://github.com/NousResearch/hermes-agent/commit/42f210de11eb6f7ebc9ad677caa1221a303cdfe8)
- **Desktop eklenti eylemleri:** Eklentiler yerleşik uygulama eylemlerini `ctx.runAction` ile çalıştırabiliyor. [resmî özellik](https://github.com/NousResearch/hermes-agent/commit/0e0539c0f01bd5abfbddfefec4c6d99158a243eb)
- **Akıl yürütme bilgisinin korunması:** `/steer`, `/branch` ve compaction hesaplaması akıl yürütme bilgisini koruyor. [resmî düzeltme](https://github.com/NousResearch/hermes-agent/commit/df3c21400d598684be57e2229d85e2270baf6031)

## Kullanıcı için amacı

Bu etiketlenmemiş geliştirmeler, tarayıcı işlemlerinde geri dönüş davranışını, `main` kaynak güncellemelerini ve eklenti entegrasyonlarını iyileştirmeyi; bazı sağlayıcı ve oturum akışlarında gereksiz yeniden denemeleri veya akıl yürütme kaybını önlemeyi hedefliyor.

## Kaynak

Bu özet yalnızca NousResearch/hermes-agent deposunun açık `main` dalındaki ilgili commitlere ve [karşılaştırma görünümüne](https://github.com/NousResearch/hermes-agent/compare/v0.21.6...main) dayanır. Kararlı ürün davranışı için asıl kaynak [resmî GitHub yayın notlarıdır](https://github.com/NousResearch/hermes-agent/releases).
