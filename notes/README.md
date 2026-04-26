# notes/

Aktif ideation. Burası agent'ların yazdığı + Bingen'le ortak güncellediğin alan.

## Dosyalar

| Dosya | İçerik | Kim yazar |
|---|---|---|
| `hypotheses.md` | Aktif hipotezler (H1, H2, ...) | `idea-explorer` agent + manuel |
| `graveyard.md` | Elenen hipotezler + neden öldü | `pain-validator` agent (otomatik) |
| `discoveries/H{N}-*.md` | Her hipotez için bulgular + validation | `problem-hunter` + `pain-validator` + `community-mapper` |
| `posts/H{N}-*.md` | Build-in-public post taslakları | `build-in-public-writer` agent |
| `testers.md` | Tester funnel | `tester-funnel` skill |
| `decisions.md` | Efe + Bingen ortak kararları | manuel, tarihli |
| `conflicts.md` | Çatışan kararlar, 24h soğuma alanı | manuel |
| `raw/` | Skill'lerin çektiği büyük JSON/CSV (gitignore'lı) | otomatik |

## Workflow

1. `hypotheses.md`'ye yeni hipotez ekle (idea-explorer veya elle)
2. `/problem-discover H{N}` → `discoveries/H{N}-{date}.md` oluşur
3. `/pain-score H{N}` → aynı dosyaya verdict eklenir
4. GO ise: `/community-map H{N}` → distribution playbook
5. `/build-in-public-post H{N} reddit` (veya başka platform) → `posts/H{N}-reddit-{date}.md`
6. Post yayınla → `/tester-funnel add` ile her ilgi gösteren kişiyi `testers.md`'ye

## Kurallar

- `discoveries/` ve `posts/` dosyalarına asla manuel paraphrase yazma — verbatim quote zorunlu
- `decisions.md`'ye yazılan her karar tarihli + her iki imzalı (Efe ✓ Bingen ✓)
- `graveyard.md`'den asla silme — öğrenme arşivi
