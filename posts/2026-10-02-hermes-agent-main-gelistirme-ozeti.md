# Hermes Agent `main` geliştirme özeti — 2 Ekim 2026

> **Kararlılık durumu:** Bu bir sürüm notu değildir. Resmî son sürüm hâlâ [`v2026.9.24`](https://github.com/NousResearch/hermes-agent/releases/tag/v2026.9.24); aşağıdakiler `main` dalında bulunan, henüz yeni bir sürüm etiketiyle yayımlanmamış geliştirmelerdir.

- **Karşılaştırma:** [`v2026.9.24...main`](https://github.com/NousResearch/hermes-agent/compare/v2026.9.24...main)
- **Amaç:** Resmî sürüm notu beklenirken, kullanıcıyı etkileyebilecek yeni değişiklikleri erken görünür kılmak.

## Öne çıkan geliştirmeler

- **Yerel araç çağrılarında batch işleme:** Yerel `tool_call` batch'leri araç başına pipeline üzerinden yürütülüyor. [resmî commit](https://github.com/NousResearch/hermes-agent/commit/2e704550b5f70d07335bc6f7bc564a9dbce856d)
- **Model katalogları:** Canlı keşif fallback'e düştüğünde hesapla sınırlı Codex satırlarının korunmasına yönelik düzeltme var; Anthropic curated fallback'i de placeholder olarak işaretleniyor. [Codex](https://github.com/NousResearch/hermes-agent/commit/3fbace2e76405e769033c60a384773800c4a39b9) · [Anthropic](https://github.com/NousResearch/hermes-agent/commit/ba2a38e7715b73fc4fea623efc5d0feb50295b62)
- **Cron teslimatı:** Kısmi gönderimden sonra standalone fallback'in aynı çıktıyı yeniden göndermemesi ve 60 saniyeyi aşan canlı gönderimin sonlandırılmaması için düzeltmeler ekleniyor. [kısmi teslim](https://github.com/NousResearch/hermes-agent/commit/be5e9f72c6681af9dfb75bf480f08844f1499949) · [uzun gönderim](https://github.com/NousResearch/hermes-agent/commit/e7b68e4a4aca9a41e3f7147e56cd876ee3476df7)
- **Komut satırı durumu:** `hermes status` için özet varsayılan davranış yapılıyor; tüm bölümler `--full` ile, kısa görünüm ise `--short` ile sunuluyor. [resmî commit](https://github.com/NousResearch/hermes-agent/commit/a3149156ecc4bee636330b94753426f0e89c42ea) · [`--short`](https://github.com/NousResearch/hermes-agent/commit/c82ad613ec6c2f3e090abbdfb09d354d2c3d5467)
- **Desktop güncelleme sonucu:** Banner gösterildikten sonra oluşan hatanın, sonlandırılmış güncellemeyi başarısız olarak koruması için düzeltme var. [resmî commit](https://github.com/NousResearch/hermes-agent/commit/7f7e1ab402d5cd1d60347840dec858f30a43c91d)

## Kullanıcı için amacı

Bu değişiklikler henüz etiketli sürüme dahil değildir. Özellikle cron çıktılarının çift gönderilmesini önleme, araç batch'leri ve model listelerinin fallback durumundaki davranışı günlük kullanımda daha güvenilir akışlar hedefliyor.

## Kaynak

Bu özet yalnızca NousResearch/hermes-agent deposunun açık `main` dalındaki commit başlıklarına ve [karşılaştırma görünümüne](https://github.com/NousResearch/hermes-agent/compare/v2026.9.24...main) dayanır. Kararlı ürün davranışı için asıl kaynak [resmî GitHub yayın notlarıdır](https://github.com/NousResearch/hermes-agent/releases).
