# Hermes Agent `main` geliştirme özeti — 6 Ekim 2026

> **Kararlılık durumu:** Bu bir sürüm notu değildir. Resmî son sürüm hâlâ [`v2026.9.24`](https://github.com/NousResearch/hermes-agent/releases/tag/v2026.9.24); aşağıdakiler `main` dalında bulunan, henüz yeni bir sürüm etiketiyle yayımlanmamış geliştirmelerdir.

- **Karşılaştırma:** [`v2026.9.24...main`](https://github.com/NousResearch/hermes-agent/compare/v2026.9.24...main)
- **Kapsam:** 5 Ekim 2026 özetinden sonra gelen kullanıcıyı etkileyen resmî commitler.

## Öne çıkan geliştirmeler

- **Kısmi klonlarda güncelleme denetimi:** Eski Git sürümlerinin `GIT_NO_LAZY_FETCH` değerini yok saydığı kısmi klonlarda, bekletilmiş dal denetimi artık `git cherry` çalıştırmıyor. `remote.*.promisor` veya `extensions.partialclone` yerel yapılandırmasından kısmi klonu algılıyor ve commit sayısıyla yetiniyor; bu sayede `git 2.43` üzerinde sınırsız lazy fetch engelleniyor. (`#124767`, `git 2.43`, `GIT_NO_LAZY_FETCH`) [resmî commit](https://github.com/NousResearch/hermes-agent/commit/86bdb75b2bbe3a58291f6b70d74872522614e61d)
- **Eklenti TTS akışında örnekleme hızı ve yönlendirme düzeltmesi:** PCM akışlı eklentilerin `stream_sample_rate` değeri artık bir kez, sonlu ve `>= 1 Hz` olarak doğrulanıyor; `nous` eklenti yönlendirmesinden ayrılıyor. Bu değişiklik, geçersiz hız yüzünden sesin hiç çalmamasını ve `tts.streaming.provider: nous` ayarının eş adlı bir eklentiye yönlenmesini önlüyor. [resmî commit](https://github.com/NousResearch/hermes-agent/commit/f9798bcf9bceca7f88a64a66aa652cf9e2b5cffa)

## Kullanıcı için amacı

Bu etiketlenmemiş düzeltmeler, belirli kısmi Git klonlarında güncelleme sırasında aşırı veri çekimini önlemeyi ve eklenti tabanlı akışlı TTS kullanımında daha tutarlı, hataya dayanıklı sesli çıktı sağlamayı hedefliyor.

## Kaynak

Bu özet yalnızca NousResearch/hermes-agent deposunun açık `main` dalındaki ilgili commitlere ve [karşılaştırma görünümüne](https://github.com/NousResearch/hermes-agent/compare/v2026.9.24...main) dayanır. Kararlı ürün davranışı için asıl kaynak [resmî GitHub yayın notlarıdır](https://github.com/NousResearch/hermes-agent/releases).
