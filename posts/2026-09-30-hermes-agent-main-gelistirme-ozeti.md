# Hermes Agent `main` geliştirme özeti — 30 Eylül 2026

> **Kararlılık durumu:** Bu yazı bir sürüm notu değildir. Resmî son sürüm hâlâ [`v2026.9.24`](https://github.com/NousResearch/hermes-agent/releases/tag/v2026.9.24); aşağıdaki değişiklikler `main` dalındaki, henüz yeni bir sürüm etiketiyle yayımlanmamış geliştirmelerdir.

- **Karşılaştırma:** [`v2026.9.24...main`](https://github.com/NousResearch/hermes-agent/compare/v2026.9.24...main)
- **Amaç:** Resmî sürüm notu beklenirken, kullanıcıyı etkileyebilecek belirgin geliştirmeleri erken görünür kılmak.

## Öne çıkan geliştirmeler

- **Onay ve soru kartları:** Bir çalışma sırasında gösterilen approval/clarify kartlarının yanıt gelene kadar açık kalması için ortak altyapı ve TUI/Desktop tarafında geliştirmeler yapılıyor. Bu, kullanıcı yanıtı bekleyen akışların erken kapanmasını önlemeyi hedefliyor. [approval](https://github.com/NousResearch/hermes-agent/commit/e57fa35) · [TUI/Desktop](https://github.com/NousResearch/hermes-agent/commit/bd50166)
- **Cron ve Desktop güvenilirliği:** Cron çalıştırmalarında yazma yetkisi scheduler sahipliğine bağlanıyor; kapanmamış eski çalıştırmalar yalnız-okunur açılıyor. Bu değişiklikler eşzamanlı cron görünümü ve hatalı eski oturumlar için koruma sağlıyor. [scheduler ownership](https://github.com/NousResearch/hermes-agent/commit/46370fd) · [read-only latch](https://github.com/NousResearch/hermes-agent/commit/3df634b) · [never-closed runs](https://github.com/NousResearch/hermes-agent/commit/7f90f07)
- **Bot ve Discord yönlendirmesi:** Bot relay hedef kapsamı reddedildiğinde nedenin ayrıştırılması ve Discord yönlendirme girdisinde işaretleyiciler yoksa oturum satırından geri kazanım üzerinde çalışmalar var. [bot relay](https://github.com/NousResearch/hermes-agent/commit/a802212) · [Discord fallback](https://github.com/NousResearch/hermes-agent/commit/cc1e4e9)
- **Model ve kimlik bilgisi yönetimi:** Codex OAuth seçicide `gpt-6.1-sol-900k` varyantı ekleniyor; kota yoklamasında döndürülmüş Codex tokenlarının cooldown temizlenirken korunmasına yönelik düzeltme var. [model picker](https://github.com/NousResearch/hermes-agent/commit/5bb6127) · [credential pool](https://github.com/NousResearch/hermes-agent/commit/8ec0f62)
- **Desktop kararlılığı:** Windows `fs.watch` olay fırtınasında polling fallback’i ve başarısız watch snapshot’ını boş klasörden ayıran düzeltmeler ekleniyor. [watch storm](https://github.com/NousResearch/hermes-agent/commit/3ae6287) · [failed snapshot](https://github.com/NousResearch/hermes-agent/commit/8a0aaf9)

## Kullanıcı için amacı

Bunlar henüz sürüm etiketi taşımadığı için günlük kullandığın kuruluma hemen gelmiş sayılmaz. Özellikle cron, bot yönlendirmesi ve kullanıcı onayı akışlarında iyileştirme birikiyor; bir sonraki resmî sürüm çıktığında ayrıca tam Türkçe sürüm notu yayımlanacak.

## Kaynak

Bu özet yalnızca NousResearch/hermes-agent deposunun açık `main` dalındaki commit başlıklarına ve karşılaştırma görünümüne dayanır. Kararlı ürün davranışı için asıl kaynak, [resmî yayın notlarıdır](https://github.com/NousResearch/hermes-agent/releases).
