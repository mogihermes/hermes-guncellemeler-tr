# Hermes Agent `main` geliştirme özeti — 3 Kasım 2026

> **Kararlılık durumu:** Bu bir sürüm notu değildir. Resmî son sürüm [`v0.22.6`](https://github.com/NousResearch/hermes-agent/releases/tag/v0.22.6); aşağıdakiler `main` dalında bulunan, henüz yeni bir sürüm etiketiyle yayımlanmamış geliştirmelerdir.
> **Kapsam:** 2 Kasım (veya önceki özet) özetinden sonra görülen kullanıcıyı etkileyen resmî `main` commitleri.

## Öne çıkan geliştirmeler

- **Inline update report, appartığı hat'a bağlanır** - `5b526a531890`: Switching the update target (mientras bir backend failure gösteriliyorken macOS Check for Updates'i değiştirirsen), eski report'in upload'i hiç görünmez link ile bitse ve daha sonraki client failure'ıBackend raporunu gösterse, box currently drops its report on unmount ve target tarafından keyed olunduğu için kapatma, retry ve target switch tüm üç durumlu raporu doğru keyer.

- **Rapor never outlives its failure: target switch drops it** - `5b526a531890`: UpdateErrorReport'ta useEffect cleanup, inline report'in failure this box shows (retry, close veya unmount) olduğunda dismiss edilmesini sağlar.

- **Raporın Copy butonu ilk log satırıyla örtüşmüyor** - `5b526a531890`: Inline report'ta Copy butonu, first log line'ı örtmediği için kullanıcı hata mesajını okurken kopyalayabilir.

- **Inline report, açıldığı an içine kaydırılır** - `5b526a531890`: Inline report, kullanıcı tarafından görülmesi için kısa pencerede otomatik olarak görünene konumlandırılır.

- **Kısa pencerelerde hata raporı retry edilirse kalıcı olur** - `5b526a531890`: Update error box, kısa pencerelerde scroll olunduğu için failed report retry edildiğinde hâlın görünür kalır.

- **Hata raporu içinde remaining notice ve failing line tutarlı olarak gösterilir** - `5b526a531890`: Update error box, report link'ının içeriide failing line ve full notice'la tutarlı olarak gösterilmesini sağlar.

- **Başarısız güncelleme, output'un gösterilip rapor linki gönderir** - `5b526a531890`: Failed update artık output'un gösterilmesini ve error box içinden report linki gönderimini sağlar.

## Kullanıcı için amacı

Bu etiketlenmemiş çalışma; desktop güncelleme raporlarının hata bağlamına bağlanması, hata raporlarının kullanıcıya daha iyi gösterilmesi, inline raporların doğru yönetilmesi ve başarısız güncellemeler hakkında clearer feedback sağlaması hedefliyor.

## Kaynak

Bu özet yalnızca NousResearch/hermes-agent deposunun açık `main` dalındaki ilgili commitlere ve [karşılaştırma görünümüne](https://github.com/NousResearch/hermes-agent/compare/v0.22.6...main) dayanır. Kararlı ürün davranışı için asıl kaynak [resmî GitHub yayın notlarıdır](https://github.com/NousResearch/hermes-agent/releases).