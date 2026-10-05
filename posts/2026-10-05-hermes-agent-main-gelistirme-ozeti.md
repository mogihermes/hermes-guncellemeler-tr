# Hermes Agent `main` geliştirme özeti — 5 Ekim 2026

> **Kararlılık durumu:** Bu bir sürüm notu değildir. Resmî son sürüm hâlâ [`v2026.9.24`](https://github.com/NousResearch/hermes-agent/releases/tag/v2026.9.24); aşağıdakiler `main` dalında bulunan, henüz yeni bir sürüm etiketiyle yayımlanmamış geliştirmelerdir.

- **Karşılaştırma:** [`v2026.9.24...main`](https://github.com/NousResearch/hermes-agent/compare/v2026.9.24...main)
- **Kapsam:** 4 Ekim 2026 özetinden sonra gelen kullanıcıyı etkileyen resmî commitler.

## Öne çıkan geliştirmeler

- **İnsan girdisi bekleyen eklentiler için kancalar:** Eklentiler için `on_human_input_request` ve `on_human_input_resolved` kancaları eklendi. Bu çift; `sudo`, açıklama isteği ve onay istemlerinde çalışır; `kind`, `request_id`, `session_id`, `session_key`, `platform`, `prompt` bilgilerini iletir; çözülme olayında `outcome` da eklenir. `prompt` zorunlu olarak redakte edilir; yazılan parolalar ve açıklama yanıtları iletilmez. (`#132333`) [resmî commit](https://github.com/NousResearch/hermes-agent/commit/c958e1a7b97c3854a85413ee682e034cf4bf7529)
- **Eklentiler için cron çalışma bağlamı:** `ctx.current_cron_execution()` artık bir eklentinin hangi cron çalışmasında olduğunu bildirir. Sağlanan `CronExecution`, iş kimliği/adı, çalışma kimliği, kaynak, planlanan an, başlangıç zamanı ve profili içerir; elle çalıştırılan `hermes cron run` ile planlanmış tetiklemeyi ayırmayı sağlar. (`#130722`) [resmî commit](https://github.com/NousResearch/hermes-agent/commit/61f8365da7564c44d061d8c0107c658f8633d71f)

## Kullanıcı için amacı

Bu etiketlenmemiş değişiklikler, eklentilerin hassas insan girdisini açığa çıkarmadan bildirim/izleme yapabilmesini ve güvenlik politikalarının planlanmış cron çalışmalarıyla elle tetiklenen çalışmaları ayırabilmesini hedefliyor.

## Kaynak

Bu özet yalnızca NousResearch/hermes-agent deposunun açık `main` dalındaki ilgili commitlere ve [karşılaştırma görünümüne](https://github.com/NousResearch/hermes-agent/compare/v2026.9.24...main) dayanır. Kararlı ürün davranışı için asıl kaynak [resmî GitHub yayın notlarıdır](https://github.com/NousResearch/hermes-agent/releases).
