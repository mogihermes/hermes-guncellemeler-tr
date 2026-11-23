# Hermes Agent `main` geliştirme özeti — 23 Kasım 2026

> **Kararlılık durumu:** Bu bir sürüm notu değildir. Resmî son sürüm [`v0.23.3`](https://github.com/NousResearch/hermes-agent/releases/tag/v0.23.3); aşağıdakiler `main` dalında bulunan, henüz yeni bir sürüm etiketiyle yayımlanmamış geliştirmelerdir.

> **Kapsam:** 22 Kasım (veya önceki özet) özetinden sonra görülen kullanıcıyı etkileyen resmî `main` commitleri.

## Öne çıkan geliştirmeler

- **macOS paketleme düzeltmesi** - `249dc60`: macOS stager's guard artık sadece `*-mac-<arch>.dmg.blockmap` ve `*-mac-<arch>.zip.blockmap` blockmap'larını kabul eder; önceki davranışde `*.blockmap.blockmap` gibi yanlış isimler staging yapılıyordu. Sol review döngüsü tarafından bulunuldu.

- **Commit claim altyapısı güncellemesi** - `main` dalı commit-claim mekanizması `stable-release.yml`'e wire edildi; read-only native legs kullanılarak publisher yetkilendirmesi kitlelendi. 90-day retention politikası başlatıldı.

- **Gizli artifact reddi** - commit-claim artifact'ları içinde gizli/görünmez entries engellendi; malformed build commit'lar deny edildi.

- **Termux claim improve** - Termux claim'ının deb dizininin gerçek bir klasör olması (real directory) şartıyla stage edildi; simbolik linkler veya yanlış yapılar reddedildi.

- **Tagless build fallback** - Default branch main değilse tagless build yapılabilir; fallback Termux base image (digest-pinned) kullanıldı.

- **CI/refactor değişiklikleri** - Paylaşılan Termux build adımları composite action'a çıkarıldı; Termux claim recording ve staging controller job'larına isolate edildi. Persisted credentials invalid edildi ve izinler daraltıldı.

- **Diğer fix'ler** - Dispatch log malformatlaması, release.py command loglama, commit-claim packages R2 secrets okuyucu adımı, validated artifact ID'lar ve GHCR builder image push Engel'i gibi çözüldü.

## Kullanıcı için amacı

Bu etiketlenmemiş çalışma; kullanıcılar macOS paketlerinde blockmap sorunlarından feragat edecek, commit-claim processı daha güvenilir ve clearolacak, Termux deb paketleri daha güvenli bir kontrollerle inşa edilecek, ve release infrastructure daha az arıza ile çalışacak. Kullanıcılar daha az teknik sorunla karşılaşacak ve-agent'ın stabilize release süreci daha güvenilir olacak.

## Kaynak

Bu özet sadece NousResearch/hermes-agent deposunun açık `main` dalındaki ilgili commitlere ve [`v0.23.3...main` karşılaştırma görünümüne](https://github.com/NousResearch/hermes-agent/compare/v0.23.3...main) dayanır. Kararlı sürüm davranışı için asıl kaynak [resmî GitHub yayın notlarıdır](https://github.com/NousResearch/hermes-agent/releases).

## Değişiklik listesi (tam committed list)

- `249dc60308` - fix(release): admit only the macOS packages' own blockmaps
- `...` - further commit-claim and release infrastructure improvements

---

*Bu özet `main` dalının cutting edge değişikliklerini documentación amacıyla toplar. Kararlı sürüm davranışı için [resmî release notları](https://github.com/NousResearch/hermes-agent/releases) Referans alın.*