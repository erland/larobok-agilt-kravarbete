# Kapitel 4: När behovsbilden är osäker

## Varför detta kapitel finns

I ett fasbaserat kravarbete finns ofta en stark förväntan på att behovsbilden ska klarläggas tidigt. Först ska verksamheten beskriva vad den behöver. Sedan ska kraven analyseras, dokumenteras, granskas och beslutas. Därefter kan lösningen byggas.

Det arbetssättet kan fungera när problemet är välkänt, intressenterna är överens och lösningsutrymmet är relativt stabilt. Men många moderna utvecklingsinitiativ börjar inte där. De börjar i något mer oklart:

- användare uttrycker problem, men inte alltid verkliga behov,
- verksamhetsrepresentanter beskriver olika bilder av samma process,
- regelverk tolkas olika,
- ledningen vill ha effekt, men effekten är inte konkretiserad,
- produktägaren behöver prioritera, men underlaget är ofullständigt,
- teamet vill börja bygga, men ingen vet ännu vad som är viktigast att lära sig först.

I en sådan situation är kravanalytikerns uppgift inte att snabbt förvandla osäkerheten till skenbart säkra krav. Uppgiften är att hjälpa organisationen att skilja mellan det som är känt, det som är antaget, det som är beslutat och det som behöver utforskas.

Det här kapitlet handlar om kravarbete när behovsbilden är osäker. Du får arbeta med tre huvudbegrepp:

- **behovshypotes**,
- **effektmål**,
- **antagande**.

Målet är att du ska kunna skapa struktur utan att låsa för tidigt.

## Lärandemål

Efter kapitlet ska du kunna:

- skilja mellan uttryckta önskemål, bakomliggande behov, antaganden och beslut,
- formulera behovshypoteser som kan prövas stegvis,
- använda effektmål för att hålla kravdialogen nära verksamhetsnytta,
- identifiera när ett krav egentligen bygger på ett osäkert antagande,
- dokumentera osäkerhet på ett sätt som hjälper produktägare och team att ta nästa steg,
- planera kravarbete där syftet är att minska osäkerhet snarare än att producera färdiga krav.

## Innan vi börjar

I kapitel 1 såg vi att agilt kravarbete kräver **tillräckligt kravunderlag** för nästa steg, inte fullständig kravsäkring för hela resan.

I kapitel 2 såg vi att kravanalytikerns roll blir mer faciliterande. Karin ska inte bara skriva ned vad någon säger. Hon ska hjälpa andra att förstå vad som är viktigt, oklart, motsägelsefullt eller ännu inte beslutat.

I kapitel 3 introducerades **levande kravunderlag**. Där skiljde vi mellan stabilt underlag, arbetsnära underlag och utforskande underlag. Det här kapitlet fördjupar just det utforskande underlaget: hur vi arbetar när vi ännu inte vet tillräckligt.

## Situationen: tre intressenter, tre behovsbilder

Karin deltar i en workshop om den nya digitala tjänsten för ansökningar. Målet är att minska manuell hantering och ge sökande bättre insyn i sina ärenden.

Efter trettio minuter har hon fått tre tydliga men olika bilder.

En handläggare säger:

> “Det viktigaste är att ansökan innehåller all information från början. Annars får vi lägga massor av tid på kompletteringar.”

En chef säger:

> “Det viktigaste är att medborgaren får snabbare besked. Vi måste korta ledtiderna.”

En jurist säger:

> “Det viktigaste är att vi inte förenklar bort rättssäkerheten. Vissa uppgifter måste prövas manuellt.”

Alla tre har rätt utifrån sitt perspektiv. Men om Karin omedelbart skriver krav av uttalandena riskerar hon att skapa en kravbild som ser tydlig ut men egentligen döljer målkonflikter.

Hon skulle kunna skriva:

- Systemet ska säkerställa att ansökan är komplett.
- Systemet ska ge snabbare besked.
- Systemet ska stödja rättssäker manuell prövning.

Det är inte fel som första observationer. Men det är inte tillräckligt. Kraven blandar önskade effekter, lösningsidéer och kvalitetsförväntningar. De säger inte vilka situationer som är viktigast, vilka användare som påverkas, vad som går att automatisera, vad som måste prövas manuellt eller hur organisationen ska avgöra om arbetet lyckas.

Karin stannar upp och säger:

> “Jag tror att vi har flera viktiga perspektiv här. Innan vi formulerar krav behöver vi skilja på vad vi vet, vad vi antar och vad vi behöver ta beslut om.”

Det är ett avgörande ögonblick i agilt kravarbete.

## Osäkerhet är inte ett problem att dölja

I många organisationer finns en outtalad förväntan på att kravarbete ska skapa säkerhet. När kravdokumentet är klart ska projektet kunna gå vidare. När kraven är godkända ska det vara tydligt vad som ska byggas. När omfattningen är beslutad ska osäkerheten minska.

Det är förståeligt. Beslut kräver underlag. Budget kräver avgränsning. Myndighetsarbete kräver ansvar.

Men i komplex utveckling försvinner inte osäkerhet bara för att den skrivs som krav. Om en formulering bygger på ett antagande är den fortfarande osäker, även om den får ett krav-ID.

Ett exempel:

> “Användaren ska kunna skicka in en komplett ansökan utan stöd från handläggare.”

Det kan se ut som ett tydligt funktionellt krav. Men bakom formuleringen kan det finnas flera antaganden:

- att sökande förstår vilka uppgifter som behövs,
- att regelverket kan översättas till begripliga frågor,
- att kompletteringar kan undvikas med bättre formulärstöd,
- att alla målgrupper har liknande digital förmåga,
- att ärendetyperna är tillräckligt lika för ett gemensamt flöde.

Om dessa antaganden inte synliggörs kan teamet bygga fel sak på ett effektivt sätt. Det är en av de vanligaste riskerna när fasbaserat kravarbete förs in i en agil miljö: tidiga antaganden får för hög status.

I agilt kravarbete är osäkerhet inte ett tecken på dåligt kravarbete. Den är ofta en naturlig del av problemet. Det professionella är att göra osäkerheten synlig, hanterbar och möjlig att lära från.

## Från önskemål till behov

Ett uttryckt önskemål är inte alltid samma sak som ett behov.

En användare kan säga:

> “Vi behöver en knapp för att pausa ärendet.”

Det kan vara ett verkligt behov, men det kan också vara en lösningsidé. Bakom önskemålet kan det finnas flera möjliga behov:

- handläggaren behöver kunna vänta in kompletterande information,
- systemet behöver skilja aktiv handläggningstid från väntetid,
- ledtidsmätningen behöver bli mer rättvis,
- ärendet får inte gå vidare till fel beslutsläge,
- medborgaren behöver förstå varför ärendet inte rör sig framåt.

Om Karin skriver “systemet ska ha en pausknapp” för tidigt riskerar hon att låsa lösningen. Om hon i stället undersöker behovet kan teamet hitta en bättre funktion, till exempel statusar, väntorsaker, automatiska påminnelser eller tydligare kommunikation till den sökande.

Ett användbart arbetssätt är att pröva tre frågor:

1. Vad försöker personen uppnå?
2. Vad hindrar personen i dag?
3. Vad skulle bli bättre om behovet löstes?

Det betyder inte att alla önskemål ska ifrågasättas i oändlighet. Ibland är önskemålet både rimligt och konkret. Men när behovsbilden är osäker bör kravanalytikern vara försiktig med att behandla första lösningsförslaget som krav.

## Behovshypotes: ett kravunderlag som erkänner osäkerhet

En **behovshypotes** är en tydlig formulering av vad vi tror att en målgrupp behöver och varför vi tror att det är viktigt.

Den är inte ett färdigt krav. Den är ett strukturerat antagande som kan undersökas, förtydligas eller omprövas.

En enkel mall kan vara:

> Vi tror att [målgrupp] behöver [förmåga/stöd] för att [önskad effekt].  
> Vi behöver ta reda på [osäkerhet] innan vi formulerar mer detaljerade krav.

Exempel:

> Vi tror att sökande behöver bättre stöd för att förstå vilka bilagor som krävs för att minska kompletteringar och korta handläggningstiden.  
> Vi behöver ta reda på vilka kompletteringar som är vanligast och om de beror på otydliga frågor, svåra regler eller bristande information.

Det här är mer användbart än att direkt skriva:

> Systemet ska visa obligatoriska bilagor.

Det senare kan mycket väl bli ett krav senare. Men hypotesen hjälper teamet att först förstå problemet. Den öppnar för analys: statistik, intervjuer, observationer, test av formulärtexter, genomgång av regler och dialog med handläggare.

Karin använder behovshypoteser när hon märker att organisationen vill gå direkt från oro till kravrad. Hon säger inte “vi vet inte, så vi kan inte gå vidare”. Hon säger:

> “Vi vet tillräckligt för att formulera vad vi behöver lära oss härnäst.”

Det är en viktig skillnad.

## Effektmål håller kravdialogen nära nyttan

Ett **effektmål** beskriver vilken förändring verksamheten vill uppnå. Det ska inte bara säga vad som ska byggas, utan vilken nytta eller vilket resultat förändringen ska leda till.

Exempel på svaga mål:

- Digitalisera ansökningsprocessen.
- Införa självservice.
- Bygga ett nytt ärendeflöde.
- Skapa en modern användarupplevelse.

De kan vara sanna, men de är inte särskilt styrande. De säger inte vilken effekt som är viktigast.

Mer användbara effektmål kan vara:

- Minska andelen ansökningar som kräver komplettering.
- Korta tiden från inkommen ansökan till första återkoppling.
- Minska manuell registrering av uppgifter som redan lämnats digitalt.
- Öka andelen sökande som förstår ärendets status utan att kontakta myndigheten.
- Minska variationen i hur likartade ärenden handläggs.

Effektmål hjälper kravanalytikern att prioritera frågor. Om målet är att minska kompletteringar behöver Karin förstå vad kompletteringarna beror på. Om målet är att öka insyn behöver hon förstå vilka statusar och händelser som är meningsfulla för sökande. Om målet är rättssäkerhet behöver hon förstå var manuella bedömningar behövs och hur de ska stödjas.

Ett effektmål gör inte behovsbilden säker. Men det ger riktning när allt inte är känt.

## Antaganden behöver märkas upp

Ett **antagande** är något vi tror är sant men ännu inte har tillräckligt stöd för.

Antaganden är inte farliga i sig. Utveckling kräver ofta antaganden. Problemet uppstår när antaganden dokumenteras som om de vore fakta eller beslut.

Karin börjar därför märka upp osäkra delar i kravunderlaget. Hon använder enkla etiketter:

| Typ av information | Exempel | Hur den bör hanteras |
|---|---|---|
| Fakta | “Förra året krävde 38 procent av ansökningarna komplettering.” | Kan användas som stabilt underlag, om källan är tydlig. |
| Antagande | “Kompletteringar beror främst på otydliga formulärfrågor.” | Behöver prövas innan stora lösningsbeslut tas. |
| Beslut | “Första versionen ska fokusera på två vanligaste ärendetyperna.” | Ska dokumenteras i beslutslogg. |
| Öppen fråga | “Vilka uppgifter får förifyllas enligt gällande regler?” | Behöver ägare och nästa steg. |
| Kravkandidat | “Sökande ska kunna se vilka bilagor som krävs för vald ärendetyp.” | Kan förädlas till backloggpost och acceptanskriterier. |

Den här sorteringen minskar risken att oklara resonemang smyger in i backloggen som färdiga krav. Den gör också kravunderlaget mer användbart för produktägare och team.

Produktägaren kan prioritera vad som behöver utredas. Teamet kan se vilka krav som är redo nog för nästa steg. Juristen kan se vilka frågor som behöver tolkning. Testaren kan se var acceptansen ännu är oklar.

## Att dokumentera osäkerhet utan att skapa otrygghet

En vanlig invändning mot att synliggöra osäkerhet är:

> “Om vi skriver att detta är osäkert, kommer styrgruppen tro att vi inte har kontroll.”

Det kan hända om osäkerheten presenteras slarvigt. Men väl dokumenterad osäkerhet skapar ofta mer förtroende än falsk precision.

Skillnaden ligger i hur den formuleras.

Mindre hjälpsamt:

> “Vi vet inte hur ansökningsflödet ska fungera.”

Mer hjälpsamt:

> “Tre delar av ansökningsflödet är ännu osäkra: vilka bilagor som krävs per ärendetyp, vilka uppgifter som får förifyllas och vilka kompletteringsorsaker som är vanligast. Dessa utreds genom regelgenomgång, statistik och två användarintervjuer innan teamet bryter ned första utvecklingsbara flödet.”

Den andra formuleringen visar kontroll. Den säger vad som är osäkert, varför det spelar roll och hur osäkerheten ska minskas.

Karin använder ofta fyra rubriker i sitt utforskande underlag:

1. Vad vet vi?
2. Vad tror vi?
3. Vad behöver beslutas?
4. Vad behöver vi lära oss först?

Det är enkla rubriker, men de förändrar samtalet. De hjälper gruppen att sluta låtsas att allt är lika säkert.

## När är ett behov redo att bli krav?

Ett behov behöver inte vara fullständigt utrett för att kunna bli kravunderlag. Men det behöver vara tillräckligt tydligt för den typ av beslut eller utveckling som ska göras.

Karin använder följande kontrollfrågor:

- Vet vi vilken målgrupp eller roll behovet gäller?
- Förstår vi vilket problem eller vilken effekt behovet kopplar till?
- Vet vi om behovet gäller alla fall eller vissa situationer?
- Finns det regler, begränsningar eller beroenden som påverkar lösningen?
- Har vi skiljt mellan behov och lösningsförslag?
- Vet vi vilka antaganden som fortfarande finns?
- Är nästa steg analys, beslut, design, utveckling eller test?

Om svaret är oklart på flera frågor är behovet kanske inte redo att brytas ned till detaljerade funktionella krav. Det kan däremot vara redo för en behovshypotes, ett analysuppdrag, en workshop eller en prototyp.

Det agila skiftet handlar inte om att alla behov ska vara oklara längre. Det handlar om att ge olika behov rätt mognadsgrad vid rätt tidpunkt.

## Exempel: från otydligt behov till utforskande kravunderlag

Under workshopen säger en verksamhetsrepresentant:

> “Sökande måste få bättre återkoppling. De ringer hela tiden och frågar vad som händer.”

Karin skulle kunna skriva:

> Systemet ska visa ärendestatus för sökande.

Det är en rimlig kravkandidat, men den är för tidig. I stället arbetar hon stegvis.

### Steg 1: Formulera behovshypotes

> Vi tror att sökande behöver tydligare återkoppling om ärendets status för att minska osäkerhet och onödiga kontakter med myndigheten.  
> Vi behöver ta reda på vilka statusar som är begripliga för sökande och vilka händelser myndigheten får visa.

### Steg 2: Koppla till effektmål

Möjligt effektmål:

> Minska antalet inkommande frågor om ärendestatus för de två vanligaste ärendetyperna.

### Steg 3: Identifiera antaganden

- Sökande kontaktar myndigheten främst på grund av otydlig status.
- Det finns statusinformation i handläggningssystemet som kan visas externt.
- Statusar som används internt är begripliga för sökande.
- Det är tillåtet och lämpligt att visa alla relevanta statusar.

### Steg 4: Skapa öppna frågor

- Vilka frågor om status är vanligast?
- Vilka interna statusar finns i dag?
- Vilka statusar bör inte visas för sökande?
- Vad behöver sökande kunna göra efter att ha sett status?
- Hur ska återkoppling formuleras så att den inte skapar fel förväntningar?

### Steg 5: Formulera kravkandidater

När några frågor har undersökts kan Karin börja formulera kravkandidater:

- Sökande ska kunna se att ansökan är mottagen.
- Sökande ska kunna se om myndigheten väntar på komplettering.
- Sökande ska kunna se när ett beslut har fattats.
- Sökande ska få en förklaring av vad varje visad status betyder.

Dessa är fortfarande inte fullständiga krav. De behöver acceptanskriterier, regler och prioritering. Men de bygger nu på en tydligare behovsbild.

## Vanliga misstag

### Misstag: Att skriva om alla önskemål till krav direkt

**Varför det händer:**  
Det känns effektivt. Workshopen producerar många punkter, och kravanalytikern vill visa framdrift.

**Hur man undviker det:**  
Märk upp punkter som behov, lösningsförslag, antaganden, beslut eller öppna frågor innan de blir kravkandidater.

### Misstag: Att behandla osäkerhet som brist på analys

**Varför det händer:**  
I fasbaserade miljöer kan osäkerhet uppfattas som något som borde ha lösts innan utveckling startar.

**Hur man undviker det:**  
Dokumentera osäkerheten tydligt och koppla den till nästa konkreta aktivitet: intervju, regelgenomgång, prototyp, dataanalys eller beslut.

### Misstag: Att formulera effektmål som leveranser

**Varför det händer:**  
Organisationer är vana att styra på projektleveranser: system, formulär, integrationer och funktioner.

**Hur man undviker det:**  
Fråga: “Vad ska bli bättre i verksamheten eller för användaren när detta är infört?”

### Misstag: Att skapa för många hypoteser utan prioritering

**Varför det händer:**  
När man börjar synliggöra antaganden kan listan snabbt bli lång.

**Hur man undviker det:**  
Prioritera de antaganden som påverkar stora beslut, användarnytta, risk, regeluppfyllelse eller kommande utvecklingsarbete.

### Misstag: Att låta behovsarbete bli evig analys

**Varför det händer:**  
När behovsbilden är komplex kan det kännas tryggare att analysera mer i stället för att ta nästa steg.

**Hur man undviker det:**  
Bestäm vad som behöver vara känt för nästa steg, inte för hela lösningen. Använd “redo nog” som styrande princip.

## Övningar

### Övning 1: Sortera en otydlig behovsbild

Utgå från följande workshopanteckningar:

- “Användarna måste få bättre överblick.”
- “Vi behöver färre kompletteringar.”
- “Systemet ska automatiskt kontrollera alla uppgifter.”
- “Det är viktigt att handläggaren kan stoppa felaktiga ärenden.”
- “Sökande förstår inte våra beslut.”
- “Vi tror att många ringer eftersom de inte ser status.”
- “Juridik behöver titta på vilka uppgifter vi får visa.”

Sortera varje punkt som något av följande:

- behov,
- lösningsförslag,
- antagande,
- beslut,
- öppen fråga,
- kravkandidat.

Skriv sedan om två av punkterna till behovshypoteser.

### Övning 2: Formulera effektmål

Välj ett område från din egen organisation eller från bokens scenario. Formulera tre möjliga effektmål.

Undvik formuleringar som bara beskriver en leverans, till exempel “införa ny e-tjänst”. Försök i stället beskriva vilken förbättring som ska uppstå.

Exempel på startpunkter:

- färre kompletteringar,
- kortare ledtid,
- bättre insyn,
- färre manuella steg,
- mer likvärdig handläggning.

### Övning 3: Synliggör antaganden

Ta ett krav eller kravförslag som låter tydligt. Skriv ned minst fem antaganden som kan ligga bakom det.

Fråga sedan:

- Vilket antagande är mest riskfyllt?
- Vilket antagande påverkar prioritering mest?
- Vilket antagande behöver prövas innan utveckling?
- Vilket antagande kan vänta?

### Fördjupning

Skapa en enkel mall för utforskande kravunderlag med rubrikerna:

1. Behovshypotes
2. Kopplat effektmål
3. Kända fakta
4. Antaganden
5. Öppna frågor
6. Beslut som behövs
7. Nästa läraktivitet
8. Möjliga kravkandidater

Testa mallen på ett verkligt eller fiktivt behov.

## Snabb sammanfattning

- Osäker behovsbild ska inte döljas genom att skrivas som säkra krav.
- Ett önskemål är inte alltid samma sak som ett behov.
- En behovshypotes gör det möjligt att formulera vad vi tror och vad vi behöver ta reda på.
- Effektmål hjälper kravdialogen att fokusera på nytta, inte bara leverans.
- Antaganden behöver märkas upp så att de inte misstas för fakta eller beslut.
- Professionellt agilt kravarbete handlar om att minska osäkerhet stegvis och medvetet.

## Quiz/reflektionsfrågor

1. Vad är skillnaden mellan ett uttryckt önskemål och ett bakomliggande behov?
2. Varför kan det vara riskabelt att skriva tidiga antaganden som färdiga krav?
3. Hur kan en behovshypotes hjälpa produktägare och team?
4. Vad kännetecknar ett användbart effektmål?
5. Vilka typer av antaganden brukar finnas i funktionella krav?
6. Hur kan kravanalytikern dokumentera osäkerhet utan att skapa otrygghet?
7. När är ett behov “redo nog” att bli kravunderlag för nästa steg?

## Nästa steg

När behovsbilden är osäker behöver kravanalytikern skapa struktur, inte falsk säkerhet. Nästa kapitel tar detta vidare från analys till dialog. Där fördjupar vi hur Karin går från kravinsamling till kravdialog och hur hon hjälper olika intressenter att upptäcka skillnader i begrepp, mål och förväntningar.
