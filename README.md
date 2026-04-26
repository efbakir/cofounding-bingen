# cofounding-bingen

Bingen ile startup ideation lab'ı. Hipotez → Reddit/HN/X üzerinde gerçek "para vermeye hazır" şikayet sinyali → build in public → tester funnel.

Yapı [selmakcby/claude-agents-skills](https://github.com/selmakcby/claude-agents-skills) modelini takip ediyor; agent ve skill'ler bu repo için özel yazılmış.

---

## Çekirdek tez

> Para vermeye hazır müşteri = yüksek frekansta + yüksek şiddetle şikayet eden, çözüm için zaten bir şey deneyen, ticket bedeli yüksek olan.

Repo bu tezi operasyonel hale getiriyor:

1. **Discover** — bir problem hipotezi ver, agent'lar Reddit/HN/X/IH'da o problemden bahseden insanları bulur.
2. **Map** — bu insanlar nerede takılıyor? Hangi subreddit, hangi Discord, hangi influencer'ı takip ediyor?
3. **Score** — bulunan thread'leri pain intensity × frequency × WTP (willingness-to-pay) sinyaline göre sıralar.
4. **Build in public** — bulgulardan Reddit/IH/X postu yazar; "şu problemi çözen şeyi yapıyoruz, test eder misin?" formatında.
5. **Funnel** — gelen ilgilileri `notes/testers.md`'de takip eder.

---

## Klasörler

| Klasör | İçerik |
|---|---|
| `agents/` | 5 subagent tanımı — `~/.claude/agents/` veya `.claude/agents/` altına kopyala |
| `skills/` | 5 skill — `~/.claude/skills/` veya `.claude/skills/` altına kopyala |
| `books/` | Startup-shaping kitapları (PDF, EPUB, markdown notlar) |
| `notes/` | Aktif ideation: hipotezler, validation log'u, tester funnel |
| `CLAUDE.md` | Repo-level kurallar (Bingen ile çalışırken Claude'a context) |

---

## Kurulum

### 1. Repo'yu klonla
```bash
git clone git@github.com:efbakir/cofounding-bingen.git
cd cofounding-bingen
```

### 2. Agent + skill'leri proje seviyesi olarak kur
Bu repo içinde Claude Code açtığında otomatik yüklenmesi için:
```bash
mkdir -p .claude/agents .claude/skills
cp agents/*.md .claude/agents/
cp -r skills/* .claude/skills/
```

Veya global olarak (her projede kullanmak için):
```bash
cp agents/*.md ~/.claude/agents/
cp -r skills/* ~/.claude/skills/
```

### 3. (Opsiyonel) Topluluk skill'leri
Aşağıdaki skill'ler bizim flow ile direkt eşleşir; yüklersen agent'lar bunları otomatik tercih eder:

| Skill | Repo | Ne işe yarar |
|---|---|---|
| `redditlens` | [0xMassi/redditlens](https://github.com/0xMassi/redditlens) | Reddit'te pain-point clustering. **Drop-in.** Serper API key ister. |
| `reddit-skill` | [brisyramshere/reddit-skill](https://github.com/brisyramshere/reddit-skill) | Resmi Reddit OAuth — search, comment-tree extract. Free. |
| `mine-calls` | [maxionmain321/claude-code-skills](https://github.com/maxionmain321/claude-code-skills/tree/main/skills/mine-calls) | Pain → exact quote → channel-angle mapping schema |
| `persona-builder` | Anthropic skills (zaten env'de) | Voice-of-customer → segment |
| `competitor-analysis` | Anthropic skills (zaten env'de) | "Bu zaten çözülmüş mü?" |

---

## Tipik akış

Yeni bir hipotezle çalışırken:

```
1. notes/hypotheses.md'ye yeni hipotezi ekle (template aşağıda)
2. Claude Code'da: "problem-hunter agent'ını çağır, şu hipotezi araştır: <hipotez>"
   → agent Reddit/HN/X tarar, ham bulguları notes/discoveries/<slug>.md'ye yazar
3. "pain-validator agent'ı bulguları skorla"
   → her thread için intensity × frequency × WTP skoru
4. "community-mapper agent'ı bu insanların hangi communities'lerde takıldığını çıkar"
5. "build-in-public-writer agent'ı bu bulgulardan IH ve Reddit post taslakları yaz"
6. Postu yayınla → ilgi gösterenleri notes/testers.md'ye ekle
```

İdeation seansında sadece **idea-explorer** agent'ını çağırırsın; o ham fikirleri 3-4 hipoteze daraltır, sonra zincir başlar.

---

## Bingen ile co-working

Bu repo public ve build-in-public stratejisinin parçası. Bingen ve Efe ortak çalışırken:

- Her hipotez için PR aç, validation log'u review et
- `notes/decisions.md`'de iki kişinin ortak verdiği kararlar
- Çatışma → kararı `notes/conflicts.md`'ye yaz, 24 saat bekle, sonra konuş

---

## Lisans

MIT
