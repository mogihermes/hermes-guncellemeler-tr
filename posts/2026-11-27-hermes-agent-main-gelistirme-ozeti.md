# Hermes Agent `main` geliştirme özeti — 27 Kasım 2026

> **Kararlılık durumu:** Bu bir sürüm notu değildir. Resmî son sürüm [`v0.23.4`](https://github.com/NousResearch/hermes-agent/releases/tag/v0.23.4); aşağıdakiler `main` dalında bulunan, henüz yeni bir sürüm etiketiyle yayımlanmamış geliştirmelerdir.

> **Kapsam:** 24 Kasım (veya önceki özet) özetinden sonra görülen kullanıcıyı etkileyen resmî `main` commitleri.

## Öne çıkan geliştirmeler

- **Çron jobı durma/reddurma durumu** - `fix(cron): refuse a paused relay-fronted run instead of falling through locally` ve `fix(cron): refuse console run for paused and disabled jobs (#156575)`: Paused ve disabled job'lar artıklı olarak reddediliyor; yerel claim atlaması engelleniyor.

- **Profiller: .env ve arşiv bağlantıları** - `fix(profiles): convert a linked .env through a fresh temp file` ve `fix(profiles): rewrite absolute links in the tar header; links need real parent dirs`: Profil .env dosyaları fresh temp dosyası üzerinden aktarılıyor; mutlak bağlantılar düzeltildi.

- **Dashboard: .env güvenliği** - `fix(dashboard): refuse a non-UTF-8 .env with a quoted override before writing config.yaml`: .env dosyaları UTF-8 kontrolü ile kabul ediliyor; quoted override öncesi reddediliyor.

- **Gateway: .env şablonları** - `fix(gateway): judge a first move's .env template against the gateway service it installs`: Gateway .env şablonları gateway servisi ile kıyaslandırılıp, uyuşmazlık durumunda reddediliyor.

- **Dashboard hareketli tema** - `feat(dashboard): 'your dashboard is moving' modal; Oswald andona Sans replace Collapse and Rules (#158363)`: Dashboard yeniden yönlendirme modali yeni Oswald andona Sans yazı tipi ile güncellendi.

- **Cron.plugin_api yayınlanması** - `feat(cron): publish cron.plugin_api for scheduling a named job and reading delivery platforms`: Named job scheduling ve delivery platforms okurulmak üzere cron.plugin_api yayınlandı.

- **Plugin oturum bilgisi** - `feat(plugins): plugins can read how the session was created, delegated children and forks`: Eklentiler oturum oluşturma yöntemi, delegated children ve forks hakkında okuma yapabiliyor.

- **Idle chats background compaction** - `feat(gateway): idle chats compact in the background on every route, per channel`: Arka plana malzeme tozlanması; her rotada ve kanala ayrı ayrı idle chat'ler tozlanır.

- **Lifecycle-guard düzeltmeleri** - `fix(lifecycle-guard): any list operator after a heredoc keeps it visible; filters must be bare names`, `fix(lifecycle-guard): drop pipe filters that can run a command`, `fix(lifecycle-guard): a heredoc body belongs to the command it is attached to`: Lifecycle guard güvenliği iyileştirmeleri; heredoc ve pipe filtreleri ile ilgili düzeltilmeler.

- **Prompt-cache iyileştirmeleri** - `fix(prompt-cache): a late keep-alive reply never rewinds a newer fold`, `fix(prompt-cache): price the unmarked tail of a request in flight as input`, `fix(prompt-cache): order a keep-alive's renewal against its request's own reply`, `fix(prompt-cache): a marked request is kept warm from its first send`, `fix(prompt-cache): keep 5m chats warm between messages, compact them at the edge`, `fix(prompt-cache): one snapshot for the tier check, upgrade after a committed edge compaction, no cold prune under a live refresh`: Prompt cache daha stabil çalışıyor; keep-alive, tier kontrolü ve soğuk prune ile ilgili düzeltilmeler.

- **Session search iyileştirmeleri** - `fix(session_search): scroll returns the requested message whole; demoted tool output stays searchable from any caller`, `fix(session_search): the any-term retry uses the store's own query rewrite`, `fix(session_search): cap tool output in results, scroll to the nearest message for a guessed id, say how to resume`, `fix(session_search): discover returns real history instead of 0 or its own search echoes`, `fix(session_search): mixed-role date sorts merge both role legs by timestamp`, `fix(session_search): recovered tool output survives re-compaction, scrolls, and image turns stay searchable`, `fix(session_search): bound the in-session search and describe its real scope`, `fix(session_search): honour query when session_id is set`: In-session search daha doğru ve güvenilir; date sıralaması, ara sorgulamalar ve recover ile ilgili iyileştirmeler.

- **Plugin catalog güncellemeleri** - `chore(plugin-catalog): review disclosure for` birçok eklenti ve `feat(plugin-catalog): add` birçok yeni eklentı: Plugin kataloğu düzenli olarak güncelleniyor; new disclosures ve eklentiler ekleniyor.

- **Webapp: Port claim genişletme** - `fix(webapp): expand sibling profile port claims with each home's .env scope`: Webprofil claim'leri ev dizin .env kapsamıyla genişletiliyor.

- **OAuth provider validation** - `fix(plugins): validate cron-scheduler provider registration too`, `fix(plugins): validate computer-use provider registration`: Saatçi ve computer-use provider kayıtları validasyon ile Kontrol ediliyor.

## Kullanıcı için amacı

Bu etiketlenmemiş çalışma; kullanıcılarının cron jobları daha güvenilir çalışacak, profillerin .env ve arşiv bağlantıları düzelteceği, dashboard .env uyumluluk sorunlarından korunacak, gateway .env şablonları daha doğru ele alınacak ve idle chat'ler arka planda tozlanacak. Kullanıcılar cron aracılığıyla çalışan job'ları yönetirken daha az rastgele kayıp deneyimleyecek ve multi-profile kurulumları daha stabilization görecektir. Arka planda idle chat tozlanması performansı artırır ve kanallar arası geçişler daha fluid olur.

## Kaynak

Bu özet sadece NousResearch/hermes-agent deposunun açık `main` dalındaki ilgili commitlere ve [`v0.23.4...main` karşılaştırma görünümüne](https://github.com/NousResearch/hermes-agent/compare/v0.23.4...main) dayanır. Kararlı sürüm davranışı için asıl kaynak [resmî GitHub yayın notlarıdır](https://github.com/NousResearch/hermes-agent/releases).

## Değişiklik listesi (tam committed list)

- `fix(cron): refuse a paused relay-fronted run instead of falling through locally`
- `fix(cron): refuse console run for paused and disabled jobs (#156575)`
- `fix(cron): one paused-run refusal for every manual-run surface`
- `fix(cli): read terminal state from the normalised job in console cron run`
- `fix(profiles): convert a linked .env through a fresh temp file`
- `fix(profiles): rewrite absolute links in the tar header; links need real parent dirs`
- `fix(profiles): keep imported links valid after a rename and .env owner-only`
- `fix(profiles): resolve archive links after extraction; only profile import accepts them`
- `fix(profiles): import a profile archive that contains symlinks`
- `fix(dashboard): refuse a non-UTF-8 .env with a quoted override before writing config.yaml`
- `fix(dashboard): judge a username template against the same .env names the cleanup removes`
- `fix(dashboard): remove a .env override assigned under a quoted name`
- `fix(gateway): catch only the errors the gateway service generators raise`
- `fix(gateway): count a NAME= token after a quoted env value as set`
- `fix(gateway): apply a unit's UnsetEnvironment= when reading the environment systemd gives it`
- `fix(gateway): judge a first move's .env template against the gateway service it installs`
- `fix(gateway): refuse a stopped unit whose env launcher may set its home`
- `fix(gateway): refuse a backend move that would resolve a .env sign-in template differently`
- `feat(dashboard): 'your dashboard is moving' modal; Oswald and Mona Sans replace Collapse and Rules (#158363)`
- `feat(cron): publish cron.plugin_api for scheduling a named job and reading delivery platforms`
- `feat(plugins): plugins can read how the session was created, delegated children and forks`
- `feat(plugin api): publish the gateway's silence helpers for platform plugins`
- `fix(title): warn when a capped reply leaves no usable title after cleanup`
- `fix(title): name the finish reason, not an unverified cap, in the empty-title warning`
- `feat(gateway): idle chats compact in the background on every route, per channel`
- `fix(lifecycle-guard): any list operator after a heredoc keeps it visible; filters must be bare names`
- `fix(lifecycle-guard): drop pipe filters that can run a command`
- `fix(lifecycle-guard): a heredoc body belongs to the command it is attached to`
- `fix(prompt-cache): a late keep-alive reply never rewinds a newer fold`
- `fix(prompt-cache): price the unmarked tail of a request in flight as input`
- `fix(prompt-cache): order a keep-alive's renewal against its request's own reply`
- `fix(prompt-cache): a marked request is kept warm from its first send`
- `fix(prompt-cache): keep 5m chats warm between messages, compact them at the edge`
- `fix(prompt-cache): one snapshot for the tier check, upgrade after a committed edge compaction, no cold prune under a live refresh`
- `fix(session_search): scroll returns the requested message whole; demoted tool output stays searchable from any caller`
- `fix(session_search): the any-term retry uses the store's own query rewrite`
- `fix(session_search): cap tool output in results, scroll to the nearest message for a guessed id, say how to resume`
- `fix(session_search): discover returns real history instead of 0 or its own search echoes`
- `fix(session_search): mixed-role date sorts merge both role legs by timestamp`
- `fix(session_search): recovered tool output survives re-compaction, scrolls, and image turns stay searchable`
- `fix(session_search): bound the in-session search and describe its real scope`
- `fix(session_search): honour query when session_id is set`
- `fix(plugins): validate cron-scheduler provider registration too`
- `fix(plugins): validate computer-use provider registration`
- `chore(plugin-catalog): review disclosure for hermes-session-reset-policy 0.4.3 (no core session writes)`
- `feat(plugin-catalog): add mechacut (community, skills-only, Agent Plugins v1)`
- `chore(plugin-catalog): review disclosure for z0live`
- `feat(plugin-catalog): add squeezevid plugin`
- `chore(plugin-catalog): review disclosure for order-cards`
- `feat(plugin-catalog): add order-cards plugin`
- `chore(plugin-catalog): review disclosure for hindsight`
- `plugin-catalog: pin the released v2.0.0`
- `chore(plugin-catalog): review disclosure for mergeable`
- `feat(plugin-catalog): add mergeable plugin`
- `chore(plugin-catalog): review disclosure for coretica-memory-rules, coretica`
- `feat(plugin-catalog): add Coretica private-memory companion plugins`
- `chore(plugin-catalog): review disclosure for spellcheck-plus`
- `catalog: add spellcheck-plus`
- `chore(plugin-catalog): review disclosure for hermes-session-reset-policy`
- `catalog: hermes-session-reset-policy 0.4.3 (no core session writes)`
- `chore(catalog): bump aisecuritywarden to 0.7.16`
- `chore(catalog): update genealogy recipes to v3.0.0`
- `chore(catalog): review disclosure for edenai-provider`
- `feat(plugin-catalog): add edenai-provider`
- `chore(catalog): review disclosure for mechacut`
- `mechacut: restauración entree (le PUT precedent avait envoye un base64 vide - macOS -w0) : v1.1.2, pin 9476b60, deux horloges`
- `mechacut: v1.1.2 — deux espaces de version nommes (le registre publie la descripción corta, el bench guarda su contador live al manifest)`
- `mechacut: repin 75470555 (v1.1.1 — splitter live)`
- `first splitter clone live: disclosure updated to the truth on chain (self-split disclosed; external proposer clone awaits base_account)`
- `plugin re-pinned: 1.1.0 ever-growing description, no baked counts (org repo 654cf357)`
- `mechacut: pin 0a84ae6a1dea910b4957a6e6da45e1d46510db4a — doc-lie fix: num/round example now uses the real field (places, not decimals — the mini promised 1234.57 while the server returned 1235 with the wrong key; caught live by the site's own demo box), and the description count is now read at build from the routing table (182) instead of a frozen 170`
- `plugin-catalog: mechacut - repo moved to the mechacut org (github.com/mechacut/plugin); sha pin unchanged, old URL redirects`
- `plugin-catalog: mechacut - description drops the datable surface count (it moves every bundle; the manifest is the count: mechacut.studio/agent/manifest lists and counts them). sha pin unchanged (ed267990)`
- `mechacut: pin ed2679907596db5c7e6a3020e4128e49b4ec92a5 — review fixes (teknium1, 24-11): secret/scan example bounded to human-chosen text + full-text-leaves-the-machine line; network skill now English; disclosure truth — plain HTTPS, no per-call harness prompt.`
- `catalog: add mechacut (community, skills-only, Agent Plugins v1)`
- `chore(catalog): review disclosure for spellcheck-plus`

---

*Bu özet `main` dalının cutting edge değişikliklerini documentación amacıyla toplar. Kararlı sürüm davranışı için [resmî release notları](https://github.com/NousResearch/hermes-agent/releases) Referans alın.*