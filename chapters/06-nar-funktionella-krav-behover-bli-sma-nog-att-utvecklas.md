# Kapitel 6: När funktionella krav behöver bli små nog att utvecklas

## Varför detta kapitel finns

I fasbaserat kravarbete är det vanligt att funktionella krav formuleras på en nivå som passar granskning, beslut och överlämning. Ett krav kan beskriva en hel funktion, ett helt flöde eller ett större verksamhetsbehov. Det kan vara fullt rimligt när syftet är att skapa en samlad kravbild inför nästa fas.

I agil utveckling behöver kraven ofta göra något mer.

De behöver vara tillräckligt små för att kunna förstås, prioriteras, utvecklas, testas och följas upp i kortare cykler. Samtidigt får de inte bli så små att sammanhanget försvinner. En backlogg fylld av små fraser är inte automatiskt mer agil än en stor kravspecifikation. Den kan tvärtom bli svårare att förstå om varje rad saknar mål, regler, beroenden och beslutsbakgrund.

Det här är en av de svåraste förändringarna för Karin.

Hon är van vid att skapa sammanhängande kravbeskrivningar. Hon vet att verksamhetsflöden, regelverk och användarbehov hänger ihop. När teamet ber henne “bryta ned kraven i stories” finns en risk att arbetet reduceras till att klippa isär text. Då blir kraven mindre på ytan, men inte nödvändigtvis mer användbara.

Det här kapitlet handlar om hur funktionella krav kan brytas ned utan att förlora helhet, spårbarhet eller verksamhetslogik.

Tre huvudbegrepp står i centrum:

- **kravnivå**,
- **nedbrytning**,
- **vertikal kravskiva**.

Målet är att du ska kunna hjälpa ett team gå från stora kravpaket till utvecklingsbara delar, samtidigt som du behåller kopplingen till behov, effekt, regler och användarflöde.

## Lärandemål

Efter kapitlet ska du kunna:

- förklara varför funktionella krav behöver delas upp i agilt arbete,
- skilja mellan att dela upp efter systemdel och att dela upp efter användarvärde,
- identifiera när ett krav är för stort, för oklart eller för isolerat för att utvecklas,
- bryta ned ett större funktionellt krav till mindre delar utan att tappa helheten,
- använda epics, features, user stories och acceptanskriterier på en praktisk nivå,
- hjälpa produktägare och team diskutera vad som är “redo nog” för nästa utvecklingssteg.

## Innan vi börjar

I kapitel 1 såg vi att kravlogiken förändras när arbetet går från fasbaserat till kontinuerligt. Kraven behöver inte vara färdiga för hela lösningen innan utvecklingen startar, men de behöver vara tillräckliga för nästa steg.

I kapitel 2 såg vi att kravanalytikerns ansvar förändras. Karin ska inte ensam äga alla krav, men hon har fortfarande en viktig roll i att skapa tydlighet, kvalitet och gemensam förståelse.

I kapitel 3 introducerades levande kravunderlag. Där såg vi att kravinformation kan finnas i flera artefakter, inte bara i en kravspecifikation.

I kapitel 4 arbetade Karin med osäker behovsbild. Där blev det viktigt att skilja mellan fakta, antaganden och hypoteser.

I kapitel 5 gick arbetet från kravinsamling till kravdialog. Det är i kravdialogen som många stora, vaga eller motstridiga krav blir möjliga att bearbeta.

Nu ska vi se vad som händer när kraven behöver bli små nog att utvecklas.

## Situationen: Karin har ett stort krav som alla håller med om

Karin arbetar med den digitala ansökningstjänsten hos Myndigheten för samhällstjänster. I en tidigare kravdialog har flera intressenter enats om ett viktigt behov:

> Den sökande ska kunna komplettera en inskickad ansökan digitalt när myndigheten behöver mer information.

Det låter tydligt. Alla håller med. Funktionen är viktig för medborgaren, för handläggaren och för myndighetens effektivitet.

Men när utvecklingsteamet tittar närmare på kravet dyker frågorna upp:

- Vem får begära komplettering?
- Hur vet den sökande att en komplettering behövs?
- Vilka handlingar får laddas upp?
- Kan den sökande ändra tidigare uppgifter eller bara lägga till nya?
- Vad händer om tidsfristen går ut?
- Ska handläggaren få en avisering?
- Behöver kompletteringen diarieföras?
- Hur ska behörighet och sekretess hanteras?
- Hur ser flödet ut för ombud?
- Vad måste fungera i första versionen?

Kravet är inte fel. Det är bara för stort för att utvecklas som en enda sammanhållen enhet.

Produktägaren frågar Karin:

> Kan du göra om det här till stories?

Karin märker att frågan egentligen betyder flera saker samtidigt:

- Kan kravet göras mindre?
- Kan vi prioritera delarna?
- Kan teamet förstå vad som ska byggas först?
- Kan vi testa varje del?
- Kan vi undvika att bygga allt innan vi vet vad som ger nytta?

Det är här nedbrytning blir ett analysarbete, inte bara en formateringsövning.

## Kravnivå: alla krav ska inte ligga på samma nivå

Ett vanligt problem i kravarbete är att alla krav försöker vara lika detaljerade. Då blandas mål, funktioner, regler, lösningsidéer och detaljer i samma lista.

I agilt kravarbete behöver Karin hjälpa gruppen att se att krav kan finnas på flera nivåer.

En enkel modell är:

| Nivå | Fråga | Exempel |
|---|---|---|
| Effekt eller mål | Varför gör vi detta? | Minska ledtiden för kompletteringar. |
| Förmåga eller större funktion | Vad behöver verksamheten kunna göra? | Hantera digital komplettering av ansökan. |
| Användarflöde eller delområde | Vilken del av arbetet handlar det om? | Sökande får begäran, laddar upp underlag och skickar in komplettering. |
| Utvecklingsbar del | Vad kan teamet bygga och testa i ett steg? | Sökande kan se en begäran om komplettering i e-tjänsten. |
| Detalj eller regel | Vilka villkor gäller? | Begäran ska visa sista svarsdatum och vilka uppgifter som saknas. |

Alla nivåer behövs, men de fyller olika syften.

Om allt bara dokumenteras på hög nivå blir teamet osäkert på vad som ska byggas. Om allt bara dokumenteras på låg nivå tappar organisationen varför delarna finns och hur de hänger ihop.

Karin behöver därför inte välja mellan helhet och detalj. Hon behöver hjälpa teamet att koppla ihop nivåerna.

## Nedbrytning är att skapa utvecklingsbara beslutspunkter

Att bryta ned krav betyder inte bara att göra dem kortare.

Ett stort krav kan delas upp på många sätt. Vissa sätt gör arbetet lättare att prioritera och testa. Andra sätt skapar beroenden och väntan.

Tänk på kravet:

> Den sökande ska kunna komplettera en inskickad ansökan digitalt.

Ett tekniskt eller systemorienterat sätt att dela upp det kan bli:

1. Skapa databastabell för kompletteringar.
2. Bygga API för uppladdning.
3. Skapa användargränssnitt.
4. Skapa avisering.
5. Skapa handläggarvy.

Den sortens uppdelning kan vara användbar internt i teamet, men den säger inte mycket om vilket användarvärde som levereras först. Den gör det också svårt för produktägaren och verksamheten att prioritera. Alla delar verkar behövas innan någon kan använda funktionen.

Ett mer kravanalytiskt sätt att dela upp kan vara:

1. Sökande kan se att en komplettering begärts.
2. Sökande kan läsa vad som saknas och vilket datum som gäller.
3. Sökande kan ladda upp en efterfrågad handling.
4. Sökande kan skicka in kompletteringen.
5. Handläggare kan se att komplettering kommit in.
6. Handläggare kan markera kompletteringen som mottagen.
7. Systemet kan hantera att tidsfristen passerats.

Den andra uppdelningen är inte perfekt, men den gör det lättare att prata om nytta, ordning, risk och testbarhet.

Nedbrytning handlar alltså om att skapa utvecklingsbara beslutspunkter:

- Vad behöver vi lära oss först?
- Vilken del ger tidig nytta?
- Vilken del minskar störst risk?
- Vilken del kan testas tillsammans med verksamheten?
- Vilken del behöver vara på plats innan nästa del är meningsfull?

## Vertikal kravskiva: en liten del som går genom flödet

Ett viktigt begrepp är **vertikal kravskiva**.

En vertikal kravskiva är en avgränsad del av funktionaliteten som går genom flera lager av användning, verksamhetslogik och teknik, så att den kan ge ett faktiskt resultat. Den är inte bara en teknisk komponent.

En horisontell uppdelning kan vara:

- först databas,
- sedan integration,
- sedan gränssnitt,
- sedan test,
- sedan verksamhetsgranskning.

En vertikal uppdelning försöker i stället skapa en tunn men fungerande del:

- sökande ser en enkel kompletteringsbegäran,
- begäran hämtas från rätt ärende,
- grundläggande behörighet gäller,
- handläggare kan se att begäran visas,
- flödet kan testas med ett verklighetsnära exempel.

Det betyder inte att allt är färdigt. Men det betyder att teamet kan lära sig något om hela kedjan.

För Karin är detta viktigt. Hon vet att många kravproblem inte syns förrän flera perspektiv möts:

- användarens förståelse,
- handläggarens behov,
- regelns formulering,
- systemets beteende,
- testbarheten,
- spårbarheten.

En vertikal kravskiva hjälper teamet att upptäcka sådana problem tidigare.

## Från epic till utvecklingsbar story

Begreppen **epic**, **feature** och **user story** används olika i olika organisationer. Boken använder dem praktiskt, inte som en strikt metodstandard.

En möjlig förenklad användning är:

| Begrepp | Praktisk betydelse i boken | Exempel |
|---|---|---|
| Epic | Ett större behov eller område som är för stort för ett team att utveckla i ett steg. | Digital komplettering av ansökan. |
| Feature | En tydlig funktionell förmåga inom området. | Sökande kan skicka in komplettering digitalt. |
| User story | En mindre utvecklingsbar del uttryckt ur användar- eller aktörsperspektiv. | Som sökande vill jag se vilka uppgifter som saknas så att jag kan komplettera rätt. |
| Acceptanskriterier | Villkor som hjälper teamet förstå när storyn är tillräckligt uppfylld. | Begäran visar saknade uppgifter, sista svarsdatum och kontaktväg. |

Karin behöver inte fastna i rätt etikett. Det viktiga är att varje nivå fyller sitt syfte.

Ett exempel:

**Epic:**  
Digital komplettering av ansökan.

**Feature:**  
Sökande kan ta emot och besvara en kompletteringsbegäran i e-tjänsten.

**User story:**  
Som sökande vill jag se vad myndigheten behöver kompletterat så att jag kan skicka in rätt underlag utan att ringa handläggaren.

**Möjliga acceptanskriterier:**

- Kompletteringsbegäran visar vilka uppgifter eller handlingar som saknas.
- Begäran visar sista dag för svar.
- Begäran visar hur den sökande kan kontakta myndigheten vid frågor.
- Om ärendet inte kräver komplettering visas ingen kompletteringsuppgift.
- Texten ska kunna förstås av en sökande utan intern myndighetsterminologi.

Det här är fortfarande inte hela lösningen. Men det är en del som går att diskutera, utveckla, testa och förbättra.

## Vanlig fallgrop: att göra user stories av systemuppgifter

När en organisation börjar arbeta agilt uppstår ofta en märklig sorts backloggposter:

> Som system vill jag spara kompletteringsstatus så att databasen är uppdaterad.

Den typen av formulering kan ibland peka på ett tekniskt behov, men den hjälper sällan verksamheten förstå användarvärdet. Den kan också skapa en falsk känsla av att kravet är användarorienterat bara för att det följer en mall.

Karin behöver kunna skilja mellan tre saker:

1. **Användarbehov**: vad en aktör behöver kunna göra eller förstå.
2. **Verksamhetsregel**: vilket villkor eller beslut som styr beteendet.
3. **Teknisk uppgift**: vad teamet behöver göra i lösningen.

Alla tre kan behöva finnas, men de ska inte blandas ihop.

Exempel:

| Typ | Formulering |
|---|---|
| Användarbehov | Som sökande vill jag se vad jag behöver komplettera så att jag kan svara korrekt. |
| Verksamhetsregel | En komplettering ska ha ett sista svarsdatum. |
| Teknisk uppgift | Systemet behöver lagra status för kompletteringsbegäran. |

En bra backlogg kan innehålla flera typer av arbete. Men när funktionella krav analyseras bör Karin hjälpa gruppen att förstå vilken typ av information de tittar på.

## Hur Karin bryter ned ett stort krav

Karin samlar produktägaren, en handläggare, en testare, en utvecklare och en representant från juridik. De arbetar med det stora kravet om digital komplettering.

Hon börjar inte med att fråga:

> Vilka stories ska vi skriva?

Hon börjar med:

> Vilka situationer behöver funktionen stödja?

Gruppen identifierar först några situationer:

- sökande får en begäran om komplettering,
- sökande förstår vad som saknas,
- sökande laddar upp handling,
- sökande skickar in komplettering,
- handläggare ser att komplettering kommit in,
- handläggare bedömer kompletteringen,
- tidsfrist passerar utan svar,
- fel handling skickas in,
- ombud svarar åt sökande.

Sedan frågar Karin:

> Vilken av dessa situationer behöver vi kunna hantera först för att få ett meningsfullt lärande?

Produktägaren väljer att börja med ett smalt normalfall:

> En sökande utan ombud ska kunna se en kompletteringsbegäran och ladda upp en efterfrågad handling innan tidsfristen.

Det är fortfarande flera delar, men det är mycket tydligare än det ursprungliga kravet.

Karin hjälper gruppen att dela upp normalfallet i möjliga stories:

1. Som sökande vill jag se att myndigheten begär komplettering så att jag förstår att jag behöver agera.
2. Som sökande vill jag läsa vilka uppgifter eller handlingar som saknas så att jag kan komplettera rätt.
3. Som sökande vill jag ladda upp en efterfrågad handling så att jag kan skicka in min komplettering digitalt.
4. Som sökande vill jag få bekräftelse på att kompletteringen tagits emot så att jag vet att jag har gjort det jag ska.
5. Som handläggare vill jag se att en komplettering kommit in så att jag kan fortsätta handläggningen.

Sedan markerar hon vad som inte ingår i första skivan:

- ombud,
- flera samtidiga kompletteringsbegäranden,
- byte av tidigare inskickade uppgifter,
- komplettering efter passerad tidsfrist,
- felaktigt filformat,
- sekretessmarkerade ärenden,
- automatisk påminnelse.

Det här är inte bortglömda krav. De är medvetet avgränsade.

## “Redo nog” i stället för färdigt för alltid

I fasbaserat arbete kan kravet behöva vara färdiggranskat innan nästa steg. I agilt arbete behöver en backloggpost ofta vara **redo nog** för att teamet ska kunna börja arbeta med den.

Redo nog betyder inte slarvigt. Det betyder att underlaget är tillräckligt tydligt för nästa utvecklingssteg, med kända osäkerheter synliga.

För en funktionell backloggpost kan “redo nog” innebära att:

- syftet är begripligt,
- aktören är tydlig,
- önskat beteende är beskrivet,
- viktigaste regler och avgränsningar är kända,
- acceptanskriterier finns på rätt nivå,
- beroenden och öppna frågor är synliga,
- teamet kan uppskatta arbetet tillräckligt,
- produktägaren kan prioritera posten,
- testaren kan se hur beteendet kan verifieras.

Karin kan använda en enkel fråga:

> Vad behöver vara sant för att teamet ska kunna börja utan att gissa på egen hand?

Det är en bättre fråga än:

> Är kravet helt färdigt?

## När kravet är för stort

Ett krav är ofta för stort om:

- teamet inte kan förklara vad som ingår och inte ingår,
- flera olika användarsituationer blandas,
- många aktörer påverkas samtidigt,
- flera regelområden behöver lösas på en gång,
- testaren inte kan beskriva konkreta testfall,
- produktägaren inte kan prioritera delar av kravet separat,
- teamet inte kan leverera något meningsfullt förrän “allt” är klart,
- diskussionen hela tiden glider mellan mål, regel, design och teknik.

När Karin ser detta bör hon inte bara säga “det här är för stort”. Hon bör hjälpa gruppen hitta en nedbrytningsprincip.

Möjliga nedbrytningsprinciper är:

| Nedbrytning efter | Fråga | Exempel |
|---|---|---|
| Användarsituation | Vilken situation ska stödjas först? | Sökande utan ombud kompletterar en handling. |
| Aktör | Vems arbete fokuserar vi på? | Sökande först, handläggare sedan. |
| Regelvariant | Vilken regel är vanligast eller viktigast? | Komplettering före tidsfrist. |
| Normalfall och undantag | Vad är enklaste men meningsfulla flödet? | Normalfall först, fel filformat senare. |
| Risk | Vad behöver vi lära oss tidigt? | Uppladdning och mottagningsbekräftelse. |
| Effekt | Vilken del ger mätbar nytta först? | Minska telefonsamtal om vad som saknas. |

## När kravet blir för litet

Det motsatta problemet är att kravet bryts ned för långt.

En backloggpost kan bli för liten om den inte längre går att förstå som funktionellt beteende. Exempel:

- “Lägg till knapp”
- “Skapa fält för datum”
- “Visa text”
- “Spara flagga”
- “Uppdatera status”

Sådana uppgifter kan vara nödvändiga i teamets interna arbete, men de är ofta för små för att fungera som funktionella krav. De saknar aktör, syfte och verifierbart beteende.

Karin behöver då hjälpa teamet att koppla tillbaka uppgiften till en meningsfull kravdel:

> Vilket användar- eller verksamhetsbeteende blir möjligt när knappen finns?

Om svaret är:

> Sökande kan skicka in kompletteringen när alla obligatoriska handlingar är bifogade.

Då är det den formuleringen som bär kravförståelsen. Knappen är en del av lösningen.

## Behåll helheten synlig

En risk med nedbrytning är att helheten försvinner. Därför behöver Karin behålla en enkel översikt över sammanhanget.

Det kan göras med:

- en kort målformulering,
- en processbild,
- en lista över aktörer,
- en begreppslista,
- en enkel karta över epic, features och stories,
- en beslutslogg,
- en lista över avgränsade undantag,
- koppling mellan stories och acceptanskriterier.

För digital komplettering kan Karin skapa en enkel översikt:

```text
Mål:
Minska ledtid och osäkerhet vid komplettering av ansökan.

Epic:
Digital komplettering av ansökan.

Feature:
Sökande kan ta emot och besvara kompletteringsbegäran.

Första vertikala skiva:
Sökande utan ombud kompletterar en efterfrågad handling före tidsfrist.

Stories:
1. Se att komplettering krävs.
2. Läsa vad som saknas.
3. Ladda upp handling.
4. Skicka in komplettering.
5. Få mottagningsbekräftelse.

Avgränsat till senare:
Ombud, flera kompletteringar, passerad tidsfrist, sekretessmarkerade ärenden.
```

Den här typen av översikt är inte tung dokumentation. Den är ett sätt att göra nedbrytningen begriplig.

## Samarbete med produktägaren

Produktägaren äger prioriteringen, men Karin kan hjälpa till att göra prioriteringen möjlig.

Om kraven är för stora blir prioriteringen ofta grov:

> Ska vi bygga digital komplettering eller inte?

När kraven bryts ned bättre kan produktägaren ta mer nyanserade beslut:

- Vilken användarsituation ger mest nytta först?
- Vilket undantag kan vänta?
- Vilken regel måste lösas innan release?
- Vilken del behöver testas tidigt?
- Vilken del minskar flest manuella kontakter?
- Vilken del är nödvändig för regelefterlevnad?

Karin ska inte ta över produktägarens beslut. Men hon kan göra besluten tydligare genom att formulera alternativen.

Ett bra arbetssätt är att Karin dokumenterar:

- vad som ingår i första skivan,
- vad som uttryckligen inte ingår,
- vilka risker avgränsningen innebär,
- vilka följdfrågor som behöver besvaras,
- vilket beslut produktägaren tog.

## Samarbete med testare

Testbarhet är en av de bästa indikatorerna på om ett funktionellt krav är lagom tydligt.

Om testaren inte kan se hur kravet ska verifieras är det ofta för vagt. Om testaren måste skapa tjugo olika testfall för en enda backloggpost är den kanske för stor.

Karin kan bjuda in testaren tidigt och fråga:

- Vilka exempel behöver vi för att förstå beteendet?
- Vad är normalfallet?
- Vilka undantag måste vara med nu?
- Vilka regler behöver vara testbara?
- Vilka begrepp är otydliga?
- Vad skulle göra kravet svårt att verifiera?

För storyn “Sökande kan läsa vad som saknas” kan testaren bidra med exempel:

- en saknad handling,
- flera saknade handlingar,
- saknad uppgift i formulär,
- sista svarsdatum nära i tid,
- komplettering som redan skickats in.

Alla exempel behöver inte utvecklas samtidigt. Men exemplen hjälper gruppen se hur stor storyn egentligen är.

## Samarbete med utvecklingsteamet

Utvecklingsteamet ser ofta beroenden som inte är synliga i kravdialogen. Det kan handla om integrationer, befintlig datamodell, behörighet, loggning, prestanda eller teknisk skuld.

Karin behöver lyssna på detta utan att låta tekniska uppgifter ersätta kraven.

Ett konstruktivt samtal kan låta så här:

**Utvecklare:** “Vi kan inte göra uppladdning förrän vi har statusmodellen på plats.”

**Karin:** “Då behöver vi förstå vilken del av statusmodellen som krävs för första användarsituationen. Behöver vi hela livscykeln nu, eller bara status för begärd, inskickad och mottagen komplettering?”

Den frågan hjälper teamet hitta en mindre vertikal skiva. Den respekterar den tekniska verkligheten men håller fokus på funktionellt beteende.

## Vanliga misstag

### Misstag: Att klippa isär kravspecifikationen rad för rad

**Varför det händer:**  
Organisationen tror att agil nedbrytning handlar om att göra varje kravrad till en backloggpost.

**Hur man undviker det:**  
Börja med användarsituationer, flöden och beslutspunkter. Fråga vilka delar som kan ge meningsfullt lärande eller nytta.

### Misstag: Att kalla allt för user stories

**Varför det händer:**  
User story-formatet används som mall för all typ av arbete.

**Hur man undviker det:**  
Skilj mellan användarbehov, verksamhetsregler, tekniska uppgifter, analysfrågor och beslut. Allt behöver inte vara en user story för att vara synligt.

### Misstag: Att bryta ned efter teknik i stället för funktionellt värde

**Varför det händer:**  
Teamet behöver lösa tekniska komponenter, och dessa blir då naturliga arbetsdelar.

**Hur man undviker det:**  
Komplettera tekniska uppgifter med funktionella skivor som visar vilket beteende som blir möjligt.

### Misstag: Att göra delarna så små att syftet försvinner

**Varför det händer:**  
Teamet vill ha små arbetsuppgifter, men tappar kopplingen till användarvärde och verksamhetsnytta.

**Hur man undviker det:**  
Varje funktionell kravdel bör kunna kopplas till aktör, syfte, beteende och verifiering.

### Misstag: Att glömma avgränsningarna

**Varför det händer:**  
Det som inte ingår i första versionen dokumenteras inte, eftersom gruppen tänker att “det tar vi senare”.

**Hur man undviker det:**  
Skriv tydligt vad som är avgränsat till senare. Det minskar missförstånd och hjälper produktägaren fatta medvetna beslut.

## Praktiskt arbetssätt: Karins nedbrytningsworkshop

När Karin behöver bryta ned ett större krav kan hon använda följande upplägg.

### 1. Börja med målet

Fråga:

- Varför behövs funktionen?
- Vilken effekt vill vi uppnå?
- Vem ska märka skillnad?
- Vad händer om vi inte gör detta?

### 2. Beskriv användarsituationerna

Fråga:

- Vilka aktörer berörs?
- Vilka situationer ska stödjas?
- Vilka är normalfall?
- Vilka är undantag?
- Vilka situationer är vanligast, viktigast eller mest riskfyllda?

### 3. Välj första vertikala skiva

Fråga:

- Vilken smal del ger meningsfull nytta?
- Vilken del lär oss mest?
- Vilken del behöver fungera för att resten ska bli möjlig?
- Vilken del kan testas med verklighetsnära exempel?

### 4. Formulera utvecklingsbara delar

För varje del:

- aktör,
- behov,
- önskat beteende,
- acceptanskriterier,
- viktiga regler,
- avgränsningar,
- öppna frågor.

### 5. Kontrollera helheten

Fråga:

- Hänger delarna ihop med målet?
- Är något viktigt tappat?
- Finns beroenden?
- Är avgränsningarna dokumenterade?
- Kan produktägaren prioritera?
- Kan testaren verifiera?

## Exempel: före och efter nedbrytning

### Före

> Systemet ska stödja digital komplettering av ansökan där sökande kan ta emot kompletteringsbegäran, skicka in efterfrågade uppgifter och handlingar, få bekräftelse, och där handläggare kan följa upp kompletteringar i ärendet.

Detta är begripligt men för stort.

### Efter

**Mål:**  
Minska ledtid och osäkerhet vid komplettering av ansökan.

**Första skiva:**  
Sökande utan ombud kompletterar en efterfrågad handling före tidsfrist.

**Story 1:**  
Som sökande vill jag se att myndigheten begär komplettering så att jag förstår att jag behöver agera.

**Story 2:**  
Som sökande vill jag läsa vilka uppgifter eller handlingar som saknas så att jag kan komplettera rätt.

**Story 3:**  
Som sökande vill jag ladda upp en efterfrågad handling så att jag kan skicka in min komplettering digitalt.

**Story 4:**  
Som sökande vill jag få bekräftelse på att kompletteringen tagits emot så att jag vet att jag har gjort det jag ska.

**Story 5:**  
Som handläggare vill jag se att komplettering kommit in så att jag kan fortsätta handläggningen.

**Avgränsat till senare:**  
Ombud, flera samtidiga begäranden, komplettering efter tidsfrist, sekretessmarkerade ärenden och automatisk påminnelse.

Nu har kravet blivit möjligt att diskutera, prioritera och utveckla stegvis.

## Checklista: är kravet lagom stort?

Använd frågorna som stöd i refinement eller kravdialog.

- Kan teamet förklara vilket beteende som ska bli möjligt?
- Finns en tydlig aktör eller verksamhetssituation?
- Är syftet begripligt?
- Går kravet att verifiera med exempel eller testfall?
- Är viktiga regler kända?
- Är avgränsningar tydliga?
- Kan produktägaren prioritera delen separat?
- Kan teamet utveckla något meningsfullt utan att hela området är klart?
- Är öppna frågor synliga?
- Finns koppling till mål, epic eller större funktion?

Om svaret är nej på flera frågor är kravet troligen inte redo nog.

## Övningar

### Övning 1: Hitta kravnivåerna

Ta ett större funktionellt krav från din egen vardag eller använd exemplet:

> Användare ska kunna hantera sina ärenden digitalt.

Dela upp det i minst fyra nivåer:

1. mål eller effekt,
2. större funktion,
3. användarsituation,
4. utvecklingsbar del,
5. regel eller detalj.

Reflektera över vilken nivå som oftast saknas i din organisation.

### Övning 2: Gör en första vertikal skiva

Använd kravet:

> Handläggare ska kunna kommunicera digitalt med sökande.

Identifiera:

- normalfall,
- minst tre undantag,
- första möjliga vertikala skiva,
- vad som uttryckligen avgränsas till senare.

### Övning 3: Förbättra en svag user story

Utgå från formuleringen:

> Som system vill jag spara status så att ärendet blir uppdaterat.

Skriv om den till:

- ett användarbehov,
- en verksamhetsregel,
- en teknisk uppgift,
- minst två acceptanskriterier.

### Fördjupning

Välj ett större kravområde i ett pågående eller tidigare projekt. Skapa en enkel karta med:

- mål,
- epic,
- features,
- första vertikala skiva,
- fem möjliga stories,
- avgränsningar,
- öppna frågor.

Diskutera med någon från verksamhet, test eller utveckling om nedbrytningen gör kravet mer begripligt.

## Snabb sammanfattning

- Funktionella krav behöver ofta bli mindre i agilt arbete, men de får inte förlora sammanhang.
- Nedbrytning är analys, inte bara omformatering.
- Kravnivåer hjälper Karin skilja mellan mål, funktion, användarsituation, utvecklingsbar del och regel.
- Vertikala kravskivor gör det möjligt att skapa tidigt lärande genom hela flödet.
- User stories är användbara när de uttrycker aktör, behov och syfte, men allt kravarbete behöver inte pressas in i storyformat.
- “Redo nog” är ett bättre mål än “färdigt för alltid”.
- Avgränsningar behöver dokumenteras, annars uppstår lätt olika förväntningar.

## Quiz/reflektionsfrågor

1. Varför räcker det inte att bara klippa isär ett stort kravdokument i mindre backloggposter?
2. Vad är skillnaden mellan horisontell uppdelning och vertikal kravskiva?
3. När kan en user story bli för liten för att vara användbar som funktionellt krav?
4. Vilka frågor kan Karin ställa för att hitta första meningsfulla utvecklingsbara del?
5. Hur kan testare hjälpa till att avgöra om ett krav är lagom stort?
6. Vad betyder “redo nog” i stället för “helt färdigt”?

## Nästa steg

I nästa kapitel går vi vidare till acceptanskriterier, testbarhet och gemensam definition av klart. När funktionella krav har brutits ned till utvecklingsbara delar behöver teamet förstå hur de ska avgöra om beteendet faktiskt är uppfyllt. Där blir exempel, acceptanskriterier och testbarhet centrala verktyg.
