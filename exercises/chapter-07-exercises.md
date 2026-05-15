# Övningar till kapitel 7: Acceptanskriterier, testbarhet och gemensam definition av klart

## Syfte

Övningarna tränar dig i att göra funktionella krav testbara utan att göra kravunderlaget onödigt tungt.

## Övning 1: Gör ett vagt krav testbart

Utgå från formuleringen:

> Handläggaren ska enkelt kunna se relevanta kompletteringar.

Skriv om den till:

1. en tydligare kravformulering,
2. minst fyra acceptanskriterier,
3. minst ett negativt acceptanskriterium,
4. två öppna frågor som behöver besvaras innan kravet är redo nog.

### Stödfrågor

- Vilken handläggare avses?
- Vilken ärendestatus gäller?
- Vad betyder “relevant” i den här situationen?
- Vilka uppgifter måste visas?
- Finns information som inte får visas?
- Hur kan teamet verifiera att kriteriet är uppfyllt?

## Övning 2: Skilj mellan nivåerna

Placera varje formulering på rätt nivå:

- kravformulering,
- acceptanskriterium,
- testfall,
- Definition of Done.

Formuleringar:

1. När sökanden laddar upp en PDF inom tidsfristen ska filen sparas på rätt ärende.
2. Logga in som sökande, öppna ärende 123 och ladda upp filen test.pdf.
3. Som sökande vill jag kunna skicka in kompletterande handlingar digitalt.
4. Relevanta tester är genomförda och dokumentation är uppdaterad.
5. Otillåtna filtyper ska stoppas.
6. Koden är granskad enligt teamets överenskommelse.
7. Som handläggare vill jag se inkomna kompletteringar så att jag kan fortsätta handläggningen.
8. Skapa ett ärende med status KOMPL_BEGÄRD och kontrollera att kompletteringssidan visas.

## Övning 3: Hitta vad som ska flyttas

Läs formuleringen:

> Givet att sökanden är inloggad med e-legitimation, har ett ärende med status KOMPL_BEGÄRD, har fått kompletteringsbegäran enligt mall M-14, laddar upp en PDF, DOCX eller JPG under 20 MB, inom 14 kalenderdagar från beslutsdatum, och handläggaren tillhör rätt organisatorisk enhet, så ska filen sparas, diarieföras, visas för handläggaren, ge kvittens och markera ärendet som komplettering mottagen.

Dela upp innehållet i:

- acceptanskriterium,
- stabil regelinformation,
- testdata eller testfall,
- möjlig separat story,
- öppna frågor.

## Övning 4: Skapa gemensam definition av klart

Arbeta med ett kravområde från din egen verksamhet eller använd scenariot med digital komplettering.

Formulera en enkel Definition of Done för funktionella krav i teamet. Den ska innehålla högst åtta punkter.

Tänk på:

- acceptanskriterier,
- test,
- dokumentation,
- beslut och avgränsningar,
- verksamhetsgranskning,
- regler och spårbarhet,
- förvaltning.

## Reflektion

Svara kort på frågorna:

1. Vilka vaga ord använder ni ofta i krav?
2. Vem avgör i praktiken om något är “klart”?
3. Var brukar acceptansdiskussionen komma för sent?
4. Vilken information hamnar ofta i fel artefakt?
5. Vilken liten förändring skulle göra era krav mer testbara redan nästa vecka?
