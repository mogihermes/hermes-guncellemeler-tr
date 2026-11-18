# Hermes Agent `main` geliştirme özeti — 18 Kasım 2026

> **Kararlılık durumu:** Bu bir sürüm notu değildir. Resmî son sürüm [`v0.23.2`](https://github.com/NousResearch/hermes-agent/releases/tag/v0.23.2); aşağıdakiler `main` dalında bulunan, henüz yeni bir sürüm etiketiyle yayımlanmamış geliştirmelerdir.

> **Kapsam:** v0.23.2'den itibaren görülen kullanıcıyı etkileyen resmî `main` commitleri.

## Öne çıkan geliştirmeler

- **Cloud sign-in error fix** - `65cca665`: Cloud auth artık "not signed in to Nous Portal" hatasını 401 yerine 409 status code ile yanıtluyor; kullanıcılar daha doğru hata mesajını görüyor.
- **Transferred messaging bots feature** - `5342a0a9`: transferred messaging bots artık switched off olarak geliyor; bulut ajanının çalışan workspace'ını etkilemiyor.
- **Import --keep-host feature** - `0695cbbb`: `hermes import --keep-host` komutu bulut ajanını değiştirirken host ayarlarını koruyuyor.
- **Desktop backup & transfer settings** - `80e77647`: Yeni Settings ▸ Backup & Transfer sekmesi eklendi; kullanıcılar yedekleme ve transfer işlemlerini GUI'den yönetebiliyor.
- **Gateway attachment handling** - `f66b6cdd`: Gateway bağlantısı yeniden bağlandığında, reply'ların attachments'ları doğru şekilde taşınıyor.
- **SSRF/secret-URL refusals** - `ed1f43c1`: Context plugin artık @url referanslarındaki SSRF ve secret-URL reddedilmeleri daha iyi floor ediyor; güvenlik uyarısı görünümü geliştirildi.
- **Plugin docstring critical → caution** - `d1b46d71`: Docstring critical findings artık "safe" yerine "caution" verdictiyle değerlendiriliyor; yanlış "safe" etiketlenmesi engellendi.

## Kullanıcı için amacı

Bu etiketlenmemiş çalışma; bulut oturum açma hata raporlamasının düzeltilmesi, messaging botlarının transferred olduğunda daha doğru davranması, import ile host ayarlarının korunması, gateway bağlantı durumundaki eki attachmentların doğru taşınması ve @url referanslarındaki güvenlik uyarılarının daha net görülemesi hedefliyor. Kullanıcılar artık bulut sign-in hatalarını daha anlaşılır bir kodla göruyor, bot transfer'lerinde veri kaybı yaşamıyor, import işlemleri daha güvenli hale geliyor ve gateway ekleri doğru bir şekilde senkronize oluyor.

## Kaynak

Bu özet sadece NousResearch/hermes-agent deposunun açık `main` dalındaki ilgili commitlere ve [`v0.23.2...main` karşılaştırma görünümüne](https://github.com/NousResearch/hermes-agent/compare/v0.23.2...main) dayanır. Kararlı sürüm davranışı için asıl kaynak [resmî GitHub yayın notlarıdır](https://github.com/NousResearch/hermes-agent/releases).

## Değişiklik listesi (tam committed list)

- `65cca665` - fix(persistence): the SQLite listing preview trims leading whitespace before its head cut
- `9ab13456` - fix(persistence): the SQLite rename through a compressed conversation lands on its live tip
- `458a3f80` - fix(persistence): a manual SQLite compress that rotates moves the conversation's name
- `0ad4d101` - refactor(persistence/sqlite): filter live delegations by state='running' only
- `6c8bdc2f` - fix(persistence): route the store admin's and readiness probe's state.db opens through connect_tracked
- `a4d40266` - feat(persistence): add sessions.prompt_cache_clock to the SQLite schema
- `2450bffa` - feat(persistence): serve the prompt-cache clock from the SQLite usage repository
- `df48af62` - feat(persistence): accept the prompt-cache clock in the SQLite usage.main receipt
- `775eedb6` - fix(persistence): the SQLite begin_epoch refuses a bump while another process owns the profile
- `499db5e4` - fix(persistence): the SQLite holder fails closed on a symlinked state.db path
- `65cca665` - fix(persistence): the SQLite listing preview trims leading whitespace before its head cut
- `5342a0a9` - feat(import): transferred messaging bots arrive switched off on the cloud agent
- `0695cbbb` - feat(import): `hermes import --keep-host` replaces a cloud agent, keeps its host setup
- `80e77647` - feat(desktop): Settings ▸ Backup & Transfer
- `8b362a27` - fix(gateway): a Desktop reply streamed before its last tool settles again
- `36706d42` - fix(gateway): an adopted Desktop row with bare custom resumes on the profile route
- `3007033a` - test(e2e): handoff scenario lets the held kanban worker finish before waiting for the relaunch
- `c3b90ccc` - fix(install-e2e): keep a profile cache's durable subdirs judged; cover --profiles-dir
- `634d43c8` - fix(install-e2e): a profile's cache/ is advisory, not user state
- `f8acc268` - refactor(gateway): outbound send files move from tools/ to gateway/outbound/
- `23ddc546` - fix(move): scan files that name only a moved file
- `5e53407e` - fix(move): a path joined through a folder variable to a moved file is flagged
- `611f0ab7` - refactor(cron): three cron helper files move from tools/ to cron/
- `3e931466` - fix(move): files that leave a folder that stays move alone
- `a1bbd329` - refactor: split utils.py into the utils package
- `0309b005` - test(core): send_message_tool refuses every action but send
- `a2c05c0d` - fix(core): keep create_custom_toolset for embedding hosts
- `c4635985` - refactor(core): delete unreached send_message actions, clarify/session helpers and backend aliases
- `70c6db1e` - refactor(browser-desktop): delete unreached browser and desktop tool code
- `56b1aab1` - fix(mcp): stop promising a health check the suspect warning never runs
- `dd478aa3` - refactor(connectors-mcp): delete unreached connector and MCP OAuth code
- `733a5cca` - fix(speech): keep listen_for_speech, the public barge monitor plugins may import
- `5d7618c4` - test(speech): the full-duplex capture test pins every speech block, pre-roll included
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
- `6cea8f02` - fix(skills): print the third-party notice after the file list on unprompted installs (duplicate)
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
*Bu özet `main` dalının cutting edge değişikliklerini documentación amacıyla toplar. Kararlı sürüm davranışı için [resmî release notları](https://github.com/NousResearch/hermes-agent/releases) Referans alın.*