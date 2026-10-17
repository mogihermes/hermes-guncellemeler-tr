# Hermes Agent `main` geliştirme özeti — 17 Ekim 2026

> **Kararlılık durumu:** Bu bir sürüm notu değildir. Resmî son sürüm [`v0.22.2`](https://github.com/NousResearch/hermes-agent/releases/tag/v0.22.2); aşağıdakiler `main` dalında bulunan, henüz yeni bir sürüm etiketiyle yayımlanmamış geliştirmelerdir.

- **Karşılaştırma:** [`v0.22.2...main`](https://github.com/NousResearch/hermes-agent/compare/v0.22.2...main)
- **Kapsam:** 16 Ekim özetinden sonra görülen kullanıcıyı etkileyen resmî `main` commitleri.

## Öne çıkan geliştirmeler

- **Yerel modeller:** `llama.cpp b11671` için `Nemotron 3.5 Bolt` yerel model kataloğa eklendi. `Qwen3.8-27B` ile `Nemotron 3.5 Bolt` için DFlash taslakları da eklendi; bu taslaklar model indirilmezse ana model kurulumunu veya runtime güncellemesini başarısız kılmıyor. `Nemotron 3.5 Bolt` yalnızca açıkça seçildiğinde kullanılacak; quickstart'ın otomatik önerisi değil. [resmî özellik commit'i](https://github.com/NousResearch/hermes-agent/commit/0ab43d4f67e41be75f4f6c0fa14a86dbcfd3e5b3) · [depo adı düzeltmesi](https://github.com/NousResearch/hermes-agent/commit/abc84c166f005c428972dcb280a0abd3243b4960) · [taslak indirme hatası düzeltmesi](https://github.com/NousResearch/hermes-agent/commit/9835ebe15c2417228800036a4bea1adc699c49f8)
- **`/undo` ve `/retry`:** Klasik gateway istemcisinde bağlantı yenilemesi kaybolsa bile geri alma işlemi korunuyor; tekrar denemede yanlış mesajın yeniden gönderilmesi önleniyor. [resmî düzeltme](https://github.com/NousResearch/hermes-agent/commit/32abca7155fb2aa726a10845fb4f81049c8bab25)
- **Scratch dizini temizliği:** Arka plan terminali veya Hermes'in başlattığı canlı bir işlem bir boşta scratch dizininde çalışıyorsa işlem artık temizleyici tarafından sonlandırılmıyor; yalnız sahipsiz süreçler temizleniyor. [resmî düzeltme](https://github.com/NousResearch/hermes-agent/commit/7cc1353633e2d8c3113361f21643de37b92f2bc1)
- **ACP editör entegrasyonu:** Tur sırasında seçilen, onay gerektiren model değişikliği tur sınırında editörden onay istiyor; desteklenmeyen kayıtlı komutlar da genel `Internal error` yerine adlandırılmış yanıt veriyor. [model seçimi düzeltmesi](https://github.com/NousResearch/hermes-agent/commit/cc9442326c10d45d667234dca7051854b673d5e4) · [komut yanıtı düzeltmesi](https://github.com/NousResearch/hermes-agent/commit/69f80031dee9afb07a0b4f4593a80ab7da7807cf)

## Kullanıcı için amacı

Bu etiketlenmemiş çalışmalar, uygun donanımda daha fazla yerel model seçeneği ve spekülatif çözümleme sunmayı; komut tekrarları, arka plan süreçleri ve ACP tabanlı editör akışlarındaki hata durumlarını daha güvenilir yönetmeyi hedefliyor.

## Kaynak

Bu özet yalnızca NousResearch/hermes-agent deposunun açık `main` dalındaki ilgili commitlere ve [karşılaştırma görünümüne](https://github.com/NousResearch/hermes-agent/compare/v0.22.2...main) dayanır. Kararlı ürün davranışı için asıl kaynak [resmî GitHub yayın notlarıdır](https://github.com/NousResearch/hermes-agent/releases).
