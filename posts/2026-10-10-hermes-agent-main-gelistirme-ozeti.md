# Hermes Agent `main` geliştirme özeti — 10 Ekim 2026

> **Kararlılık durumu:** Bu bir sürüm notu değildir. Resmî son sürüm [`v0.21.6`](https://github.com/NousResearch/hermes-agent/releases/tag/v0.21.6); aşağıdakiler `main` dalında bulunan, henüz yeni bir sürüm etiketiyle yayımlanmamış geliştirmelerdir.

- **Karşılaştırma:** [`v0.21.6...main`](https://github.com/NousResearch/hermes-agent/compare/v0.21.6...main)
- **Kapsam:** 7 Ekim 2026 özetinden sonra gelen kullanıcıyı etkileyen resmî commitler.

## Öne çıkan geliştirmeler

- **Kaynak kurulumlarda kararlı kanal varsayılanı:** Resmî kaynaktan kurulmuş kopyalarda `hermes update` ve Desktop güncelleme düğmesi artık commit commit `main` izlemek yerine yayımlanmış `vX.Y.Z` sürümleri arasında ilerliyor. `hermes update --set-channel stable` kullanılabiliyor; fork, mirror ve checkout'suz ağaçlar `main` davranışını koruyor. [varsayılan kanal](https://github.com/NousResearch/hermes-agent/commit/6a92a2aa4928175041e6bb04922d69d3f6e49eda) · [kararlı sürüm kaynağı](https://github.com/NousResearch/hermes-agent/commit/158cd52a6bc6747668e3b4039db9ecff08853b79)
- **Güncellemede geri alma güvenliği:** Sığ (shallow) veya çevrimdışı bir checkout, sürümden ilerideyse ilişki kanıtlanamadığında artık geriye taşınmıyor; yalnızca tam geçmişteki kanıt veya GitHub'ın `behind`/`diverged` sonucu hareket ettiriyor. [resmî düzeltme](https://github.com/NousResearch/hermes-agent/commit/dce1e9b37581dd62e480a9064dc04a709c2940d3)
- **Beceri değişikliklerinin görünürlüğü ve güvenliği:** Çalışan süreç, başka bir süreç tarafından yazılan `SKILL.md`/`DESCRIPTION.md` değişikliğini yeniden başlatma olmadan indeksine alıyor; değişiklik notu her yüzeyde tur başına bir kez bildiriliyor. Topluluk becerilerinde iç kabuk parçacıkları için güven kapısı iç içe/cross-profile dizinleri kapsıyor ve okunamayan kilitte güvenli biçimde kapalı kalıyor. [indeks yenileme](https://github.com/NousResearch/hermes-agent/commit/c098b2bf1ddad46c24c6ec01f5d8754555d23f6d) · [tur bildirimi](https://github.com/NousResearch/hermes-agent/commit/097fcaa1deec1903ece5abce8919c9937a57f3f4) · [iç kabuk güvenliği](https://github.com/NousResearch/hermes-agent/commit/587f638e5256fe33b3a1667979ee416e53857eb6)
- **Python ve arayüz güncelleme düzeltmeleri:** Çekirdek modüller Python 3.11–3.13 üzerinde yeniden içe aktarılabiliyor. Ayrıca Desktop'a özgü Node bağımlılığı başarısız olursa kaynak güncellemesi TUI ve web UI derlemelerini artık engellemiyor. [Python 3.11–3.13 düzeltmesi](https://github.com/NousResearch/hermes-agent/commit/a274d3388f882f751099cd9bd5ac2988bfaf8391) · [TUI/web UI güncelleme düzeltmesi](https://github.com/NousResearch/hermes-agent/commit/73162b00eefde3794bed0afb53d84a19c0eed230)
- **Relay telemetri varsayılanı:** Taşınmış Relay yapılandırmalarında Relay 0.10'un OTLP otomatik dışa aktarımı kapatılıyor; ilgili ortam uç noktaları mevcut olduğunda prompt ve yanıt mesajlarını taşıyabilen trace/log/metric dışa aktarımı böylece varsayılan olarak başlamıyor. [resmî düzeltme](https://github.com/NousResearch/hermes-agent/commit/5ba559c9e4b1c8397df7788e319ab634144ca728)

## Kullanıcı için amacı

Bu etiketlenmemiş geliştirmeler, kaynak kurulumların daha öngörülebilir güncellenmesini, beceri değişikliklerinin güvenli biçimde etkinleşmesini ve desteklenen eski Python sürümlerinde/başsız arayüzlerde çalışabilirliği hedefliyor.

## Kaynak

Bu özet yalnızca NousResearch/hermes-agent deposunun açık `main` dalındaki ilgili commitlere ve [karşılaştırma görünümüne](https://github.com/NousResearch/hermes-agent/compare/v0.21.6...main) dayanır. Kararlı ürün davranışı için asıl kaynak [resmî GitHub yayın notlarıdır](https://github.com/NousResearch/hermes-agent/releases).
