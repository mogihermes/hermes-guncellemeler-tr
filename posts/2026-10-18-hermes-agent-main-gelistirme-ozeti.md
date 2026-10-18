# Hermes Agent `main` geliştirme özeti — 18 Ekim 2026

> **Kararlılık durumu:** Bu bir sürüm notu değildir. Resmî son sürüm [`v0.22.2`](https://github.com/NousResearch/hermes-agent/releases/tag/v0.22.2); aşağıdakiler `main` dalında bulunan, henüz yeni bir sürüm etiketiyle yayımlanmamış geliştirmelerdir.

- **Karşılaştırma:** [`v0.22.2...main`](https://github.com/NousResearch/hermes-agent/compare/v0.22.2...main)
- **Kapsam:** 17 Ekim özetinden sonra görülen kullanıcıyı etkileyen resmî `main` commitleri.

## Öne çıkan geliştirmeler

- **Eklenti geliştiricileri için skill katalog yardımcıları:** Skill keşfi ve arama yardımcıları herkese açık isimlerle sunuldu: `find_all_skills`, `sort_skills`, `skill_search_dirs`, `locate_skill`, `skill_lookup_path_error`, `dir_hash` ve `read_skill_name`. Bu, eklentilerin skill kataloğu ve araması için desteklenen API adlarını kullanabilmesini hedefliyor. [resmî özellik commit'i](https://github.com/NousResearch/hermes-agent/commit/93fafc4d6fffd10ea31b3d1bd1224d6d98d71679)
- **Eklenti belgeleri:** `locate_skill` işlevinin ikinci parametresinin gerçek adı `local_category_name` olarak düzeltildi; `SKILL.md` okuma örneği `skill_view` ile aynı `utf-8-sig` ve `errors="replace"` ayarını kullanacak biçimde güncellendi. [resmî belge commit'i](https://github.com/NousResearch/hermes-agent/commit/bb834a2cb329b27d67958036039d3e4fe9749a54)

## Kullanıcı için amacı

Bu etiketlenmemiş çalışma, özel eklenti geliştirenler için skill kataloglarını Hermes'in kendi keşif ve arama davranışıyla uyumlu biçimde kullanmayı hedefliyor.

## Kaynak

Bu özet yalnızca NousResearch/hermes-agent deposunun açık `main` dalındaki ilgili commitlere ve [karşılaştırma görünümüne](https://github.com/NousResearch/hermes-agent/compare/v0.22.2...main) dayanır. Kararlı ürün davranışı için asıl kaynak [resmî GitHub yayın notlarıdır](https://github.com/NousResearch/hermes-agent/releases).
