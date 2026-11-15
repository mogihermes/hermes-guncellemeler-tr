# Hermes Agent `main` geliştirme özeti — 15 Kasım 2026

> **Kararlılık durumu:** Bu bir sürüm notu değildir. Resmî son sürüm [`v0.23.1`](https://github.com/NousResearch/hermes-agent/releases/tag/v0.23.1); aşağıdakiler `main` dalında bulunan, henüz yeni bir sürüm etiketiyle yayımlanmamış geliştirmelerdir.

> **Kapsam:** 9 Kasım (veya önceki özet) özetinden sonra görülen kullanıcıyı etkileyen resmî `main` commitleri.

## Öne çıkan geliştirmeler

- **Plugin docstring critical currently stops at caution** - `d1b46d71`: Docstring critical findings now stop at "caution" verdict instead of being incorrectly marked "safe". Every line a non-docstring AST node occupies is code; files with non-UTF-8 source encoding get no docstring cap at all. All 2,251 listed catalog pins vs main: 0 worse, 25 of 31 dangerous become installable (24 caution, 1 safe).

- **Docstring sharing its line with code stays critical** - `fc562d87`: A docstring is runtime data any file can read back under names no static scan enumerates, so the cap no longer tries to prove a docstring inert. A critical inside one now stops at high (verdict caution: the user confirms the install), never safe and never the un-overridable dangerous that prose alone caused.

- **Demote plugin-guard findings inside Python docstrings** - `2a51b766`: Code on the docstring's own line (or a header default), or a source cookie that makes CPython run other text than the UTF-8 parse, executes: no docstring cap.

- **A reply's attachments follow its text onto the reconnected adapter** - `f66b6cdd`: Gateway attachment handling repair ensures replies' attachments follow their text onto the reconnected adapter.

- **SSRF and secret-URL refusals surfaced in @url references** - `ed1f43c1`: Context plugin now surfaces SSRF and secret-URL refusals in @url references, improving security visibility.

- **Plugin catalog entries updated and delisted** - Various catalog bumps and delistings for entries whose pinned source is gone or deprecated.

## Kullanıcı için amacı

Bu etiketlenmemiş çalışma; plugin güvenlik değerlendirmesinin (docstring critical → caution) stabilitesinin artması, gateway bağlantı durumundaki eki attachments'ın doğru taşınması ve @url referanslarındaki SSRF/secret-URL reddedilmelerin daha iyi floor edilmesi hedefliyor. Kullanıcılar artık eklentilerin güvenli değerlendirilmesi daha doğru yapılacağını, gateway'da bağlantı yeniden bağlandığında ekler doğru biçimde geri yükleneceğini ve URL tabanı güvenlik uyarılarının daha net görüleceğini期待할 할 수.

## Kaynak

Bu özet sadece NousResearch/hermes-agent deposunun açık `main` dalındaki ilgili commitlere ve [`v0.23.1...main` karşılaştırma görünümüne](https://github.com/NousResearch/hermes-agent/compare/v0.23.1...main) dayanır. Kararlı ürün davranışı için asıl kaynak [resmî GitHub yayın notlarıdır](https://github.com/NousResearch/hermes-agent/releases).

## Değişiklik listesi (tam committed list)

- `d1b46d71` - fix(plugins): a docstring critical stops at caution; header and re-encoded lines stay code
- `fc562d87` - fix(plugins): a docstring sharing its line with code, or read back as data, stays critical
- `2a51b766` - fix(plugins): demote plugin-guard findings inside Python docstrings
- `f66b6cdd` - fix(gateway): a reply's attachments follow its text onto the reconnected adapter
- `ed1f43c1` - fix(context): surface SSRF and secret-URL refusals in @url references
- `fcabfe38` - fix(gateway): keep primary re-login hint on the resolved backup account
- `deb7cc36` - fix(gateway): keep the primary's failed login with the turn and the route that resolved it
- `6cea8f02` - fix(skills): print the third-party notice after the file list on unprompted installs
- `5b229517` - plugin-catalog: glasses-platform 0.6.9 (reword a docstring example the install scanner flags)
- `t2d76c501` - chore(plugin-catalog): delist four entries whose pinned source is gone
- `f578714e` - test: pin that an empty backup account keeps its billing card, and drop the class-name layout test
- `9dbcb627` - fix(fallback): compare the route before a channel or session override, where the failure is taken
- `319938fa` - fix(fallback): drop the primary's failure when the turn's overrides change the resolved route
- `632edf2` - refreshed fallback candidate other model'de quarantined
- `73ec436` - custom route: main runtime identity only at origin
- `3e0dda7` - payment error: same-host custom endpoint, session provider değil
- `535477e` - fallback candidate credential refresh parameter repairs korur
- `897ee4a` - custom route: main runtime identity only on relay path
- `47053c7` - model-aware peek: current key cooled down for that model survives
- `3253e57` - parameter repair: pool rotation retry survives
- `1482adf` - parameter repair: also survives pool rotation retry
- `4b74783` - fallback candidate: backend tag classification provider
- `d98f790` - content-policy refusal with quota wording sent once
- `38d4de8` - two guards at paths where behaviour changed
- `3c8d925` - policy refusal quota wording: provider benches
- `90b40ad` - error-classifier: drop bare "credits" account-wall token
- `cf7b294` - streamed certificate failure test: also pins the fallback
- `b479868` - gateway rowless-binding repair: CAS refuses mid-lookup
- `392c588` - gateway observed native-image turns persist pre-wrap
- `606967f` - gateway group transcript rows: epoch floats stamped
- `eeb54f9` - gateway persist clean observed image turns
- `7e7dfd4` - gateway exec-approval delivery boundaries: logged for triage
- `eac24f9` - gateway edited /goal: kicks off as own turn (instead of admission_conflict)
- `fbaa6d8` - gateway edited /queue or /steer mid-turn: queues instead of admission_conflict
- `edb9736` - telegram core: early-return receipts ve failed-prep reporting pinlendi
- `2b0337e` - telegram shutdown: admission claim releases bekler; queued update cancelled before entry closes handler
- `8d7061f` - fallback walk: zaten denenmiş lane'ları tekrar geçmemeyi sağlar
- `6834d14a` - merge: sec3/134019-standalone-npmrc
- `7f4e5e68` - fix(contracts): declare upstream_repo on catalog install rows; map contributor email
- `aa3534c3` - fix(skills): name the upstream repo for live-upstream optional skills
- `6834d14a` - merge: sec3/139327-uv-cache-locks
- `2483ca10` - merge: sec3/148835-git-for-windows-bump
- `b624d30e` - merge: sec3/128930-history-check-pr-head
- `00c53467` - merge: sec3/108382-ci-input-hardening
- `1fa93223` - merge: sec3/144380-mcp-hint-flip-recheck
- `b2a201cd` - merge: sec3/7485-approval-redos
- `1b128eb9` - merge: sec3/117815-approval-comment-strip
- `fa0fdfe0` - merge: sec3/122024-redact-exec-spill
- `1c8bde79` - merge: sec3/38964-drive-letter-paths
- `8ab4b8d4` - merge: sec3/143691-delete-floor-cd-tracking
- `8b4c5343` - merge: sec3/155836-followup-155400
- `2ab88774` - merge: sec3/fix/secret-refresh-owner-scope
- `5d616829` - chore: map contributor email for lad75020
- `6cea8f02` - fix(skills): print the third-party notice after the file list on unprompted installs
- `778dc708` - fix: main's no-tmp lint passes again after the Sentinel Governance pin
- `c8245965` - chore: map contributor email for isthananaya
- `952f7b68` - chore(catalog): drop empty image/screenshots fields from hermes-eye-memory
- `ed8fd34a` - pin catalog entry to security fix
- `13ba0436` - pin hermes-eye-memory to compatibility fix
- `e71d2da7` - add hermes-eye-memory to the plugin catalog
- `cd922988` - catalog: remove follow-through (author withdrew plugin)
- `e96ae552` - catalog: remove eyes (author withdrew plugin)
- `de9a2f30` - catalog: remove card-grader (author withdrew plugin)
- `ed1f43c1` - fix(context): surface SSRF and secret-URL refusals in @url references (duplicate entry, same fix)
- `50637d57` - fix(context): surface web_extract policy denials in @url references
- `a7bf80f4` - chore(catalog): re-pin hey-pcb to 545f30ee (cost_unit fix), keeping main's reviewed text
- `c2779be8` - rebrand: gemini-live-bridge becomes livetalk (pin v2.0.0)
- `34244862` - rebrand: gemini-live-bridge becomes livetalk (pin v2.0.0)
- `ed95cb6c` - chore(plugin-catalog): bump circuit-bench to 0.1.1
- `5dcd3b55` - feat(plugin-catalog): add neuralwatt-provider
- `c0fbe46e` - plugin-catalog: re-pin tironian to 3b8c1f1 (post-deadline fixes)
- `6f0d8dd6` - plugin-catalog: bump tironian to 0.2.0 (e25e339)
- `d902c7e8` - Update unblockbruecke.yaml
- `be53dd38` - chore(catalog): livetalk requires_hermes >=0.22.1 (prompt.receipt ships in v0.22.1)
- `129b3427` - pin: the dependency declaration rides along (websockets floor+bound)
- `4436eb78` - rebrand: gemini-live-bridge becomes livetalk (pin v2.0.0)
- `34244862` - rebrand: gemini-live-bridge becomes livetalk (pin v2.0.0)
- `5d616829` - chore: map contributor email for lad75020
- `ff194672` - chore(catalog): review disclosure for qmd-workspaces
- `09adb261` - Add QMD Workspaces to plugin catalog
- `c6339f39` - chore(catalog): bump Frihet to v0.2.2
- `5a070ced` - Update shaderbruecke.yaml

---
*Bu özet `main` dalının-cutting edge_ değişikliklerini documentación amacıyla toplar. Kararlı sürüm davranışı için [resmî release notları](https://github.com/NousResearch/hermes-agent/releases) Referans alın.*