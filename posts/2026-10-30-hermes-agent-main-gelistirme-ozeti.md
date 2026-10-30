# Hermes Agent `main` geliştirme özeti — 30 Ekim 2026

> **Kararlılık durumu:** Bu bir sürüm notu değildir. Resmî son sürüm [`v0.22.5`](https://github.com/NousResearch/hermes-agent/releases/tag/v0.22.5); aşağıdakiler `main` dalında bulunan, henüz yeni bir sürüm etiketiyle yayımlanmamış geliştirmelerdir.

- **Karşılaştırma:** [`v0.22.5...main`](https://github.com/NousResearch/hermes-agent/compare/v0.22.5...main)
- **Kapsam:** 28 Ekim (veya önceki özet) özetinden sonra görülen kullanıcıyı etkileyen resmî `main` commitleri.

## Öne çıkan geliştirmeler

- **Error card v2 — severity ve eylem butonları** - `ef35e8b9`: İnline hata kartı Error System Overhaul tasarımına güncellendi. Engelleme (blocking) vs. degrade (degraded) şiddet derecelendirmesi, birincil eylem ve en fazla biriksel seçenek, hata ayrıntıların görüntüleneebilmesi için toggle, tüm 8 locale için çeviri. Kart, sessiz oturum toaster'ını engeller; kredisi bitmişse compose banneryi gösterir.

- **Discord /model picker otomatik kapatma** - `606b8345`: /model picker açıkken cevap verildikten sonra bırakılıyordu. Art picker hemen kapatılıyor.

- **Plugin doktor: sadece doğrulanmış eklentiyi stade etme** - `903230b1`: `doctor` komutu sadece o anki validated plugin'i stade ediyor, home dizini değil.

- **Plugin home kopyası uyarısı** - `831637fe`: Sadece bir home içeren projeler kopyalandığında uyarı verilmiyordu. Art home'u merece plugin checkout olarak işleniyor.

- **BotDesktop: takeover idle screen durumu** - `e298669b`: Bir takeover ekranı kullanıldığında idle sayacı sıfırlanıyor ve ekran kapatılıyor.

- **BotDesktop: abandonned human lease serbest bırakma** - `d4046152`: Yasaklanınca bırakıksız human lease'lar serbest bırakılıyor.

- **BotDesktop: infinite idle window önleniyor** - `8f40eac4`: Sonsuz idle window'lar start() hatası vermez, kapatılıyor.

## Kullanıcı için amacı

Bu etiketlenmemiş çalışma; hata kartı deneyiminin modernleştirilmesini, Discord model picker'ın daha temiz bir closure sağlamasını, plugin doctor'ın daha doğru plugin seçim yapmasını ve botDesktop idle yönetiminin daha güvenilir olmasını hedefliyor.

## Kaynak

Bu özet yalnızca NousResearch/hermes-agent deposunun açık `main` dalındaki ilgili commitlere ve [karşılaştırma görünümüne](https://github.com/NousResearch/hermes-agent/compare/v0.22.5...main) dayanır. Kararlı ürün davranışı için asıl kaynak [resmî GitHub yayın notlarıdır](https://github.com/NousResearch/hermes-agent/releases).