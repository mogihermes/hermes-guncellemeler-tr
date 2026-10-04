# Hermes Agent `main` geliştirme özeti — 4 Ekim 2026

> **Kararlılık durumu:** Bu bir sürüm notu değildir. Resmî son sürüm hâlâ [`v2026.9.24`](https://github.com/NousResearch/hermes-agent/releases/tag/v2026.9.24); aşağıdakiler `main` dalında bulunan, henüz yeni bir sürüm etiketiyle yayımlanmamış geliştirmelerdir.

- **Karşılaştırma:** [`v2026.9.24...main`](https://github.com/NousResearch/hermes-agent/compare/v2026.9.24...main)
- **Kapsam:** 3 Ekim 2026 özetinden sonra gelen kullanıcıyı etkileyen resmî commitler.

## Öne çıkan geliştirmeler

- **SSH ile devam ettirilen TUI oturumları:** Devam ettirilen SSH oturumlarının Hermes sunucusunun dizinlerinde çalışmasını engelleyen bir düzeltme eklendi (`#132622`; `#132025` yerine geçer). [resmî commit](https://github.com/NousResearch/hermes-agent/commit/819cc3cbe02104c420ea32f1f1a924247d42eaf8)
- **Profil dışa aktarımlarında kimlik bilgileri:** `.docker`, `.azure`, `.config/gh` ve `.config/gcloud` artık profil dışa aktarımına dahil edilmiyor; böylece kayıt defteri, GitHub ve Google Cloud kimlik verilerinin taşınması engelleniyor. [resmî commit](https://github.com/NousResearch/hermes-agent/commit/404b1fec55c02edc4f39dad574f2344aa49c3123)
- **Home Assistant katalog eklentisi:** Home Assistant gateway platformu ve `ha_*` araçları, `NousResearch/hermes-homeassistant` üzerinden bağımsız katalog eklentisi olarak ekleniyor. Eklenti yokken `homeassistant:` hedefi için hata iletisi etkin profil komutunu gösteriyor: `hermes [-p <profile>] plugins install homeassistant`. [katalog commit'i](https://github.com/NousResearch/hermes-agent/commit/403fc8beee087e2a6b83d2f2f3b353cfb54dcb62) · [kurulum yönlendirmesi](https://github.com/NousResearch/hermes-agent/commit/f7689f40a400d5fa0185dc0715ef927d73cbfcb1)
- **Discord davet izinleri:** Kullanılmayan `Use External Emojis` izni çıkarıldı; sihirbaz davet değeri `309241171008` → `309240908864`, önerilen belge satırı `309238025280` → `309237763136` olarak düzeltildi. [resmî commit](https://github.com/NousResearch/hermes-agent/commit/937f23db2d707cde1c87337fde3aafee514d117c)

## Kullanıcı için amacı

Bu etiketlenmemiş değişiklikler, SSH oturumlarının doğru çalışma dizinini korumayı, profil dışa aktarımlarındaki hassas kimlik verilerini sınırlamayı ve Home Assistant ile Discord kurulum akışlarını daha açık ve güvenli hâle getirmeyi hedefliyor.

## Kaynak

Bu özet yalnızca NousResearch/hermes-agent deposunun açık `main` dalındaki ilgili commitlere ve [karşılaştırma görünümüne](https://github.com/NousResearch/hermes-agent/compare/v2026.9.24...main) dayanır. Kararlı ürün davranışı için asıl kaynak [resmî GitHub yayın notlarıdır](https://github.com/NousResearch/hermes-agent/releases).
