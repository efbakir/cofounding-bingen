# Agents

5 subagent. Her biri zincirde tek iş yapar, çıktısını ana Claude'a döner.

| Agent | Model | Sorumluluk |
|---|---|---|
| `idea-explorer` | opus | Ham fikirleri 3-4 test edilebilir hipoteze indirir |
| `problem-hunter` | opus | Bir hipotezi alıp Reddit/HN/X/IH'ta o problemin gerçek izlerini bulur |
| `pain-validator` | opus | Bulunan thread'leri intensity × frequency × WTP üzerinden skorlar |
| `community-mapper` | opus | Bu kullanıcılar nerede toplanıyor (sub, Discord, takip ettikleri) |
| `build-in-public-writer` | opus | Bulgulardan IH/Reddit/X postu taslağı yazar, tester recruit eder |

## Tipik zincir

```
idea-explorer  →  problem-hunter  →  pain-validator
                                       ↓
            build-in-public-writer  ←  community-mapper
```

## Model seçimi neden hepsi opus?

Bu repo hızdan değil, **karar kalitesinden** kazanır. Bir yanlış pozitif "para verir bunlara" → haftalarca yanlış yöne build. Sonnet bazı agent'larda yeterli olur ama default opus, custom override için her agent'ın frontmatter'ında `model:` satırı var — düşürmek istersen oradan.

(Efe'nin kişisel tercihi: model downgrade yapma. Memory'deki [feedback_model_choice.md](https://github.com/efbakir/...) — tüm subtask'lar opus.)

## Kurulum

Bu dosyaları `~/.claude/agents/` (global) veya `.claude/agents/` (proje) altına kopyala. Detay: ana README.
