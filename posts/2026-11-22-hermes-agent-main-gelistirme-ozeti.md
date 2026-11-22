# Hermes Agent `main` geliştirme özeti — 22 Kasım 2026

> **Kararlılık durumu:** Bu bir sürüm notu değildir. Resmî son sürüm [`v0.23.3`](https://github.com/NousResearch/hermes-agent/releases/tag/v0.23.3); aşağıdakiler `main` dalında bulunan, henüz yeni bir sürüm etiketiyle yayımlanmamış geliştirmelerdir.

> **Kapsam:** 19 Kasım (veya önceki özet) özetinden sonra görülen kullanıcıyı etkileyen resmî `main` commitleri.

## Öne çıkan geliştirmeler

- **CLI/TUI hata clear fix** - `c7a3fe2`: Bir-shot çalışma terminal durumunu temizler; TUI hataları artık nedenini söyler
- **Fatura onayı düzelmesi** - `b149403`: Slasher/fatura onayı artık engellenmez; TUI onay overlay'ı ile senkronize olur
- **Profile publish race düzeltmesi** - `fcc8002`: Windows publish kontrolü her işlemci üzerinde okunuyor; cross-process race giderildi
- **Kanban config-plane outage fix** - `88e01c3`: Config-plane arızası pinned kartı ertelemeyi ve 403 hatasını önler
- **Kanban refusal unblock fix** - `eda7fde`: Refusal'ın unblock komutu kart board'ını doğru şekilde namıyor
- **Profil oluşturma race giderildi** - `52b5271`: Publish platform branches gerçek hostlar üzerinde çalıştırılıyor
- **MCP araçları güncellemesi** - `0d49d6d`: memtomem 0.1.27'e yükseltilmiş; plugin kataloğu güncellemesi
- **Gateway receipt ve connection fixes** - `b8478bc`: Durdurulmuş sender'ın lock'u serbest büyütülüyor; stored cwd platform-spelling düzeltiliyor
- **Compression altyapısı improvements** - `95a1d22`: Stub helpers modül başına import; `8e8b582`: Pruned results preceding callsla eşleştiriliyor; `6a5cee0`: Başarısız exclusive archives temizlendi; `e7e66a1`: 20,000 capsız archive reference row okunuyor
- **Terminal ve Windows test düzeltmeleri** - `6b554ff`: identify_gateway/psutil imports hoisted; `055f391`: readiness wait fails olduğunda pipe server reaped; `49f87e3`: two live tests load altında durmıyor; atomic snapshot test noclobber-safe '>|' redirect'ı kabul ediyor
- **Desktop archived state preservation** - Archived state session search'ta preserved

## Kullanıcı için amacı

Bu etiketlenmemiş çalışma; kullanıcılar terminal.status'ın daha temiz görüntüye sahip olacak, TUI hataları sebep ve nedenlerini clearer gözetecek, fatura/onay sürecinde daha az engel Experience'a sahip olacak, gateway bağlantıları daha güvenilir şekilde geri yüklenecek, compression altyapısı daha az başarısızlıkla çalışacak, ve terminal/testlar daha stabil çalışacak. Kullanıcılar daha az teknik sorunla karşılaşacak ve session aramaları daha hızlı ve doğru sonuçlanacak.

## Kaynak

Bu özet sadece NousResearch/hermes-agent deposunun açık `main` dalındaki ilgili commitlere ve [`v0.23.3...main` karşılaştırma görünümüne](https://github.com/NousResearch/hermes-agent/compare/v0.23.3...main) dayanır. Kararlı sürüm davranışı için asıl kaynak [resmî GitHub yayın notlarıdır](https://github.com/NousResearch/hermes-agent/releases).

## Değişiklik listesi (tam committed list)

- `c7a3fe2abd68fd58833ba0fc1f78ab209d213ed8` - fix(cli,tui): a one-shot run clears its terminal status; TUI errors say why
- `b149403a24` - fix(cli): a slash/billing confirm reports blocked, like the TUI's confirm overlay
- `fcc8002c1e7418d82b0397d3e446f3f3eaceab7d` - fix(profiles): read the Windows publish check from hermes_platform
- `88e01c39eff15ba84d46b8976fee4bc3c962c64a` - fix(profiles): a create that loses a cross-process race gets "already exists"
- `52b527194b364ba073c85f0b1cd8c63bc9264cac` - test(profiles): run the publish platform branches on their real hosts
- `0d49d6d9d20e461155d49ba9d188687079c811af` - plugin-catalog: bump memtomem to 0.1.27 (memtomem 0.7.12)
- `b8478bc161bade3c1cbc828ac557734bc75c2070` - fix(gateway): release a stopped sender's lock whatever its confirmation does
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