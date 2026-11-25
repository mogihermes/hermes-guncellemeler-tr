# Hermes Agent `main` geliştirme özeti — 24 Kasım 2026

> **Kararlılık durumu:** Bu bir sürüm notu değildir. Resmî son sürüm [`v0.23.4`](https://github.com/NousResearch/hermes-agent/releases/tag/v0.23.4); aşağıdakiler `main` dalında bulunan, henüz yeni bir sürüm etiketiyle yayımlanmamış geliştirmelerdir.

> **Kapsam:** 23 Kasım (veya önceki özet) özetinden sonra görülen kullanıcıyı etkileyen resmî `main` commitleri.

## Öne çıkan geliştirmeler

- **Çron jobı durma/reddurma durumu** - `fix(cron): refuse a paused relay-fronted run instead of falling through locally` ve `fix(cron): refuse console run for paused and disabled jobs (#156575)`: Paused ve disabled job'lar artıklı olarak reddediliyor; yerel claim atlaması engelleniyor.

- **Profiller: .env ve arşiv bağlantıları** - `fix(profiles): convert a linked .env through a fresh temp file` ve `fix(profiles): rewrite absolute links in the tar header; links need real parent dirs`: Profil .env dosyaları fresh temp dosyası üzerinden aktarılıyor; mutlak bağlantılar düzeltildi.

- **Dashboard: .env güvenliği** - `fix(dashboard): refuse a non-UTF-8 .env with a quoted override before writing config.yaml`: .env dosyaları UTF-8 kontrolü ile kabul ediliyor; quoted override öncesi reddediliyor.

- **Gateway: .env şablonları** - `fix(gateway): judge a first move's .env template against the gateway service it installs`: Gateway .env şablonları gateway servisi ile kıyaslandırılıp, uyuşmazlık durumunda reddediliyor.

- **Dashboard hareketli tema** - `feat(dashboard): 'your dashboard is moving' modal; Oswald andona Sans replace Collapse and Rules (#158363)`: Dashboard yeniden yönlendirme modali yeni Oswald and Mona Sans yazı tipi ile güncellendi.

- **Cron.plugin_api yayınlanması** - `feat(cron): publish cron.plugin_api for scheduling a named job and reading delivery platforms`: Named job scheduling ve delivery platforms okurulmak üzere cron.plugin_api yayınlandı.

- **Plugin oturum bilgisi** - `feat(plugins): plugins can read how the session was created, delegated children and forks`: Eklentiler oturum oluşturma yöntemi, delegated children ve forks hakkında okuma yapabiliyor.

## Kullanıcı için amacı

Bu etiketlenmemiş çalışma; kullanıcılarının cron jobları daha güvenilir çalışacak, profillerin .env ve arşiv bağlantıları düzelteceği, dashboard .env uyumluluk sorunlarından korunacak ve gateway .env şablonları daha doğru ele alınacak. Kullanıcılar cron aracılığıyla çalışan job'ları yönetirken daha az rastgele kayıp deneyimleyecek ve multi-profile kurulumları daha stabilization görecektir.

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
- `fix(profiles): export installer links as relative links so the archive imports`
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

---

*Bu özet `main` dalının cutting edge değişikliklerini documentación amacıyla toplar. Kararlı sürüm davranışı için [resmî release notları](https://github.com/NousResearch/hermes-agent/releases) Referans alın.*