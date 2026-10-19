# Hermes Agent `main` geliştirme özeti — 19 Ekim 2026

> **Kararlılık durumu:** Bu bir sürüm notu değildir. Resmî son sürüm [`v0.22.2`](https://github.com/NousResearch/hermes-agent/releases/tag/v0.22.2); aşağıdakiler `main` dalında bulunan, henüz yeni bir sürüm etiketiyle yayımlanmamış geliştirmelerdir.

- **Karşılaştırma:** [`v0.22.2...main`](https://github.com/NousResearch/hermes-agent/compare/v0.22.2...main)
- **Kapsam:** 18 Ekim özetinden sonra görülen kullanıcıyı etkileyen resmî `main` commitleri.

## Öne çıkan geliştirmeler

- **Gateway’de kaybolan otomasyon turları:** Kaybolan bir otomasyon turu artık onu sınırlayan çıkışta sonuçlandırılıyor. Bekleyen mesajlar devam edebiliyor; `discard` komutu ilgili kayıp turu reddetmek için tüm yüzeylerde sunuluyor. [resmî gateway commit'i](https://github.com/NousResearch/hermes-agent/commit/eea83bb603c397396acaf6cc453cf3012a8524aa)
- **Yeniden bağlanmada bekleyen istemler:** Eski bağlantı yöntemini kullanan bir yeniden bağlanmadan sonra bekleyen istemler tekrar oynatılıyor. [resmî gateway commit'i](https://github.com/NousResearch/hermes-agent/commit/fa2836d1ee92f274d3670591ed92e3b0fa296514)
- **TUI komutları ve kesintiler:** Ink TUI’de `/voice`, `/reload-mcp`, `/config`, `/save` ve `/timestamps` gateway üzerinden çalıştırılıyor. Kesilen turların yeniden başlatmadan kaynaklandığı açıkça bildiriliyor; `!command` reddinde de backend adı gösteriliyor. [resmî TUI commit'i](https://github.com/NousResearch/hermes-agent/commit/18b79b2ba8e9f98f928412e934dce5925f26ab32) · [resmî kesinti commit'i](https://github.com/NousResearch/hermes-agent/commit/0bd184f3af33a903f1a039dd287bc7709ba3ebb0)
- **Profil başına tarayıcı bağlantısı:** Bağlantı kesilince bir profil kendi `BROWSER_CDP_URL` değerine geri dönüyor; başka bir profilin başlatma ortamındaki değer kullanılmıyor. [resmî tarayıcı commit'i](https://github.com/NousResearch/hermes-agent/commit/45b15aac70d339eaa65662bc93d2aefb9640c2fd)
- **Ses yakalama çakışması:** İkinci bir oturum, kullanımda olan mikrofon yakalamasını devralamıyor; istek reddediliyor. [resmî TUI commit'i](https://github.com/NousResearch/hermes-agent/commit/e3bf070e6005e6d21f1a824c52563fd513a0aa83)

## Kullanıcı için amacı

Bu etiketlenmemiş çalışma; gateway/TUI oturumlarının kesinti, yeniden bağlanma, profil ayrımı ve ses yakalama çakışmalarında daha öngörülebilir davranmasını hedefliyor.

## Kaynak

Bu özet yalnızca NousResearch/hermes-agent deposunun açık `main` dalındaki ilgili commitlere ve [karşılaştırma görünümüne](https://github.com/NousResearch/hermes-agent/compare/v0.22.2...main) dayanır. Kararlı ürün davranışı için asıl kaynak [resmî GitHub yayın notlarıdır](https://github.com/NousResearch/hermes-agent/releases).
