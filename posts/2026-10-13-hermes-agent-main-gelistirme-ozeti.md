# Hermes Agent `main` geliştirme özeti — 13 Ekim 2026

> **Kararlılık durumu:** Bu bir sürüm notu değildir. Resmî son sürüm [`v0.21.7`](https://github.com/NousResearch/hermes-agent/releases/tag/v0.21.7); aşağıdakiler `main` dalında bulunan, henüz yeni bir sürüm etiketiyle yayımlanmamış geliştirmelerdir.

- **Karşılaştırma:** [`v0.21.7...main`](https://github.com/NousResearch/hermes-agent/compare/v0.21.7...main)
- **Kapsam:** `v0.21.7` sonrasında görülen kullanıcıyı etkileyen resmî `main` commitleri.

## Öne çıkan geliştirmeler

- **Desktop clarify yanıtları:** Composer'a yazılan metin, bekleyen bir clarify card için yanıt olarak işleniyor. [resmî düzeltme](https://github.com/NousResearch/hermes-agent/commit/df930df60c0849071ce05dc5a0fcc6ad1df5bb76)
- **MCP OAuth park durumu:** Park edilmiş bir OAuth sunucusu, her yeni oturumda geçersiz refresh token'ını yeniden oynatmıyor. [resmî düzeltme](https://github.com/NousResearch/hermes-agent/commit/f7b26efc2ffa9c1380a7b8c3fad8c7331ab802e3)
- **Solstice model seçenekleri:** Solstice sağlayıcısında `Gemini 3.1 Pro`, `Gemini 3.8 Flash` ve `Gemini 3.5 Flash Lite` sunuluyor. [resmî düzeltme](https://github.com/NousResearch/hermes-agent/commit/b605c79ab2401bf39ebc1e413fcca43fe234ff2a)
- **Bağlayıcı dizini:** `manage_connections` görünümü için bir directory card eklendi. [resmî özellik](https://github.com/NousResearch/hermes-agent/commit/c07be22d0c9d01d95fbb4e5d2352288d0ed3e39b)
- **Profil takma adı onarımı:** `hermes doctor`, orphan alias kaldırma komutunu gösteriyor; ilgili ipucu platforma uygun hale getirildi. [resmî düzeltme](https://github.com/NousResearch/hermes-agent/commit/ea665e6d711d0bdc9050696446b34b1be987a227) · [platform düzeltmesi](https://github.com/NousResearch/hermes-agent/commit/0033af0e4d72554cb55ff048e28596c7f42a18a5)

## Kullanıcı için amacı

Bu etiketlenmemiş geliştirmeler Desktop'ta clarify yanıtlarının akışını, MCP OAuth hata sonrası davranışını, bazı sağlayıcı model seçimlerini, bağlayıcı yönetimini ve profil takma adı teşhislerini iyileştirmeyi hedefliyor.

## Kaynak

Bu özet yalnızca NousResearch/hermes-agent deposunun açık `main` dalındaki ilgili commitlere ve [karşılaştırma görünümüne](https://github.com/NousResearch/hermes-agent/compare/v0.21.7...main) dayanır. Kararlı ürün davranışı için asıl kaynak [resmî GitHub yayın notlarıdır](https://github.com/NousResearch/hermes-agent/releases).
