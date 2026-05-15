# Övningar till kapitel 8: När regler, undantag och verksamhetslogik styr kraven

## Syfte

Övningarna hjälper dig att träna på att synliggöra verksamhetsregler, undantag och beslutspunkter i funktionella krav utan att skapa ett tungt kravdokument.

## Övning 1: Hitta dold regelstyrning

Välj ett funktionellt krav från ett pågående eller tidigare arbete.

1. Markera ord som kan dölja regler, till exempel:
   - behörig,
   - komplett,
   - giltig,
   - korrekt,
   - relevant,
   - enligt regelverk,
   - vid behov,
   - särskilda fall.
2. Skriv fem frågor som behöver besvaras innan kravet kan bli testbart.
3. Ange vilka roller som behöver vara med för att besvara frågorna.

## Övning 2: Skapa en beslutstabell

Utgå från kravet:

> Systemet ska avgöra om en digital ansökan kan skickas in.

Skapa en beslutstabell med minst fyra villkor och tre möjliga utfall.

Exempel på villkor:

- ärendetyp,
- sökanderoll,
- obligatorisk bilaga,
- befintligt ärende,
- skyddade personuppgifter,
- komplettering krävs.

Exempel på utfall:

- ansökan kan skickas in,
- ansökan stoppas med felmeddelande,
- ansökan kräver manuell granskning,
- komplettering ska begäras.

## Övning 3: Sortera undantag

Lista fem undantag från ett kravområde du känner till.

Sortera varje undantag i en av följande grupper:

1. Måste hanteras nu.
2. Måste förstås nu men kan byggas senare.
3. Kan vänta.
4. Ska inte hanteras.

Motivera varje placering med en mening.

## Övning 4: Skapa en enkel regelkatalog

Skapa en tabell med minst fem regler.

Använd kolumnerna:

| Regel | Källa | Tolkning beslutad av | Ägare | Påverkar | Hur testas regeln? |
|---|---|---|---|---|---|

Reflektera sedan över:

- Vilka regler är stabila?
- Vilka regler kan ändras?
- Vilka regler saknar tydlig ägare?
- Vilka regler påverkar flera funktioner?

## Reflektionsfrågor

1. Var i ert nuvarande arbetssätt riskerar verksamhetsregler att försvinna eller misstolkas?
2. Vilka undantag brukar upptäckas sent?
3. Hur kan ni skilja mellan regler som måste byggas nu och regler som bara måste förstås nu?
4. Vilken minsta dokumentationsform skulle räcka för att göra reglerna användbara för teamet?
