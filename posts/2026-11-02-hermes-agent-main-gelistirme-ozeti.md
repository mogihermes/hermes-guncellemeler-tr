# Hermes Agent `main` geliştirme özeti — 2 Kasım 2026

> **Kararlılık durumu:** Bu bir sürüm notu değildir. Resmî son sürüm [`v0.22.5`](https://github.com/NousResearch/hermes-agent/releases/tag/v0.22.5); aşağıdakiler `main` dalında bulunan, henüz yeni bir sürüm etiketiyle yayımlanmamış geliştirmelerdir.
> **Karşılaştırma:** [`v0.22.5...main`](https://github.com/NousResearch/hermes-agent/compare/v0.22.5...main)
> **Kapsam:** 30 Ekim (veya önceki özet) özetinden sonra görülen kullanıcıyı etkileyen resmî `main` commitleri.

## Öne çıkan geliştirmeler

- **Gateway session restored shared listener** - `4d26e0cceaed`: Gateway'de restore işlemi yapılan webhook sessizliklerinin shared listener'ları koruyup koruymadığı kontrol edilir. Aynı listener'ı tekrar kullanmaması sağlanır.

- **Eski tahmin chat'ler primary bot'a yanıt vermeyi bırakır** - `10d34c53d967`: Eski kaydedilmiş tahmin, primary bot'tan restored chat üzerinden yanıt vermek için denenmemesi sağlanarak gereksiz yanıtlar engellenir.

- **Warm reopen cron ve messaging toplamlarını korur** - `edf1495a314f`: Warm reopen işlemi cron ve messaging session'ların toplamlarını (totals) kaybetmeden tutar.

- **Yeniden açılan session'lar saklı cache hit'ini gösterir** - `e53cd9f31a5b`: Yeniden açılan (reopened) session'lar, saklı cache hit'ini yeni bir turn başına göstererek performansı iyileştirir.

- **Desktop: removed gateway terminal'lar kaldırılır** - `8bf447a7291e`: Kaldırılan gateway, terminal sekmelerinden tutarlı şekilde kaldırılır.

- **Desktop: terminal tab gateway kaydı** - `f9cf1f0f5d68`: Terminal tab'ı, başlangıçta gateway'yi kaydetmek için protokol eklenir.

- **Desktop: SSH disconnected localization** - `22af40a27e88`: SSH terminal bağlantı kesildiğinde gösterilecek yerelize edilmiş mesaj eklenir.

- **Desktop: New terminal tab active profile kaydı** - `0079924fcd58`: Yeni terminal oluşturulduğunda aktif profile kaydedilir.

- **Sessions: read-only view phone chat engeli kaldırılır** - `92628552ab06`: İlk olarak açılan read-only view, phone chat'yi engellememesi sağlanır.

- **Sessions: login-stamped phone chat adoption** - `7aa5200e91ee`: Hermes session'ları login-stamped phone chat'ları followed şekilde benimsemesi sağlanır.

- **Plugin katalog sürümü güncellemesi** - `334fceea7391`: Plugin kataloğu, agent-importers 1.2.1 sürümüne güncellenir.

- **Hermes migrate OpenBot import** - `afc5c55d4748`: Hermes migrate ve setup, OpenBot import seçeneği sunar.

- **Bare hermes migrate hat düzeltmesi** - `06433066f46a`: Bare hermes migrate, setup-only flag'ları geçirmemesi ve hatalı import'lar için uyarı veren özellik eklenir.

- **Hermes migrate OpenClaw secrets düzeltmesi** - `43cc73f12dfd`: Hermes migrate --migrate-secrets flagiyle OpenClaw sırtajının içe aktarılması sağlanır.

- **Hermes migrate non-zero exit on failure** - `f21c7baef1ba`: Hermes migrate <agent>, import başarısız olduğunda non-zero exit kodu döndürür.

- **Error card v2 geliştirme devam eder** - Engelleme/degrade şiddet derecelendirmesi, birincil eylem, toggle'lı ayrıntılar ve 8 locale çeviri çalışmaları devam ediyor.

## Kullanıcı için amacı

Bu etiketlenmemiş çalışma; gateway session kayıplarını önleme, cron session toplamlarının korunması, session yeniden açma performansının iyileştirilmesi, desktop kullanıcı deneyiminin geliştirilmesi ve migrate komutunun daha güvenilir olması hedefliyor.

## Kaynak

Bu özet yalnızca NousResearch/hermes-agent deposunun açık `main` dalındaki ilgili commitlere ve [karşılaştırma görünümüne](https://github.com/NousResearch/hermes-agent/compare/v0.22.5...main) dayanır. Kararlı ürün davranışı için asıl kaynak [resmî GitHub yayın notlarıdır](https://github.com/NousResearch/hermes-agent/releases).