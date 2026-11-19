# Hermes Agent `main` geliştirme özeti — 19 Kasım 2026

> **Kararlılık durumu:** Bu bir sürüm notu değildir. Resmî son sürüm [`v0.23.2`](https://github.com/NousResearch/hermes-agent/releases/tag/v0.23.2); aşağıdakiler `main` dalında bulunan, henüz yeni bir sürüm etiketiyle yayımlanmamış geliştirmelerdir.

> **Kapsam:** 18 Kasım (veya önceki özet) özetinden sonra görülen kullanıcıyı etkileyen resmî `main` commitleri.

## Öne çıkan geliştirmeler

- **Discord slash command improvements** - `8d70b88`: Discord sync after mid-refresh now shows who triggered it; `c1a3cb0`: slash-command registry moved into adapter_command_sync for cleaner organization
- **Fix Discord app-info memo** - `7c33ac9`: app-info memo tied to its client; `32bceb3`: refresh bounded; `1ba9016`: install types set from app's Installation settings; `779cee6`: mixed drift/refresh upsert before sync
- **Gateway receipt and connection fixes** - `8911007`: adopt stored receipt whose policy keys build dropped; `bc3f2da`: restore receipt whose stored cwd is platform-spelled; `5d5b1dc`: restore policies written with local source or empty model; `0579add`: restore receipts whose model writers persisted empty; `f00be26`: control listener warms its identify answer before accepting
- **Compression infrastructure updates** - `95a1d22`: stub helpers import at module top; `8e8b582`: pruned results matched to preceding calls; `6a5cee0`: cleaned up failed exclusive archives; `e7e66a1`: archive reference row read without 20,000 cap; `ade65d4`: read-back points to archive again; `752162a`: model needs details in tool result stubs; `4a45994`: hoisted identify_gateway and psutil imports to module top
- **Terminal and Windows test fixes** - `6b554ff`: hoisted identify_gateway/psutil imports; `055f391`: reap pipe server when readiness wait fails; `49f87e3`: two live tests stop failing under load; atomic snapshot test accepts noclobber-safe '>|' redirect
- **Desktop archived state preservation** - preserves archived state in session search

## Kullanıcı için amacı

Bu etiketlenmemiş çalışma; Discord komutlarının daha doğru senkronize olması, gateway bağlantıları yeniden bağlandığında eki attachmentsların düzgün geri yüklenmesi, compression altyapısındaki güvenilirliği artması, terminal testlerinin daha stabil çalışması ve masaüstünde arşivlenen state'lerin doğru preserving'i hedefliyor. Kullanıcılar artık Discord slash komutlarında daha az veri kaybı experience'ı, gateway eklerinde daha doğru attachment geri yükleme, daha az test hataısı ve daha güvenilir session araması bekleyebilir.

## Kaynak

Bu özet sadece NousResearch/hermes-agent deposunun açık `main` dalındaki ilgili commitlere ve [`v0.23.2...main` karşılaştırma görünümüne](https://github.com/NousResearch/hermes-agent/compare/v0.23.2...main) dayanır. Kararlı sürüm davranışı için asıl kaynak [resmî GitHub yayın notlarıdır](https://github.com/NousResearch/hermes-agent/releases).

## Değişiklik listesi (tam committed list)

- `8d70b88abd68fd58833ba0fc1f78ab209d213ed8` - docs(discord): say who syncs after a mid-refresh
- `c1a3cb0` - refactor(discord): move slash-command registry into adapter_command_sync
- `7c33ac9` - fix(discord): tie the app-info memo to its client
- `32bceb3` - fix(discord): bound the app-info refresh and keep its last good result
- `1ba9016` - fix(discord): set command install types from the app's Installation settings
- `779cee6` - fix(discord): upsert on mixed drift and refresh app info before syncing
- `2a683b1` - test(discord): skip serialization probe without optional dependency
- `4504606` - fix(discord): preserve scope drift recreation
- `dc1b4a9` - Fix Discord guild slash command visibility
- `4bd8656` - fix(discord): diff slash commands against the raw registry
- `fe8b920` - test(gateway): pin that the process record is built before the control listener opens
- `f00be26` - fix(gateway): the control listener warms its identify answer before it accepts
- `95a1d22` - refactor(compression): the stub helpers import at module top
- `8e8b582` - fix(compression): match each pruned result to its own preceding call; register the streamed reference read
- `6a5cee0` - fix(compression): clean up failed exclusive archives
- `e7e66a1` - fix(compression): read every archive reference row, without the 20,000 cap
- `ade65d4` - fix(compression): clamp the hot-reloaded prune floor; name the real no-op reason
- `752162a` - fix(compression): point a read-back of an archive at that archive again
- `4a45994` - test: hoist the new identify_gateway and psutil imports to module top
- `055f391` - test(windows): reap the pipe server when the readiness wait itself fails
- `49f87e3` - test(windows): two live tests stop failing at random under load
- `6b554ff` - test: hoist the new identify_gateway and psutil imports to module top (duplicate)
- `055f391` - test(windows): reap the pipe server when the readiness wait itself fails
- `49f87e3` - test(windows): two live tests stop failing at random under load
- `49f87e3` - View commit details
- `055f391` - View commit details
- `49f87e3` - Browse repository at this point in the history
- `6834d14a` - fix(desktop): preserve archived state in session search
- `6cea8f02` - fix(contracts): declare upstream_repo on catalog install rows; map contributor email
- `aa3534c3` - fix(skills): name the upstream repo for live-upstream optional skills
- `b479868` - fix(gateway): rowless-binding repair: CAS refuses mid-lookup
- `392c588` - gateway observed native-image turns persist pre-wrap
- `606967f` - gateway group transcript rows: epoch floats stamped
- `eeb54f9` - gateway persist clean observed image turns
- `7e7dfd4` - gateway exec-approval delivery boundaries: logged for triage
- `eac24f9` - gateway edited /goal: kicks off as own turn (instead of admission_conflict)
- `fbaa6d8` - gateway edited /queue or /steer mid-turn: queues instead of admission_conflict
- `edb9736` - telegram core: early-return receipts ve failed-prep reporting pinlendi
- `2b0337e` - telegram shutdown: admission claim releases bekler; queued update cancelled before entry closes handler
- `8d7061f` - fallback walk: zaten denenmiş lane'ları tekrar geçmemeyi sağlar
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