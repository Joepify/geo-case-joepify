# Case: GEO/AEO-optimalisatie van een Nederlandse webstudio in één dag (oktober 2026)

Wat we op [joepify.nl](https://www.joepify.nl) (±200 pagina's, statische HTML, Nederlands) deden om beter gevonden en geciteerd te worden door ChatGPT, Copilot, Perplexity en Google AI-overzichten, met de gemeten scores ervoor en erna. Alle metingen zijn gedaan met open-source tools op 22 oktober 2026.

## Gemeten resultaat
| Meting (tool) | Voor | Na |
|---|---|---|
| GEO-score sitebreed, 40 pagina's ([geo-optimizer-skill](https://github.com/Auriti-Labs/geo-optimizer-skill)) | 80 (25 pagina's) | 86,6 |
| GEO-score homepage (idem) | 77 | 91 |
| AEO-audit, 16 checks ([gtm-engineer-skills](https://github.com/onvoyage-ai/gtm-engineer-skills)) | 97 | 97 (16/16) |
| Citeerbaarheid, 12 belangrijkste pagina's (citability scorer uit [geo-seo-claude](https://github.com/zubair-trabzada/geo-seo-claude), aangepast voor Nederlands) | ~41 | ~60 |
| Structured data: echte fouten (eigen strikte check) | 13 FAQ-items onzichtbaar, 2 bedrijfs-entiteiten | 0 |

## Belangrijkste bevinding
robots.txt liet alle AI-crawlers toe, maar de **firewall van de hostingpartij gaf GPTBot, ClaudeBot, CCBot, MistralAI-User en anderen een 403**. De zoekbots (OAI-SearchBot, ChatGPT-User, Claude-SearchBot, PerplexityBot, bingbot, Googlebot) kwamen wel binnen. Zonder test zie je dat niet. Tool: [ai-crawler-access-check](https://github.com/Joepify/ai-crawler-access-check).

## Wat we veranderden
1. **Toegang:** robots.txt met expliciete AI-groep en Content-Signal; UTF-8 in de HTTP-header (zonder charset maakten fetchers van "€1.499" iets onleesbaars); llms.txt, llms-full.txt, RSS-feed, /ai/summary.json.
2. **Eén entiteit:** de blog gebruikte een tweede, losse bedrijfs-@id; samengevoegd tot één `#organization` op 166 pagina's, met `sameAs` (LinkedIn, Google Maps, GitHub) en de eigenaar als auteur (Person) op 49 blogartikelen.
3. **Antwoord eerst:** "In het kort"-blokken op 29 pagina's; een antwoordblok van ~40 woorden onder de H1 op nieuwe pagina's.
4. **Vraag-koppen en zelfstandige secties:** ~45 pagina's herschreven naar vraag-H2's met secties van 120-170 woorden die op zichzelf te citeren zijn.
5. **Bronnen en eigen data:** per zwakke sectie maximaal één statistiek en één citaat uit een officiële bron (Google, OpenAI, php.net, WordPress.org, KvK, ACM), volgens het GEO-onderzoek van Aggarwal e.a. ([KDD 2024, arXiv 2311.09735](https://arxiv.org/abs/2311.09735)), plus cijfers uit eigen onderzoek ([DOI 10.5281/zenodo.23561392](https://doi.org/10.5281/zenodo.23561392)).
6. **Consistentie:** één webshopprijs op 36 pagina's (AI vertrouwt tegenstrijdige prijzen minder); zichtbare FAQ gelijk aan FAQPage-schema.
7. **Nieuwe pagina's** voor onbezette zoekvragen uit Search Console en Google autocomplete (o.a. webbureau Rotterdam, maatwerk software Rotterdam, WordPress specialist Rotterdam, gevonden worden in ChatGPT).

## Wat (nog) niet werkt en waarom
- **Merk buiten de site** (score 18/100): weinig reviews en profielen op platforms die AI-antwoorden citeren. On-site werk lost dat niet op.
- **Training-crawlers geblokkeerd** door de host: oplossen via de host of een CDN-laag. Open data op GitHub en Zenodo bereikt die crawlers wel.

## Lessen
- Test wat bots **echt** krijgen, niet alleen robots.txt.
- Een score van 100 op "citeerbaarheid" is geen doel: gedwongen statistieken in elke sectie maken tekst slechter. Kwaliteit en echte bronnen winnen.
- Eigen data (onderzoek, metingen) is het sterkste wat je kunt publiceren.

Gemaakt door Ayoub Assaidi, [Joepify](https://www.joepify.nl), Rotterdam. Zie ook [geo-aeo-checklist-nl](https://github.com/Joepify/geo-aeo-checklist-nl) en [gevonden worden in ChatGPT](https://www.joepify.nl/gevonden-worden-in-chatgpt). Licentie: CC BY 4.0.
