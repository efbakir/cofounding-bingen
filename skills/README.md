# Skills

5 skill, her biri agent zincirinin bir adımı için. Skill'ler agent'lardan farklı: agent karar verir, skill yapar.

| Skill | Slash | Çağıran agent | Ne yapar |
|---|---|---|---|
| `problem-discover` | `/problem-discover` | problem-hunter | Hipotezi alıp arama query'leri üretir, Reddit/HN/IH/X'te koşturur |
| `community-map` | `/community-map` | community-mapper | Validated hipotez için sub/Discord/influencer haritası çıkarır |
| `pain-score` | `/pain-score` | pain-validator | Bir thread/finding'i intensity × frequency × WTP üzerinden skorlar |
| `build-in-public-post` | `/build-in-public-post` | build-in-public-writer | Platform-specific post taslağı yazar |
| `tester-funnel` | `/tester-funnel` | (manuel) | İlgi gösterenleri funnel stage'lerine göre günceller |

## Topluluk skill entegrasyonu

Bu skill'ler aşağıdaki community skill'leri "varsa kullan" prensibiyle çağırır:

| Skill | Repo | Bizim hangi skill kullanır |
|---|---|---|
| `redditlens` | [0xMassi/redditlens](https://github.com/0xMassi/redditlens) | `problem-discover` (Reddit kanalı için tercihli) |
| `reddit-skill` | [brisyramshere/reddit-skill](https://github.com/brisyramshere/reddit-skill) | `problem-discover` (fallback) |
| `mine-calls` | [maxionmain321/claude-code-skills](https://github.com/maxionmain321/claude-code-skills) | `pain-score` (cluster schema için referans) |
| `persona-builder` | Anthropic | `community-map` (kullanıcı persona çıkarımı) |
| `competitor-analysis` | Anthropic | `pain-score` ("zaten çözülmüş mü?" kontrolü) |

Yoksa skill'ler kendi yedek path'lerini koşturur (Reddit JSON endpoint, HN Algolia API gibi auth gerektirmeyen kaynaklar).

## Kurulum

```bash
cp -r skills/* .claude/skills/      # proje seviyesi
# veya
cp -r skills/* ~/.claude/skills/    # global
```

## API key'leri

`.env` dosyasında (gitignore'lı):

```
SERPER_API_KEY=...      # redditlens için (opsiyonel)
REDDIT_CLIENT_ID=...    # reddit-skill için (opsiyonel)
REDDIT_CLIENT_SECRET=...
XQUIK_API_KEY=...       # x-twitter-scraper için (opsiyonel)
```

Hiçbiri yoksa skills HN Algolia + Reddit public JSON ile sınırlı çalışır — yine de işe yarar, sadece daha az source.
