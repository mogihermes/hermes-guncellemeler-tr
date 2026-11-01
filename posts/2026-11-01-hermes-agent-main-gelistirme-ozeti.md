# Hermes Agent `main` geliştirme özeti — 1 Kasım 2026

> **Kararlılık durumu:** Bu bir sürüm notu değildir. Resmî son sürüm [`v0.22.5`](https://github.com/NousResearch/hermes-agent/releases/tag/v0.22.5); aşağıdakiler `main` dalında bulunan, henüz yeni bir sürüm etiketiyle yayımlanmamış geliştirmelerdir.

- **Karşılaştırma:** [`v0.22.5...main`](https://github.com/NousResearch/hermes-agent/compare/v0.22.5...main)
- **Kapsam:** 30 Ekim (veya önceki özet) özetinden sonra görülen kullanıcıyı etkileyen resmî `main` commitleri.

## Öne çıkan geliştirmeler

- **Clarify display benzersizliği** - `a4994d4e`: Seçeneklerin display string'leri birbirine karışmayacak şekilde özelleştirildi. İki ham seçenek aynı display (örneğin `***`) sanitize edildiğinde, model her iki seçeneği de distingo (ayrılaştırıcı) suffix'lerle (`(2)`, `(3)`) seçebiliyor. Bu, pick mapping hatalarını önler.

- **/model reset TUI/CLI** - `65effb1e`, `66c48cb1`, `5bb7bdc7`: Kullanıcının oturum modeli pinini kaybederek geçici olarak temizlemesi, kanoni TUI, Desktop ve CLI'lerde desteklendi. `model reset` komutu artık seçenek gösterir ve geçmişi koruyarak modeli sıfırlar.

- **Photon iMessage ayarlamaları** - `5d9b27cd`, `d47a49d4`, `a97f13ff`, `9bc94eb2`: iMessage opt-in akışı güncellendi. Numara routes olduğunda "complete" mesajı gösterilir, henüz routes olmadan "saved-not-live" sonu doğrulandı. Başlangıç mesajı ile opt-in başarılı olduğunda gate işlemi gerçekleşir.

- **Telegram notice improvements** - `631b00c3`, `61794f3f`, `5bb0e7d8`: Kanal/post bildirimleri "?" eki kaldırıldı. Bilinmeyen yazarlı reply'lar groups'ta silence marker'ı gösterir. Voice notes ve audio files için ses eksikliği uyarısı güncellendi.

- **Gateway room allow_silence** - `73da1800`, `33cf2037`: Odadaki sessizlik seçeneği gateway konfigürasyonuna göre değerlendirilir. Failed room silence receipt artık error'a dönüşmez.

- **Plugin doktor güncellemesi** - `903230b1`: `doctor` komutu artık home dizini değil, validated plugin'i stade eder.

- **BotDesktop idle yönetimi** - `e298669b`, `d4046152`, `8f40eac4`: Takeover ekranı kullanıldığında idle sayacı sıfırlanır ve ekran kapatılır. Yasaklandığında bırakıksız human lease'lar serbest bırakılır. Sonsuz idle window'lar engellenir.

- **Error card v2 iyileştirmeleri** - (Devam eden çalışma, önceki özette de belirtildi): Engelleme/degrade şiddet derecelendirmesi, birincil eylem, toggle'lı ayrıntılar ve 8 locale çeviri.

## Kullanıcı için amacı

Bu etiketlenmemiş çalışma; clarify display'ın daha güvenilir pick mapping'i, /model reset özelliğinin TUI/Desktop/CLI'lerde çalışması, iMessage ayarlamalarının daha akıcı olması ve botDesktop idle yönetiminin daha stabil olması hedefliyor.

## Kaynak

Bu özet yalnızca NousResearch/hermes-agent deposunun açık `main` dalındaki ilgili commitlere ve [karşılaştırma görünümüne](https://github.com/NousResearch/hermes-agent/compare/v0.22.5...main) dayanır. Kararlı ürün davranışı için asıl kaynak [resmî GitHub yayın notlarıdır](https://github.com/NousResearch/hermes-agent/releases).