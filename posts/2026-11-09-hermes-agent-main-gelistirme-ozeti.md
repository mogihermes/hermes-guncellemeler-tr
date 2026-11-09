# Hermes Agent `main` geliştirme özeti — 9 Kasım 2026

> **Kararlılık durumu:** Bu bir sürüm notu değildir. Resmî son sürüm [`v0.23.0`](https://github.com/NousResearch/hermes-agent/releases/tag/v0.23.0); aşağıdakiler `main` dalında bulunan, henüz yeni bir sürüm etiketiyle yayımlanmamış geliştirmelerdir.

> **Kapsam:** 4 Kasım (veya önceki özet) özetinden sonra görülen kullanıcıyı etkileyen resmî `main` commitleri.

## Öne çıkan geliştirmeler

- **Telegram topic recovery pinlendi** - `0c36055`: Konu topic'i geri alınması için chat-prompt fallback ve unmoved-thread guard pinlendi. Önceki mesajların tekrar okunmasını önler.
- **Telegram root DM topic transferı düzeltilmiş** - `fe54b16`: Konuya auto transfer yapılan root DM'ler, topic'ın prompt girişlerini doğru taşır.
- **Recovered topic mesajı prompt girişlerini taşır** - `800826b`: Geri alınılan topic mesajı, topic'ın prompt girişlerini taşır.
- **Telegram other-bot skip log edildi** - `56e9d96`: Observation modunda other-bot atlanması loglanmıştır.
- **Telegram group command argumenleri yazı olarak gönderildi** - `09b17f4`: Group komutlarının argümanları ve hedefi yazı olarak gönderilmiştir.
- **Telegram group mesajları leading handle ile adresatıldı** - `a6c1dfb`: Group mesajları leading handles ile adresatıldı; `/cmd@bot` argümanlarını korur.
- **Teleforum topic reply anchor gate** - `7636137`: Forum topic reply anchor gate KoNit-K ve teknium1 tarafından düzeltilmiştir.
- **Teleforum mention gating free-response chats ve topics** - `bcfa713`: Maintain bots_require_mention on free-response chats and topics.
- **Telegram refusal toast pinlendi clarify tap** - `c3354ea`: Clarify tap'tan refusal toast pinlendi.
- **Telegram clarify dict[type, ClarifyPrompt] olarak türlendi** - `0eb1493`: Clarify prompt `_clarify_state` olarak dict[str, ClarifyPrompt] türlendi.
- **Telegram clarify sadece kendi prompt mesajından çözülür** - `47c7600`: Clarify, sadece kendi prompt mesajından çözülen refusal.
- **Telegram link-preview edit'leri disable_option carry etme** - `022a144`: Prompt-resolving edits link-preview seçeneğini carry etmemesi için düzeltilmiştir.
- **Telegram link-preview testleri is_disabled=True** - `60dc0a7`: Link-preview edit testleri is_disabled=True gerektiriyor.
- **Telegram legacy edit'ler disable_link_previews honor ediliyor** - `46a7c67`: Legacy edits, disable_link_previews (#61018, salvage #61022) honor ediliyor.
- **Gateway rowless-binding repair CAS refuses mid-lookup** - `b479868`: Gateway rowless-binding repair, CAS refuses a binding cleared mid-lookup.
- **Gateway observed native-image turns persist pre-wrap** - `392c588`: Gateway observed native-image turns, pre-wrap message persistence.
- **Gateway group transcript rows epoch floats stamped** - `606967f`: Gateway group transcript rows, epoch floats ile stamped.
- **Gateway persist clean observed image turns** - `eeb54f9`: Gateway persist clean observed image turns.
- **Gateway exec-approval delivery boundaries logged** - `7e7dfd4`: Gateway exec-approval delivery boundaries triage için loglanıyor.
- **Gateway edited /goal kicks off as own turn** - `eac24f9`: Edited /goal, admission_conflict yerine kendi turn'ını kick off eder.
- **Gateway edited /queue or /steer mid-turn queues instead** - `fbaa6d8`: Edited /queue or /steer mid-turn, queues instead of admission_conflict.
- **Telegram core early-return receipts ve failed-prep reporting pinlendi** - `edb9736`: Core early-return receipts ve failed-prep reporting pinlendi.
- **Telegram shutdown admission claim releases bekler; queued update cancelled** - `2b0337e`: Shutdown admission claim releases bekler; queued update cancelled before entry closes handler.
- **Aux fallback walk lanes zaten denenmiş gibi geçmez** - `8d7061f`: Fallback walk, zaten denenmiş lane'ları tekrar geçmemeyi sağlar.
- **Refreshed fallback candidate other model'de quarantined** - `632edf2`: Refreshed fallback candidate, başka model'de quarantined olur.
- **Custom route main runtime identity only at origin** - `73ec436`: Custom route, main runtime identity'ni sadece orijinde alır.
- **Payment error same-host custom endpoint, session provider değil** - `3e0dda7`: Payment error, aynı-host custom endpoint, session provider'si benches.
- **Fallback candidate credential refresh parameter repairs korur** - `535477e`: Fallback candidate credential refresh, parameter repairs korur.
- **Custom route main runtime identity only on relay path** - `897ee4a`: Custom route, main runtime identity'ni sadece relay path'de alır.
- **Model-aware peek current key cooled down for that model** - `47053c7`: Model-aware peek, current key cooled down for that model survives.
- **Parameter repair pool rotation retry survives** - `3253e57`: Parameter repair, pool rotation retry survives.
- **Parameter repair also survives pool rotation retry** - `1482adf`: Parameter repair, also survives pool rotation retry.
- **Fallback candidate backend tag classification provider** - `4b74783`: Fallback candidate backend tag, classification provider picks.
- **Content-policy refusal with quota wording sent once** - `d98f790`: Content-policy refusal with quota wording, once gönderilir.
- **Two guards at paths where behaviour changed** - `38d4de8`: Two guards at paths where behaviour changed.
- **Policy refusal quota wording benches provider** - `3c8d925`: Policy refusal quota wording, provider benches.
- **Error-classifier drop bare "credits" account-wall token** - `90b40ad`: Error-classifier, bare "credits" account-wall token dropped.
- **Streamed certificate failure test also pins the fallback** - `cf7b294`: Streamed certificate failure test, also pins the fallback.

## Kullanıcı için amacı

Bu etiketlenmemiş çalışma; Telegram bot connectivity'si (topic recovery, DM handling, group chat addressing), gateway odası stabilitesi (bot list, group chats, image persistence), ve auxiliary refined fallback seçim mekanizmalarının kullanıcı deneyimini iyileştirmesi hedefliyor. Kullanıcılar artık topic'lar daha güvenilir şekilde geri alınabileceği, gateway odaları daha az hata ile çalışacaği ve hata raporları daha duidelijk feedback alabileceği için Beklentiler daha yönetilebilir hale geliyor.

## Kaynak

Bu özet sadece NousResearch/hermes-agent deposunun açık `main` dalındaki ilgili commitlere ve [v0.23.0...main karşılaştırma görünümüne](https://github.com/NousResearch/hermes-agent/compare/v0.23.0...main) dayanır. Kararlı ürün davranışı için asıl kaynak [resmî GitHub yayın notlarıdır](https://github.com/NousResearch/hermes-agent/releases).