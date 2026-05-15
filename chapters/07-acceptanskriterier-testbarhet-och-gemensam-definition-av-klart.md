# Kapitel 7: Acceptanskriterier, testbarhet och gemensam definition av klart

## Varför detta kapitel finns

I föregående kapitel såg vi hur funktionella krav kan brytas ned till mindre, utvecklingsbara delar. Det är ett viktigt steg, men det räcker inte. Ett krav kan vara lagom stort och ändå vara svårt att bygga om teamet inte förstår vad som ska gälla när funktionen är klar.

Det är här acceptanskriterier och testbarhet kommer in.

I fasbaserat kravarbete hamnar acceptansen ofta sent. Kravet skrivs först, lösningen byggs senare och test eller granskning avgör i efterhand om leveransen motsvarar förväntningarna. Det kan fungera när kravbilden är stabil och alla tolkar formuleringarna likadant. Men när utvecklingen sker iterativt, och flera roller behöver fatta beslut löpande, blir sena acceptansdiskussioner riskabla.

För Karin märks det när utvecklingsteamet frågar:

> Hur vet vi att den här storyn är klar?

Hon kan svara med en längre kravbeskrivning, men det hjälper inte alltid. Teamet behöver veta vilka beteenden som ska finnas, vilka regler som ska gälla, vilka undantag som ska hanteras och vad som kan vänta. Testaren behöver veta vad som ska verifieras. Produktägaren behöver veta vad som är accepterbart. Verksamheten behöver känna igen sin process. Förvaltningen behöver förstå vad som faktiskt har beslutats.

Det här kapitlet handlar om hur Karin kan hjälpa teamet att formulera acceptanskriterier som gör funktionella krav testbara och begripliga.

Tre huvudbegrepp står i centrum:

- **acceptanskriterium**,
- **testbarhet**,
- **Definition of Done**.

Målet är inte att skapa perfekta formuleringar. Målet är att skapa tillräckligt tydliga villkor för att team, produktägare och verksamhet ska kunna avgöra om nästa utvecklingsbara del är klar nog att leverera, visa, testa eller bygga vidare på.

## Lärandemål

Efter kapitlet ska du kunna:

- förklara varför acceptanskriterier behövs i agilt kravarbete,
- skilja mellan kravformulering, acceptanskriterium, testfall och Definition of Done,
- skriva acceptanskriterier som beskriver observerbart beteende,
- identifiera vaga formuleringar som behöver göras testbara,
- använda exempel för att upptäcka regler, undantag och missförstånd,
- hjälpa teamet skapa gemensam förståelse för vad “klart” betyder.

## Innan vi börjar

I kapitel 3 såg vi att kravunderlag kan vara levande och bestå av flera artefakter. Acceptanskriterier är en sådan artefakt. De behöver inte bära hela kravbilden, men de spelar en viktig roll i att knyta samman behov, beteende och verifiering.

I kapitel 5 såg vi att kravdialog handlar om att skapa gemensam förståelse. Acceptanskriterier är ett konkret sätt att få fram om förståelsen verkligen är gemensam.

I kapitel 6 såg vi att funktionella krav behöver bli små nog att utvecklas. När ett krav har blivit utvecklingsbart behöver det också bli tillräckligt testbart. Annars finns risken att teamet bygger något som verkar rätt, men som olika personer bedömer på olika sätt.

## Situationen: alla håller med tills någon frågar vad som räknas som klart

Karin arbetar vidare med funktionen för digital komplettering av ansökan. Efter nedbrytningen finns en första prioriterad story:

> Som sökande vill jag kunna ladda upp en kompletterande handling så att myndigheten kan fortsätta handlägga mitt ärende.

Vid första anblicken verkar den tydlig. Produktägaren tycker att den är viktig. Teamet förstår ungefär vad som ska byggas. Testaren ser att den borde gå att verifiera.

Men under refinement ställer testaren frågan:

> Vad måste fungera för att vi ska kunna säga att den här storyn är klar?

Samtalet blir snabbt mer komplicerat.

En utvecklare frågar om den sökande ska kunna ladda upp flera filer eller bara en. En handläggare frågar om kompletteringen måste kopplas till rätt ärende automatiskt. En säkerhetsspecialist undrar vilka filtyper som får användas. Produktägaren vill veta om kvittens måste ingå i första versionen. Juristen frågar om kompletteringen ska diarieföras direkt eller först när handläggaren granskar den.

Karin känner igen situationen. I ett fasbaserat arbetssätt hade många av dessa frågor kanske hamnat i en kravspecifikation, ett regelavsnitt, ett granskningsprotokoll eller ett testdokument. Nu behöver teamet förstå tillräckligt mycket innan utvecklingen startar, men utan att försöka lösa hela framtida funktionaliteten på en gång.

Det är inte ett tecken på att storyn är dålig. Det är ett tecken på att acceptansen ännu är otydlig.

## Vad är ett acceptanskriterium?

Ett acceptanskriterium är ett villkor som behöver vara uppfyllt för att ett krav, en story eller en funktionell del ska kunna accepteras.

Det beskriver inte allt om lösningen. Det ersätter inte behovsanalys, processbeskrivning, regelbeskrivning eller testfall. Det gör något mer avgränsat:

> Det anger vad som måste vara sant för att vi ska kunna säga att denna del fungerar enligt överenskommen förväntan.

Ett bra acceptanskriterium är ofta:

- konkret,
- observerbart,
- testbart,
- kopplat till användning eller verksamhetsregel,
- tillräckligt avgränsat för den aktuella delen,
- begripligt för både verksamhet och team.

Exempel på svagt acceptanskriterium:

> Uppladdning ska fungera bra.

Det säger nästan ingenting. Vad betyder “fungera”? Vad betyder “bra”? För vem? I vilken situation?

Ett tydligare acceptanskriterium kan vara:

> När den sökande laddar upp en tillåten filtyp som är mindre än maxstorleken ska filen sparas på ärendet och visas i listan över inskickade kompletteringar.

Här går det att observera beteendet. Antingen sparas filen på ärendet och visas i listan, eller så gör den inte det. Kriteriet väcker också följdfrågor: vilka filtyper är tillåtna, vad är maxstorleken och vilken lista avses? Det är bra. Acceptanskriterier ska inte dölja frågor. De ska hjälpa teamet att hitta dem.

## Krav, acceptanskriterium, testfall och Definition of Done

Karin märker att orden ibland blandas ihop. Någon säger “acceptanskriterier” men menar testfall. Någon säger “klart” men menar att koden är färdig. Någon säger “kravet är uppfyllt” men menar att verksamheten har godkänt helheten.

För att skapa tydlighet använder Karin fyra nivåer.

### Kravformulering

Kravformuleringen beskriver vad som behövs och varför. Den kan vara en user story, ett användningsfall, en regelbeskrivning eller en annan form av kravartefakt.

Exempel:

> Som sökande vill jag kunna ladda upp en kompletterande handling så att myndigheten kan fortsätta handlägga mitt ärende.

Kravformuleringen ger riktning, men den räcker inte alltid för att avgöra om funktionen är klar.

### Acceptanskriterium

Acceptanskriteriet beskriver villkor för acceptans av just denna del.

Exempel:

> Om den sökande försöker ladda upp en otillåten filtyp ska uppladdningen stoppas och ett begripligt felmeddelande visas.

Det är mer specifikt än kravformuleringen, men fortfarande inte ett fullständigt testfall.

### Testfall

Testfallet beskriver hur någon faktiskt verifierar beteendet.

Exempel:

1. Logga in som sökande med ett ärende där komplettering är begärd.
2. Gå till kompletteringssidan.
3. Välj en fil med otillåten filtyp.
4. Försök ladda upp filen.
5. Kontrollera att filen inte sparas.
6. Kontrollera att felmeddelande visas.

Testfallet kan vara manuellt, automatiserat eller delvis automatiserat. Det är mer detaljerat än acceptanskriteriet.

### Definition of Done

Definition of Done beskriver gemensamma kvalitetsvillkor som gäller för en viss typ av arbete, ofta på team- eller produktnivå. Den är inte unik för en story, utan återkommer.

Exempel:

- Koden är granskad.
- Relevanta tester är genomförda.
- Dokumentation är uppdaterad där det behövs.
- Tillgänglighetskrav som gäller för ändringen är kontrollerade.
- Beslut eller avgränsningar är dokumenterade.
- Inga kända blockerande fel finns kvar.

Definition of Done svarar på frågan:

> Vilka generella villkor behöver vara uppfyllda innan teamet kan betrakta arbetet som klart?

Acceptanskriterier svarar på frågan:

> Vilka specifika beteenden eller villkor behöver vara uppfyllda för just detta krav?

Båda behövs. Om Definition of Done saknas kan teamet leverera funktioner som uppfyller storyn men inte håller gemensam kvalitet. Om acceptanskriterier saknas kan teamet hålla hög teknisk kvalitet men ändå bygga fel beteende.

## Testbarhet börjar med språk

Ett krav blir inte testbart bara för att det ligger i en backlogg. Testbarhet börjar ofta med språket.

Karin letar särskilt efter ord som låter tydliga men är svåra att verifiera:

- enkel,
- användarvänlig,
- snabb,
- lämplig,
- korrekt,
- effektiv,
- tydlig,
- säker,
- flexibel,
- relevant,
- automatiskt,
- vid behov.

Orden är inte förbjudna. Problemet är att de ofta behöver förklaras.

Exempel:

> Systemet ska visa relevant information för handläggaren.

Karin frågar:

- Vilken information?
- Relevant för vilken situation?
- Ska informationen alltid visas eller bara vid vissa ärendestatusar?
- Vem avgör vad som är relevant?
- Finns det information som inte får visas?
- Hur ser vi att visningen är korrekt?

Efter kravdialog kan formuleringen bli:

> När handläggaren öppnar ett ärende med status “Komplettering mottagen” ska systemet visa datum för mottagen komplettering, avsändare, filnamn och om filen ännu inte är granskad.

Det är inte nödvändigtvis slutlig text, men den är betydligt mer testbar. Den säger när beteendet gäller, vem som berörs, vilken status som är relevant och vilken information som ska visas.

## Exempelbaserade acceptanskriterier

Ett sätt att skapa testbarhet är att arbeta med konkreta exempel. Karin använder ofta exempel när verksamheten har svårt att formulera regler abstrakt.

I stället för att börja med frågan:

> Vilken regel gäller för komplettering?

kan hon fråga:

> Kan vi ta tre konkreta ärenden och beskriva vad som ska hända?

Exempel 1:

- Sökanden har fått en kompletteringsbegäran.
- Sökanden laddar upp en PDF inom tidsfristen.
- Filen ska tas emot, kopplas till ärendet och visas för handläggaren.

Exempel 2:

- Sökanden försöker ladda upp en körbar fil.
- Filen ska nekas.
- Sökanden ska få ett meddelande som förklarar att filtypen inte är tillåten.

Exempel 3:

- Sökanden försöker ladda upp en komplettering efter tidsfristens slut.
- Systemet ska inte ta emot kompletteringen utan särskild hantering.
- Sökanden ska få information om vad som gäller.

När exemplen ligger på bordet kan Karin hjälpa gruppen att formulera acceptanskriterier:

- När en sökande laddar upp en tillåten fil inom tidsfristen ska filen sparas på rätt ärende.
- När en sökande försöker ladda upp en otillåten filtyp ska uppladdningen stoppas och felmeddelande visas.
- När kompletteringsfristen har passerat ska sökanden inte kunna skicka in komplettering via standardflödet.

Exemplen gör två saker. De konkretiserar vad kravet betyder och de avslöjar frågor som annars hade upptäckts senare.

## Given–When–Then som arbetsform

Karin behöver inte göra teamet beroende av en viss mall, men hon använder ibland formatet Given–When–Then eftersom det hjälper gruppen tänka i situation, händelse och förväntat resultat.

På svenska kan det beskrivas så här:

- **Givet att** ett visst tillstånd gäller,
- **när** något händer,
- **så ska** ett visst resultat uppstå.

Exempel:

> Givet att en kompletteringsbegäran är aktiv och tidsfristen inte har passerat,  
> när den sökande laddar upp en PDF-fil som är mindre än maxstorleken,  
> så ska filen sparas på ärendet och visas som mottagen komplettering.

Det här formatet hjälper särskilt när krav styrs av status, regler eller undantag. Det tvingar gruppen att säga vad som gäller före handlingen, vad användaren eller systemet gör och vilket resultat som förväntas.

Men Karin är försiktig. Given–When–Then är ett verktyg, inte ett mål. Om gruppen börjar lägga energi på att fylla i mallen korrekt men fortfarande inte förstår regeln, har formen tagit över. Då går hon tillbaka till exempel och samtal.

## Acceptanskriterier ska inte bära all dokumentation

Ett vanligt misstag i agilt kravarbete är att försöka lägga all kravinformation i acceptanskriterierna. Då blir varje backloggpost tung, svårläst och fylld av upprepning.

Karin skiljer därför på tre typer av information.

### Det som hör hemma i acceptanskriterier

Det som direkt avgör om den aktuella delen kan accepteras.

Exempel:

- filen ska sparas på rätt ärende,
- otillåtna filtyper ska stoppas,
- användaren ska få kvittens,
- handläggaren ska se att komplettering har mottagits.

### Det som hör hemma i stabilt underlag

Det som gäller över flera stories eller behöver vara spårbart över tid.

Exempel:

- tillåtna filtyper,
- maxstorlek för bilagor,
- juridisk grund för diarieföring,
- begreppsdefinitioner,
- processens huvudflöde,
- beslut om avgränsningar.

### Det som hör hemma i testunderlag

Det som beskriver exakt hur verifieringen ska göras.

Exempel:

- testdata,
- steg-för-steg-instruktioner,
- förväntade tekniska svar,
- kombinationer av filtyper, roller och statusar,
- automatiserade testskript.

När Karin håller isär dessa nivåer blir acceptanskriterierna användbara utan att bli en ny kravspecifikation i miniatyr.

## Negativa kriterier är också viktiga

Många acceptanskriterier beskriver vad som ska fungera. Men i myndighetskontext är det ofta lika viktigt att beskriva vad som inte får hända.

Exempel:

- En sökande ska inte kunna komplettera ett ärende som tillhör någon annan.
- En fil som innehåller otillåten filtyp ska inte sparas.
- En handläggare utan rätt behörighet ska inte kunna se kompletteringen.
- En komplettering ska inte kunna skickas in via standardflödet efter tidsfristens slut.

Sådana kriterier kan kännas mer tekniska eller kontrollinriktade, men de är ofta funktionella ur verksamhetens perspektiv. De skyddar rättssäkerhet, sekretess, korrekt handläggning och förtroende.

Karin markerar dem inte som “tekniska detaljer” för tidigt. Hon ställer i stället frågan:

> Vilket verksamhetsvärde eller vilken risk handlar det här om?

Om svaret är rätt åtkomst, korrekt beslut, skyddad information eller lagstyrd process, hör frågan hemma i kravdialogen.

## När acceptanskriterier blir för många

Ibland växer acceptanskriterierna snabbt. En story får tio, femton eller tjugo kriterier. Det kan betyda att kravet är komplext, men det kan också betyda att storyn är för stor.

Karin använder följande signaler:

- kriterierna beskriver flera olika användarflöden,
- kriterierna gäller flera roller,
- kriterierna blandar huvudfall, undantag och administration,
- vissa kriterier kan prioriteras bort men andra är nödvändiga,
- teamet säger att storyn är svår att uppskatta,
- testaren behöver flera separata testområden,
- produktägaren har svårt att säga vad som är minsta användbara del.

Då föreslår Karin inte bara att kriterierna ska skrivas om. Hon frågar om kravet behöver delas upp.

Exempel:

En story om “komplettera ansökan” kan delas upp i:

1. Sökande kan ladda upp tillåten fil inom aktiv kompletteringsfrist.
2. Sökande får kvittens på inskickad komplettering.
3. Handläggare kan se mottagen komplettering.
4. Otillåtna filtyper och för stora filer stoppas.
5. Komplettering efter tidsfrist hanteras enligt beslutad regel.

Varje del kan få egna acceptanskriterier. Det gör inte bara arbetet mindre. Det gör acceptansen tydligare.

## Definition of Done i kravarbete

Definition of Done ägs ofta av teamet, men Karin har mycket att bidra med. Hon kan hjälpa teamet se vilka kravrelaterade kvalitetsvillkor som behöver vara återkommande.

En enkel Definition of Done för funktionella ändringar kan innehålla:

- berörda acceptanskriterier är uppfyllda,
- relevanta testfall är genomförda eller uppdaterade,
- beslutade avgränsningar är dokumenterade,
- berörda regler eller begrepp är uppdaterade i stabilt underlag,
- påverkan på användarflöde är avstämd med produktägare,
- eventuella öppna frågor är dokumenterade och ägda,
- verksamhetsrepresentant eller produktägare har accepterat resultatet enligt överenskommen nivå.

Det betyder inte att Karin ska införa tung kontroll. Det betyder att återkommande kvalitetsfrågor inte ska behöva uppfinnas på nytt för varje story.

Särskilt i myndighetsmiljö kan Definition of Done behöva inkludera frågor som:

- är beslut eller avgränsning spårbar?
- har rätt regelkälla eller verksamhetsregel uppdaterats?
- har tillgänglighet berörts?
- påverkas information som är känslig eller sekretessbelagd?
- finns konsekvens för handläggningsprocess eller förvaltning?

Alla dessa punkter behöver inte gälla varje gång. Men teamet behöver en gemensam bild av vilka kvalitetsvillkor som normalt måste kontrolleras.

## Gemensam definition av klart är mer än en lista

Det är lätt att tro att Definition of Done bara är en checklista. Men det viktigaste är inte listan i sig. Det viktigaste är att teamet har en gemensam förståelse av vad listan betyder.

Karin märker detta när olika personer använder ordet “klart” på olika sätt:

- Utvecklaren menar att koden är färdig.
- Testaren menar att beteendet är verifierat.
- Produktägaren menar att funktionen kan visas och bedömas.
- Verksamheten menar att den fungerar i det verkliga arbetsflödet.
- Förvaltningen menar att den går att ta emot, förstå och underhålla.
- Juristen eller säkerhetsspecialisten menar att viktiga krav inte har missats.

Alla har delvis rätt. Problemet uppstår när de tror att ordet betyder samma sak för alla.

Karin använder därför frågan:

> När vi säger att den här delen är klar, vad vågar vi då göra?

Möjliga svar kan vara:

- visa den för verksamheten,
- gå vidare med nästa del,
- aktivera den för en begränsad användargrupp,
- släppa den i produktion,
- använda den som grund för beslut,
- avsluta ett ärende i verklig handläggning.

Ju större konsekvens, desto högre krav på acceptans, testbarhet och dokumentation.

## Vanliga kvalitetsnivåer för acceptans

Alla kravdelar behöver inte samma acceptansnivå. Karin hjälper gruppen att skilja mellan olika situationer.

### Utforskande acceptans

Används när teamet bygger något för att lära. Kriterierna kan fokusera på vad som ska kunna visas, prövas eller jämföras.

Exempel:

> När prototypen visas för handläggare ska de kunna genomföra huvudflödet för att lämna synpunkter på ordning och begrepp.

Detta är inte samma sak som produktionsklar funktion.

### Utvecklingsacceptans

Används när en story ska bli klar inom teamets arbete. Kriterierna fokuserar på beteende, regler och testbarhet.

Exempel:

> När en sökande skickar in en godkänd fil ska kompletteringen kopplas till rätt ärende och visas för handläggaren.

### Leveransacceptans

Används när funktionaliteten ska kunna användas skarpt eller ingå i en release. Då kan fler kvalitetsvillkor behöva vara uppfyllda.

Exempel:

- överenskomna acceptanskriterier är uppfyllda,
- relevanta regressionstester är genomförda,
- stödtexter är granskade,
- förvaltningsdokumentation är uppdaterad,
- verksamheten har accepterat förändringen enligt beslutad process.

Skillnaden mellan dessa nivåer gör det lättare att undvika två vanliga ytterligheter: att kräva produktionsklar kvalitet för allt utforskande arbete, eller att behandla en ofärdig lösning som färdig bara för att den är demonstrerbar.

## Exempel: från vagt krav till testbara kriterier

Karin får följande formulering från en workshop:

> Den sökande ska enkelt kunna komplettera sitt ärende.

Det är en rimlig ambition, men inte ett testbart krav. Karin bryter ned det med gruppen.

Först frågar hon:

- Vilken sökande?
- Vilket ärende?
- När får komplettering ske?
- Vad betyder komplettera?
- Vad betyder enkelt?
- Vilka fel behöver hanteras?
- Vad behöver handläggaren se?

Efter dialogen landar gruppen i en mer konkret story:

> Som sökande med en aktiv kompletteringsbegäran vill jag kunna ladda upp en kompletterande handling så att mitt ärende kan fortsätta handläggas.

Sedan formulerar de acceptanskriterier:

1. Givet att den sökande har en aktiv kompletteringsbegäran, när den sökande laddar upp en tillåten fil inom tidsfristen, så ska filen sparas på rätt ärende.
2. Givet att filen har sparats, när uppladdningen är klar, så ska den sökande få en kvittens som visar att kompletteringen har tagits emot.
3. Givet att filtypen inte är tillåten, när den sökande försöker ladda upp filen, så ska uppladdningen stoppas och ett begripligt felmeddelande visas.
4. Givet att kompletteringsfristen har passerat, när den sökande försöker ladda upp en fil, så ska standardflödet inte ta emot kompletteringen.
5. Givet att kompletteringen har tagits emot, när handläggaren öppnar ärendet, så ska det framgå att ny komplettering finns att granska.

Nu går det att diskutera om detta är en story eller flera. Det går också att se vilka regler som bör ligga i stabilt underlag:

- vad en aktiv kompletteringsbegäran är,
- vilka filtyper som är tillåtna,
- hur tidsfrist beräknas,
- vilken kvittensinformation som behöver sparas,
- vilken roll som får se kompletteringen.

Acceptanskriterierna gör alltså mer än att förbereda test. De hjälper gruppen upptäcka struktur.

## Acceptanskriterier och produktägarens beslut

Produktägaren behöver ofta fatta prioriteringsbeslut innan allt är känt. Acceptanskriterier hjälper genom att göra omfattningen synlig.

Utan kriterier kan en story se liten ut:

> Sökande kan ladda upp komplettering.

Med kriterier blir omfattningen tydligare:

- filuppladdning,
- validering av filtyp,
- validering av storlek,
- koppling till ärende,
- kvittens,
- visning för handläggare,
- tidsfrist,
- behörighet,
- felmeddelanden,
- diarieföring.

Det betyder inte att allt måste ingå i första versionen. Tvärtom gör acceptanskriterierna det möjligt att fatta bättre beslut om vad som ska ingå.

Karin kan fråga produktägaren:

- Vilka kriterier är nödvändiga för första användbara del?
- Vilka kriterier är säkerhets- eller regelstyrda och kan inte prioriteras bort?
- Vilka kriterier kan vänta utan att skapa oacceptabel risk?
- Vilka kriterier hör egentligen till en annan story?
- Vilka kriterier behöver utredas innan beslut?

På så sätt blir acceptanskriterierna ett stöd för prioritering, inte bara för test.

## Acceptanskriterier och testares tidiga roll

I traditionellt arbete kommer test ibland in sent. I agilt kravarbete bör testperspektivet komma in tidigt, helst redan när kravet formuleras.

Testaren kan hjälpa Karin och teamet att se:

- om kravet går att verifiera,
- vilka data som behövs,
- vilka undantag som saknas,
- vilka kombinationer som kan skapa risk,
- om kriterierna är för vaga,
- om kriterierna beskriver flera olika beteenden,
- om test kan automatiseras eller behöver vara manuellt,
- om det finns beroenden till andra system eller processer.

Karin behöver inte själv vara testexpert. Men hon behöver förstå att testbarhet är en del av kravkvalitet. Ett krav som inte går att verifiera är ofta inte tillräckligt förstått.

## När acceptanskriterier låser lösningen för tidigt

Det finns också en risk åt andra hållet. Acceptanskriterier kan bli så detaljerade att de styr lösningsdesign i onödan.

Exempel:

> Knappen “Ladda upp komplettering” ska vara blå, ligga längst upp till höger och öppna en modalruta med tre fält.

Det kan vara relevant om designen är beslutad och viktig. Men ofta blandar formuleringen ihop önskat beteende med lösningsdetaljer.

Karin frågar då:

- Är placeringen ett krav eller ett designförslag?
- Är modalrutan nödvändig eller ett möjligt sätt att lösa behovet?
- Vilket beteende behöver uppfyllas oavsett gränssnitt?
- Finns tillgänglighets- eller användbarhetsskäl som gör designen viktig?

En mer beteendefokuserad formulering kan vara:

> Den sökande ska kunna starta uppladdning från kompletteringssidan och förstå vilka handlingar som kan bifogas innan filen skickas in.

Det lämnar mer lösningsutrymme, men behåller det viktiga beteendet.

## Checklista: är acceptanskriteriet användbart?

Karin använder en enkel kontroll innan hon betraktar ett acceptanskriterium som redo nog.

Fråga:

1. Går kriteriet att observera?
2. Går det att verifiera genom test, granskning eller demonstration?
3. Är det tydligt vilken situation kriteriet gäller?
4. Är aktör, händelse och förväntat resultat begripliga?
5. Beskriver kriteriet beteende eller regel snarare än intern lösning, om inte lösningen faktiskt är beslutad?
6. Är kriteriet avgränsat till den aktuella storyn eller funktionen?
7. Finns viktiga negativa fall eller undantag med?
8. Finns information som borde flyttas till stabilt underlag?
9. Finns detaljer som hör hemma i testfall snarare än acceptanskriterium?
10. Förstår både verksamhet och team vad kriteriet betyder?

Alla kriterier behöver inte vara perfekta, men om flera frågor får svaret nej är kravet troligen inte redo nog.

## Vanliga misstag

### Misstag: Acceptanskriterier skrivs som önskelista

Exempel:

> Funktionen ska vara enkel, snabb, smidig och tydlig.

**Varför det händer:** Gruppen försöker uttrycka en legitim ambition men har ännu inte konkretiserat vad den betyder i användning.

**Hur man undviker det:** Be om exempel. Fråga vad användaren ska kunna göra, vad systemet ska visa, vad som inte får hända och hur teamet kan se att beteendet är uppnått.

### Misstag: Acceptanskriterier blir testfall med för mycket detalj

**Varför det händer:** Teamet vill vara noggrant och börjar skriva steg-för-steg-instruktioner direkt i storyn.

**Hur man undviker det:** Håll acceptanskriterierna på villkorsnivå. Lägg exakta teststeg i testunderlag när det behövs.

### Misstag: All regelinformation upprepas i varje story

**Varför det händer:** Gruppen saknar stabil plats för regler, begrepp och beslut.

**Hur man undviker det:** Dokumentera återkommande regler i stabilt underlag och länka från relevanta stories.

### Misstag: Definition of Done används som ersättning för acceptanskriterier

**Varför det händer:** Teamet har en generell kvalitetslista och tror att den räcker.

**Hur man undviker det:** Skilj på generella kvalitetsvillkor och specifika beteenden för den aktuella funktionen.

### Misstag: Kriterierna skrivs utan test- eller verksamhetsperspektiv

**Varför det händer:** Kraven förbereds av en person och skickas vidare utan gemensam genomgång.

**Hur man undviker det:** Ta in testare, produktägare och relevant verksamhet tidigt i refinement eller kravdialog.

## Övningar

### Övning 1: Gör ett vagt krav testbart

Utgå från formuleringen:

> Handläggaren ska enkelt kunna se relevanta kompletteringar.

Skriv om den till:

- en tydligare kravformulering,
- minst fyra acceptanskriterier,
- minst ett negativt kriterium,
- två frågor som behöver besvaras innan kravet är redo nog.

### Övning 2: Skilj mellan nivåerna

Placera följande på rätt nivå: kravformulering, acceptanskriterium, testfall eller Definition of Done.

1. “När sökanden laddar upp en PDF inom tidsfristen ska filen sparas på rätt ärende.”
2. “Logga in som sökande, öppna ärende 123 och ladda upp filen test.pdf.”
3. “Som sökande vill jag kunna skicka in kompletterande handlingar digitalt.”
4. “Relevanta tester är genomförda och dokumentation är uppdaterad.”
5. “Otillåtna filtyper ska stoppas.”
6. “Koden är granskad enligt teamets överenskommelse.”

### Övning 3: Hitta vad som ska flyttas

Läs acceptanskriteriet:

> Givet att sökanden är inloggad med e-legitimation, har ett ärende med status KOMPL_BEGÄRD, har fått kompletteringsbegäran enligt mall M-14, laddar upp en PDF, DOCX eller JPG under 20 MB, inom 14 kalenderdagar från beslutsdatum, och handläggaren tillhör rätt organisatorisk enhet, så ska filen sparas, diarieföras, visas för handläggaren, ge kvittens och markera ärendet som komplettering mottagen.

Identifiera:

- vad som är acceptanskriterium,
- vad som borde vara stabil regelinformation,
- vad som borde vara testfall,
- om storyn bör delas upp.

### Fördjupning

Välj en aktuell backloggpost eller ett kravområde. Samla produktägare, testare och en verksamhetsrepresentant. Gå igenom följande frågor:

- Vad betyder “klart” för den här delen?
- Vilka beteenden måste kunna demonstreras?
- Vilka regler får inte brytas?
- Vilka negativa fall behöver hanteras?
- Vilka kriterier är nödvändiga nu?
- Vilka kriterier kan vänta?
- Vilken information ska dokumenteras utanför storyn?

Dokumentera resultatet som en kort kravdialog och jämför med hur kravet såg ut innan.

## Snabb sammanfattning

- Acceptanskriterier beskriver villkor för att ett krav eller en story ska kunna accepteras.
- Testbarhet börjar ofta med språket: vaga ord behöver konkretiseras.
- Acceptanskriterier, testfall och Definition of Done fyller olika funktioner.
- Exempel hjälper gruppen upptäcka regler, undantag och missförstånd.
- Negativa kriterier är särskilt viktiga i myndighetskontext.
- För många kriterier kan vara en signal om att storyn behöver delas upp.
- Definition of Done skapar gemensamma kvalitetsvillkor, men ersätter inte specifika acceptanskriterier.
- En gemensam definition av klart handlar ytterst om vad teamet, produktägaren och verksamheten vågar göra när arbetet är färdigt.

## Quiz/reflektionsfrågor

1. Vad är skillnaden mellan ett acceptanskriterium och ett testfall?
2. Varför är ord som “enkelt”, “snabbt” och “relevant” ofta problematiska i krav?
3. När bör ett negativt acceptanskriterium skrivas?
4. Vad kan det betyda om en story får väldigt många acceptanskriterier?
5. Hur kan Definition of Done hjälpa kravarbete utan att bli tung kontroll?
6. Vilka personer bör vara med när acceptanskriterier formuleras för en verksamhetskritisk funktion?
7. Hur kan Karin avgöra om ett kriterium beskriver beteende eller låser lösningsdesign för tidigt?

## Nästa steg

I nästa kapitel går vi vidare till regler, undantag och verksamhetslogik. Acceptanskriterier gör funktionella krav testbara, men många myndighetskrav styrs av mer komplexa regelverk än en enskild story kan bära. Då behöver Karin kunna dokumentera regler och undantag på ett sätt som både team, verksamhet, test och förvaltning kan använda.
