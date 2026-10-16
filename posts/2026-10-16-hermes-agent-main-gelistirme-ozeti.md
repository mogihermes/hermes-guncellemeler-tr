# Hermes Agent `main` geliştirme özeti — 16 Ekim 2026

> **Kararlılık durumu:** Bu bir sürüm notu değildir. Resmî son sürüm [`v0.22.2`](https://github.com/NousResearch/hermes-agent/releases/tag/v0.22.2); aşağıdakiler `main` dalında bulunan, henüz yeni bir sürüm etiketiyle yayımlanmamış geliştirmelerdir.

- **Karşılaştırma:** [`v0.22.2...main`](https://github.com/NousResearch/hermes-agent/compare/v0.22.2...main)
- **Kapsam:** `v0.22.2` sonrasında görülen kullanıcıyı etkileyen resmî `main` commitleri.

## Öne çıkan geliştirmeler

- **`/loop` geri sayımı:** CLI, TUI ve Desktop'ta canlı çalışma alanına sabit bir `/loop` satırı ile akan geri sayım eklendi; oturum denetim durumu değişince diğer görüntüleyiciler de güncelleniyor. [CLI özelliği](https://github.com/NousResearch/hermes-agent/commit/cba95563d41b7e914af97432f42a0c6ce9391ef6) · [TUI özelliği](https://github.com/NousResearch/hermes-agent/commit/2add194aa7a9991d67bed18ad04e0c41131db091) · [gateway düzeltmesi](https://github.com/NousResearch/hermes-agent/commit/874d1485abc68172e1adfc7d357f3490c708884b)
- **Yapılandırma dayanıklılığı:** Config watcher ile config backup işlemleri arasındaki race condition düzeltildi. [resmî düzeltme](https://github.com/NousResearch/hermes-agent/commit/c3ddf7563bff036227c4b4140a0e61b4aea3fb1e)
- **Telegram ilerleme metni:** İlerleme mesajlarındaki code fence'lerin korunması düzeltildi. [resmî düzeltme](https://github.com/NousResearch/hermes-agent/commit/ecffe12eae3691e728869c77c6f6c0fb7ad97400)
- **Yerel oturum komutları:** Yerel oturumun workspace'i slash komut keşfi ve skill dispatch için bağlandı; `/diff` ile `/rollback` checkpoint'leri yerel oturum politikasından oluşturuluyor. [workspace düzeltmesi](https://github.com/NousResearch/hermes-agent/commit/9de32e7be98ed1cc1be35ff9e81cc12c7375a9d1) · [checkpoint düzeltmesi](https://github.com/NousResearch/hermes-agent/commit/e89706c0202b82aba521b085603adfba7d6d0416)
- **Desktop yolları ve kuyruk:** Windows shell yolları attachment preview öncesinde çözümleniyor; tek harfli WSL dizinleri bridge üzerinde tutuluyor. Yeni pencere ardından gönderilen ileti de yeni sohbete aktarılıyor. [Windows yol düzeltmesi](https://github.com/NousResearch/hermes-agent/commit/8087af8550f9282522d8bdd510468e338814118f) · [WSL düzeltmesi](https://github.com/NousResearch/hermes-agent/commit/8211bb96eddb79d18079d5319a6bfed7255740b7) · [yeni sohbet düzeltmesi](https://github.com/NousResearch/hermes-agent/commit/8c33b4f281e08bb6b229b600e9fa69a5eec2dfaa)
- **Model ve sıkıştırma hata bilgisi:** Solstice için `Gemini 4 Argon` sunuluyor; tüm auxiliary fallback'ler tükendiğinde compression hatası başarısız olan modeli adlandırıyor. [Solstice güncellemesi](https://github.com/NousResearch/hermes-agent/commit/acc3cada0da86c81efc8aa6c5a291989549ca900) · [compression düzeltmesi](https://github.com/NousResearch/hermes-agent/commit/0eeba2d7a2632e11cc72d586ae61ca317664eb40)
- **Docker ve worker bağlantıları:** Docker'da gateway s6 runtime service üzerinden başlatılıyor; managed worker, owner bağlantısı gönderimden önce kapanırsa bir kez yeniden bağlanıyor. [Docker düzeltmesi](https://github.com/NousResearch/hermes-agent/commit/20b8cd75e87d65d7341b04b435d7c2d363ee5afc) · [worker düzeltmesi](https://github.com/NousResearch/hermes-agent/commit/e06087d9d2524fb3d685c61a8afa0590051c7067)

## Kullanıcı için amacı

Bu etiketlenmemiş çalışmalar, loop zamanlamasının tüm arayüzlerde görünür kalmasını; Telegram ve Desktop akışlarının daha güvenilir olmasını; yerel oturum komutları, yapılandırma işlemleri, Docker ve worker bağlantılarındaki hata durumlarının daha iyi yönetilmesini hedefliyor.

## Kaynak

Bu özet yalnızca NousResearch/hermes-agent deposunun açık `main` dalındaki ilgili commitlere ve [karşılaştırma görünümüne](https://github.com/NousResearch/hermes-agent/compare/v0.22.2...main) dayanır. Kararlı ürün davranışı için asıl kaynak [resmî GitHub yayın notlarıdır](https://github.com/NousResearch/hermes-agent/releases).
