# Hermes Agent `main` geliştirme özeti — 4 Kasım 2026

> **Kararlılık durumu:** Bu bir sürüm notu değildir. Resmî son sürüm [`v0.22.7`](https://github.com/NousResearch/hermes-agent/releases/tag/v0.22.7); aşağıdakiler `main` dalında bulunan, henüz yeni bir sürüm etiketiyle yayımlanmamış geliştirmelerdir.
>
> **Kapsam:** 3 Kasım (veya önceki özet) özetinden sonra görülen kullanıcıyı etkileyen resmî `main` commitleri.

## Öne çıkan geliştirmeler

- **Gateway odaları başarısız bot listesi bile survive eder, asla yeniden doğmaz** - `6d765b570558e2c145af9f7f89da0e1b8f8fd870`: Failed or still-loading bot list gateway rooms behind the bot-list error göstermez. `groups.list` oku, kullanıcı odayı açana kadar nothing yazar. Odadan ayrılan (disbanded) room, oku before disband olmuş olsa bile veya sonradan failed re-read tuttuğu halde, gateway listing durdurulana kadar gizli kalır. Gateway odası never bir Desktop odası records by name okur, böylece aynı isimdeki Desktop room oda section veya saved order verir. Desktop oku üzerinde move up/down, sadece Desktop oku okur, böylece komşu gateway oda nothing enabled button yapmaz. A room an open view working rapor eder veya ihtiyaç duyarsa Active filter past recency window içinde kalır.

- **Gateway Group Chats roster'a yerleştirilir, Refresh button yok** - `e98b60f8b80e9590d7fb7e36bcaffaf2d291a833`: Bots pannede "Refresh gateway groups" ghost button ve toolbar ö gateway rooms'ü adlı unlabeled strip kalkmıştı. A connection'ın registry id'si yoksa (env veya legacy remote), "Canonical groups require an explicit connection" içaç metin gösterilirdi. Dialogdan oluşturulan bir room, Refresh'a kadar gösterilmedi. Gateway rooms, Desktop group chats ile aynı tile, name, age ve member line ile roster rows olarak olur, sorted and filtered with the rest. Sağ tık Open/Delete preserved. List 10 s poll, her socket veya source değişikliği ve create/disband sonrası kendini günceller, böylece button gerekmez. Failed re-read last good list tutar; registry id'si olmayan connection ya da gateway Group Chats olmayan backend, hiç listing gösterir ve hiçbir şey söylemez.

- **Inline report, goal'a bağlanır ve target switch'ta drop ediliyor** - `71736c9f32597bbca9d89cede5aa136e55946b2f`: Inline report, belonging failure'a bağlanır. Target switch (backend failure gösterilirken macOS Check for Updates'i değiştirirsen), eski report'in hiç görünmez link ile bitse ve daha sonraki client failureBackend raporunu gösterse, box now drops its report on unmount ve target tarafından keyed olunduğu için kapatma, retry ve target switch tüm üç durumlu raporu doğru keyer.

## Kullanıcı için amacı

Bu etiketlenmemiş çalışma; Desktop gateway güncelleme raporlarının hata bağlamına bağlanması, gateway Group Charts'in Refresh butonunun kaldırılması ve roster satırı olarak düzenlenmesi, failed bot list altında gateway odalarının kalıcı remaining durumunun sağlanması hedefliyor. Kullanıcılar artık hata raporlarını view ederken daha duidelijk feedback alacak ve gateway odaları sorunsuzca çalışacak.

## Kaynak

Bu özet yalnızca NousResearch/hermes-agent deposunun açık `main` dalındaki ilgili commitlere ve [v0.22.7...main karşılaştırma görünümüne](https://github.com/NousResearch/hermes-agent/compare/v0.22.7...main) dayanır. Kararlı ürün davranışı için asıl kaynak [resmî GitHub yayın notlarıdır](https://github.com/NousResearch/hermes-agent/releases).