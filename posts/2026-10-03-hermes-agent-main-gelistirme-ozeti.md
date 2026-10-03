# Hermes Agent `main` geliştirme özeti — 3 Ekim 2026

> **Kararlılık durumu:** Bu bir sürüm notu değildir. Resmî son sürüm hâlâ [`v2026.9.24`](https://github.com/NousResearch/hermes-agent/releases/tag/v2026.9.24); aşağıdakiler `main` dalında bulunan, henüz yeni bir sürüm etiketiyle yayımlanmamış geliştirmelerdir.

- **Karşılaştırma:** [`v2026.9.24...main`](https://github.com/NousResearch/hermes-agent/compare/v2026.9.24...main)
- **Kapsam:** 2 Ekim 2026 özetinden sonra gelen kullanıcıyı etkileyen resmî commitler.

## Öne çıkan geliştirmeler

- **Araç kurulumu / PM:** Değiştirilen araç girdisi kaldırılırken salt-okunur bitlerinin temizlenmesi Windows `unlink`/`rmdir` izin hatalarıyla sınırlandırıldı; POSIX hataları normal `rmtree` davranışıyla yükseltiliyor. [salt-okunur temizleme](https://github.com/NousResearch/hermes-agent/commit/be431788dd81a24492210df537658c55f9ba7688) · [Windows'a sınırlandırma](https://github.com/NousResearch/hermes-agent/commit/eb7e8620324b32424c06218f6a28094df2e921f8)
- **Desktop bot profilleri:** Çoklu bağlantı bot listelerinde kimlik atıf izleri eklendi; bot adı kendi backend'inden alınıyor ve profil düzenleme yalnızca düzenlenen alanları kaydediyor. [izler](https://github.com/NousResearch/hermes-agent/commit/c55a6e3d9fb22fa56537f2251aea82ce47930a8c) · [bot adı](https://github.com/NousResearch/hermes-agent/commit/33261470752f9ab3ec72f85d327f61a8e416cc01) · [profil kaydı](https://github.com/NousResearch/hermes-agent/commit/7229edf52aabb45d528952e34698eff7240be844)
- **Telegram kod blokları:** Çitli kod bloğu algılama ankrajları genişletilerek satır içi ve girintili blokların korunması hedefleniyor. [resmî commit](https://github.com/NousResearch/hermes-agent/commit/c82abc309a3f956c3d02104aa9cd2b21ac98c7df)
- **MCP süreç temizliği:** Ölmüş bir MCP sunucusunun alt süreçlerinin yeniden toplanmasına yönelik düzeltme eklendi. [resmî commit](https://github.com/NousResearch/hermes-agent/commit/d526f14714ce8a95cafd7f3a95d1eab5b6e0b910)
- **Kanban pano seçimi:** Açık pano geçersiz kılmasının çitlenmemiş çağrılarla sınırlandırılmasına yönelik düzeltme var. [resmî commit](https://github.com/NousResearch/hermes-agent/commit/387c78c8f7f2f552605de006ccec13ee9427d7a2)

## Kullanıcı için amacı

Bu değişiklikler henüz etiketli sürümde değildir; araç güncellemelerinin dosya temizliği, çoklu bot profil yönetimi, Telegram’daki kod blokları ve MCP süreç yaşam döngüsünün daha öngörülebilir olmasını hedefliyor.

## Kaynak

Bu özet yalnızca NousResearch/hermes-agent deposunun açık `main` dalındaki ilgili commit başlıklarına ve [karşılaştırma görünümüne](https://github.com/NousResearch/hermes-agent/compare/v2026.9.24...main) dayanır. Kararlı ürün davranışı için asıl kaynak [resmî GitHub yayın notlarıdır](https://github.com/NousResearch/hermes-agent/releases).
