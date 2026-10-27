# Hermes Agent `main` geliştirme özeti — 27 Ekim 2026

> **Kararlılık durumu:** Bu bir sürüm notu değildir. Resmî son sürüm [`v0.22.5`](https://github.com/NousResearch/hermes-agent/releases/tag/v0.22.5); aşağıdakiler `main` dalında bulunan, henüz yeni bir sürüm etiketiyle yayımlanmamış geliştirmelerdir.

- **Karşılaştırma:** [`v0.22.5...main`](https://github.com/NousResearch/hermes-agent/compare/v0.22.5...main)
- **Kapsam:** 21 Ekim özetinden sonra görülen kullanıcıyı etkileyen resmî `main` commitleri.

## Öne çıkan geliştirmeler

- **Gerekçesiz Captcha durumu: Tek standing digest görevi** Captcha wording düzeltmesiyle birlikte, `human_task_queued` case artık her `next` adımında tekrar taramak yerine, tek bir standing digest görevi olarak parksıyor. Böylece re-scan ve re-queue döngüsü ortadan kalkıyor. [Commit `085f562a`](https://github.com/NousResearch/hermes-agent/commit/085f562af53a6fedadac3681e2c498fc71316132)

- **Defunct broker'lar: --priority runs during asla kalkmaz** `--priority` flagi ile yapılan runner'lar, zaten kapatılmış (defunct) broker'ları tekrar kalkıştırmıyor ve uyandırıyor. Defunct ids artın ledger'in tamamından, sadece passed listeden değil, cron uykusundan de kurtuluyor. [Commit `f33e4811`](https://github.com/NousResearch/hermes-agent/commit/f33e4811274ed8c930dc78e36e6505d4ea0e8d4b)

- **TDC --declined: Tek digest girişi for dead parked tasks** `dnc --declined` artık sadece tek bir digest girişi oluşturuyor; dead parked case'lar için iki digest girişi (yeni close-out + parked manual step) önleniyor. [Commit `a4ed3b34`](https://github.com/NousResearch/hermes-agent/commit/a4ed3b3493e887d30150187678f54e8b3489927f)

- **Full otonomy: confirm_first uyarısı** Full autonomy instructions artık üç farklı yerde (SKILL.md rule, next loop step, note) `confirm_first=true` yasasını düzelterek, agentın kendi instruction'larını ihmal etmesini engelliyor. Tüm otomoda `except on action with confirm_first=true` zaslında operatorı her seferinde bekletiyor. [Commit `be2e2bd0`](https://github.com/NousResearch/hermes-agent/commit/be2e2bd0f3f3af471bfc4669e2457ae5efb202d7)

- **Plugin katalogı: tracekit eklentisi eklendi** Catalog artık tracekit pluginini destekliyor; kullanıcılar tarama ve disclosures özelliklerinden yararlanabilir. [Commit `fe3160b1`](https://github.com/NousResearch/hermes-agent/commit/fe3160b17a5719fe18d5c08e655ff74fd901d6a2)

## Kullanıcı için amacı

Bu etiketlenmemiş çalışma; captcha işlemlerinin daha temiz bir digest görünümüyle tamamlanmasını, defunct broker'ların --priority runs during sustained daha güvenilir olmasını, TDC consent işlemlerinin tek girişle düzgünetlenmesini, full oturum otonomlığının beklenenden farklı davranmasını ve eklenti katalogına yeni tracekit eklentisinin eklenmesini hedefliyor.

## Kaynak

Bu özet yalnızca NousResearch/hermes-agent deposunun açık `main` dalındaki ilgili commitlere ve [karşılaştırma görünümüne](https://github.com/NousResearch/hermes-agent/compare/v0.22.5...main) dayanır. Kararlı ürün davranışı için asıl kaynak [resmî GitHub yayın notlarıdır](https://github.com/NousResearch/hermes-agent/releases).