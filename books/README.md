# books/

Startup-shaping kitapları. PDF/EPUB push'lanmaz (`.gitignore`'da); sadece notlar `books/notes/` altına gider, agent'lar bunları okur.

## Önerilen okuma sırası (problem-discovery + build-in-public flow için)

| # | Kitap | Yazar | Neden |
|---|---|---|---|
| 1 | **The Mom Test** | Rob Fitzpatrick | Validation yaparken yanlış soruları sormamak için. `pain-validator` agent'ının doğal uzantısı. |
| 2 | **Demand-Side Sales 101** | Bob Moesta | "Job to be done" framework'ünün sade hali. `idea-explorer` "kim, neden, ne işe alıyor" netleşsin diye. |
| 3 | **The Lean Startup** | Eric Ries | Build-measure-learn döngüsü ve MVP tanımı. Repo'nun mental model'i bunun üstüne kurulu. |
| 4 | **Hooked** | Nir Eyal | Habit-forming product loop. `tester-funnel` "using → converted" dönüşü için referans. |
| 5 | **Traction** | Gabriel Weinberg | 19 traction kanalı. `community-mapper` çıktısının başucu kontrol listesi. |
| 6 | **The Cold Start Problem** | Andrew Chen | Network effects + atomic network konsepti. Eğer marketplace/community yönüne kayarsa. |
| 7 | **Working Backwards** | Bryar & Carr | Amazon'un PR-FAQ tekniği. `idea-explorer`'a hipotezi "press release" olarak yazdırmak için. |
| 8 | **Crossing the Chasm** | Geoffrey Moore | Early adopter → mainstream geçişi. Validation'dan sonra, scale öncesi. |
| 9 | **Blue Ocean Strategy** | Kim & Mauborgne | Differentiation framework. `competitor-analysis` skill'inin yanında okunmalı. |
| 10 | **Zero to One** | Peter Thiel | "Hangi gerçeği biliyorsun ki başka kimse bilmiyor?" sorusu — `idea-explorer`'a manşet sorusu. |

## Klasör yapısı

```
books/
├── README.md         (bu dosya)
├── notes/            (markdown notlar — version'lanır)
│   ├── mom-test.md
│   ├── lean-startup.md
│   └── ...
└── *.pdf / *.epub    (gitignore'lı, sadece local)
```

## Not formatı

Her kitap için `books/notes/{slug}.md`:

```markdown
# {Title} — {Author}

**Read**: YYYY-MM-DD
**Pillar**: {discovery / build / sell / scale / mindset}

## TL;DR
{3-5 cümle. Kitabı okumamış birine bu repo'da ne işe yaradığını anlatır.}

## Frameworks (agent'lar için)
{İsmi olan, transferable framework'ler. Örnek: "Mom Test'in 3 anti-pattern'ı: kompliman avı, hipotezi söyleyip onay arama, gelecek vaadleri ısrarı".}

## Quotes
> "{verbatim, sayfa numarasıyla}"

## Bu repo için ne anlama geliyor
- `idea-explorer` agent'ında: ...
- `pain-validator` agent'ında: ...
```

## Agent'lar bunları nasıl kullanır

`idea-explorer` agent'ı çalıştığında `Read`, `Glob` ile `books/notes/*.md` taraması yapıyor — "Frameworks" bölümlerini öncelikli alıyor. Bir kitap notu eklersen, agent bir sonraki çalışmasında otomatik kullanır.
