# Hermes Agent `main` geliştirme özeti — 28 Ekim 2026

> **Kararlılık durumu:** Bu bir sürüm notu değildir. Resmî son sürüm [`v0.22.5`](https://github.com/NousResearch/hermes-agent/releases/tag/v0.22.5); aşağıdakiler `main` dalında bulunan, henüz yeni bir sürüm etiketiyle yayımlanmamış geliştirmelerdir.

- **Karşılaştırma:** [`v0.22.5...main`](https://github.com/NousResearch/hermes-agent/compare/v0.22.5...main)
- **Kapsam:** 21 Ekim (veya önceki özet) özetinden sonra görülen kullanıcıyı etkileyen resmî `main` commitleri.

## Öne çıkan geliştirmeler

- **Stale-target retry ile ilgili kullanıcı etkileri** - `ee7e0f517`: Deserted retry senaryosu where the second deep confirm was declined or accepted after the edited turn moved, the retry rolled its busy arm back unconditionally. If another window or queued follow-up started a turn in the same session while the dialog was open, that turn was shown idle while it ran. Now the session's flags and transcript correctly reflect the moved turn when `turnLive` is set by the backend.

- **Stored session olmayan stale-target retry** - `91832ef0`: Stale-target retry that sends nothing (second confirm declined, answered after a switch, or the edited turn moved) kept whatever history the session held, on the grounds that the refresh had already replaced the optimistic edit. Without a stored session the session still showed the optimistic, cut-down timeline with the unsent edit. Now `retryStaleEdit` restores the pre-edit history when it had nothing to refresh from, and keeps the refreshed one otherwise.

- **Runtime recovery edit hatası** - `c9c343c3`: Edit that fails after a runtime recovery leaves the composer idle. `rollBackEdit` cleared the foreground busy flags only while the edited runtime was still the active one. A submit that finds its runtime gone resumes the stored session under a new runtime id and moves the active session to it, so when the resent submit then failed the composer stayed busy and awaiting a response. Now the ownership check applies only where it is needed: a stale-target retry whose second confirm was answered after the user switched to another session.

## Kullanıcı için amacı

Bu etiketlenmemiş çalışma; stale-target retry'ların daha doğru bir şekilde yönetilmesini, session recovery durumundaki editor durumunun düzeltilmesini ve kullanıcının.Session state kaybetmemesini hedefliyor.

## Kaynak

Bu özet yalnızca NousResearch/hermes-agent deposunun açık `main` dalındaki ilgili commitlere ve [karşılaştırma görünümüne](https://github.com/NousResearch/hermes-agent/compare/v0.22.5...main) dayanır. Kararlı ürün davranışı için asıl kaynak [resmî GitHub yayın notlarıdır](https://github.com/NousResearch/hermes-agent/releases).