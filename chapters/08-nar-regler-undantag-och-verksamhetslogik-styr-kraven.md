# Kapitel 8: När regler, undantag och verksamhetslogik styr kraven

## Varför detta kapitel finns

I föregående kapitel såg vi hur acceptanskriterier gör funktionella krav testbara. Det är ett viktigt steg, men i myndighetsmiljö finns ofta en särskild svårighet: det som ska byggas är inte bara ett enkelt användarflöde. Det är ett flöde som styrs av lagar, förordningar, interna beslut, behörigheter, tidsfrister, undantag, kompletteringar och verksamhetsregler som inte alltid är lätta att se vid första anblicken.

För Karin blir det tydligt när teamet arbetar med en digital ansökan. På ytan verkar behovet enkelt:

> Som sökande vill jag kunna skicka in min ansökan digitalt så att handläggningen kan starta snabbare.

Men bakom den formuleringen finns många frågor.

Vem får skicka in ansökan? Vad händer om den sökande företräder någon annan? Vilka uppgifter är obligatoriska? När måste en komplettering begäras? Får systemet automatiskt avslå ett ärende? Vilka uppgifter får visas för vilken roll? Vilken regel gäller om ett datum infaller på en helgdag? Vad ska hända när två regler pekar åt olika håll?

Det här kapitlet handlar om hur funktionella krav kan hantera sådan komplexitet utan att kravunderlaget blir så tungt att ingen längre orkar använda det.

Tre huvudbegrepp står i centrum:

- **verksamhetsregel**,
- **undantag**,
- **beslutstabell**.

Målet är att visa hur Karin kan göra regelstyrd funktionalitet synlig, diskuterbar och testbar. Hon ska inte behöva skriva en jättelik kravspecifikation för att fånga allt. Men hon behöver hjälpa teamet att förstå vilka regler som faktiskt styr beteendet och vilka undantag som måste hanteras redan nu.

## Lärandemål

Efter kapitlet ska du kunna:

- skilja mellan funktionellt krav, verksamhetsregel och undantag,
- identifiera när ett krav döljer regelstyrd komplexitet,
- använda enkla beslutstabeller för att dokumentera regler och utfall,
- formulera frågor som hjälper verksamhet, juridik, test och utveckling att upptäcka otydligheter,
- avgöra när regler bör dokumenteras i en separat regelmodell i stället för direkt i user stories,
- beskriva hur regelstyrda krav kan hållas levande i ett agilt arbetssätt.

## Innan vi börjar

Boken har hittills etablerat några viktiga utgångspunkter.

I kapitel 3 såg vi att kravunderlag i agilt arbete ofta består av flera kompletterande delar, inte av ett enda dokument. I kapitel 6 såg vi att funktionella krav behöver brytas ned så att teamet kan utveckla, testa och lära stegvis. I kapitel 7 såg vi att acceptanskriterier gör kraven verifierbara.

Det här kapitlet bygger vidare på alla tre.

När verksamhetslogik och regler är enkla kan de ofta beskrivas direkt i en story eller i acceptanskriterierna. Men när reglerna blir många, när undantagen är viktiga eller när samma regel används i flera delar av systemet, behöver Karin hjälpa teamet att skilja mellan själva användarbehovet och den logik som styr hur systemet ska bete sig.

Det är skillnaden mellan att skriva:

> Systemet ska hantera ansökningar enligt gällande regelverk.

och att faktiskt synliggöra vad det betyder.

## Regelstyrd funktionalitet ser ofta enklare ut än den är

Ett vanligt misstag i kravarbete är att man beskriver ett verksamhetsflöde som om det vore linjärt.

1. Användaren fyller i uppgifter.
2. Systemet validerar uppgifterna.
3. Ansökan skickas in.
4. Handläggaren granskar ansökan.
5. Beslut fattas.

Det är en rimlig första bild. Den hjälper teamet att förstå huvudflödet. Men i verkligheten är myndighetsprocesser ofta fulla av villkor.

- Om den sökande är under 18 år krävs vårdnadshavares medgivande.
- Om ansökan saknar obligatorisk bilaga ska komplettering begäras.
- Om komplettering inte kommer in inom viss tid ska ärendet hanteras enligt en särskild rutin.
- Om den sökande redan har ett pågående ärende ska ansökan kopplas till det.
- Om uppgiften omfattas av sekretess får den inte visas i vissa vyer.
- Om handläggaren saknar behörighet får ärendet inte öppnas.
- Om ett beslut påverkar en annan myndighet ska underrättelse skickas.

Var och en av dessa regler kan verka liten. Tillsammans avgör de systemets faktiska beteende.

Karin behöver därför vara vaksam när ett krav innehåller ord som:

- enligt regelverk,
- vid behov,
- i förekommande fall,
- om det är relevant,
- behörig användare,
- giltig ansökan,
- komplett ärende,
- korrekt uppgift,
- särskilda skäl,
- normal handläggning.

Sådana uttryck behöver inte vara fel. Men de är ofta signaler om att det finns verksamhetsregler som ännu inte har blivit tydliga.

## Funktionellt krav, verksamhetsregel och undantag

För att undvika sammanblandning behöver Karin hjälpa gruppen att skilja mellan tre saker.

Ett **funktionellt krav** beskriver vad systemet eller tjänsten ska kunna göra. Exempel:

> Systemet ska kunna ta emot en digital ansökan.

En **verksamhetsregel** beskriver ett villkor, en begränsning eller en princip som styr hur verksamheten eller systemet ska bete sig. Exempel:

> En ansökan får inte lämnas in om obligatoriska uppgifter saknas.

Ett **undantag** beskriver när huvudregeln inte räcker eller när ett särskilt utfall ska gälla. Exempel:

> Om uppgiften redan finns i ett betrott register behöver den sökande inte ange den manuellt.

Skillnaden är praktisk. Om allt blandas ihop i en lång kravtext blir det svårt att se vad som är användarflöde, vad som är regel och vad som är undantag. Då blir det också svårt att testa.

Karin kan i stället arbeta med tre nivåer:

1. **Flödet:** vad användaren eller handläggaren gör.
2. **Reglerna:** vad som styr vilka steg, fält, beslut och utfall som gäller.
3. **Undantagen:** vilka situationer som avviker från huvudflödet.

Det gör kravunderlaget lättare att diskutera.

## Exempel: ansökan som verkar enkel

Karin håller en workshop om den digitala ansökan. Produktägaren vill prioritera en första version där sökande kan skicka in ansökan digitalt. Teamet har formulerat en story:

> Som sökande vill jag skicka in min ansökan digitalt så att myndigheten kan påbörja handläggningen utan pappersblankett.

Första utkastet till acceptanskriterier ser ut så här:

- Ansökan kan skickas in när alla obligatoriska fält är ifyllda.
- Den sökande får en bekräftelse när ansökan har skickats in.
- Handläggaren kan se ansökan i ärendekön.

Det är inte dåligt. Men Karin märker att ordet **obligatoriska** bär mycket mer information än kriterierna visar.

Hon frågar:

> Är samma fält alltid obligatoriska?

Verksamhetsspecialisten svarar:

> Nej, det beror på ärendetyp, sökandens roll och om vissa uppgifter redan finns hos oss.

Karin stannar upp. Här finns verksamhetslogik som inte bör gömmas i en enda formulering.

Hon ritar upp en enkel tabell:

| Ärendetyp | Sökanderoll | Uppgift finns redan | Obligatorisk bilaga? | Utfall |
|---|---|---|---|---|
| Ny ansökan | Privatperson | Nej | Ja | Bilaga måste bifogas |
| Ny ansökan | Privatperson | Ja | Nej | Ansökan kan skickas in |
| Ändringsansökan | Ombud | Nej | Ja | Ombudsfullmakt krävs |
| Ändringsansökan | Ombud | Ja | Ja | Ombudsfullmakt krävs ändå |

Tabellen är inte komplett. Det är inte heller meningen. Den gör en dold diskussion synlig. Teamet kan nu se att kravet inte bara handlar om en knapp för att skicka in ansökan. Det handlar också om regler för obligatoriska uppgifter, roller, bilagor och registeruppgifter.

## Beslutstabeller som kravverktyg

En **beslutstabell** är ett enkelt sätt att visa vilka villkor som leder till vilka utfall. Den behöver inte vara avancerad. Den behöver bara göra regelkombinationer synliga.

En praktisk beslutstabell kan innehålla:

- villkor,
- möjliga värden,
- utfall,
- källa eller beslutsgrund,
- kommentar eller öppen fråga.

Exempel:

| Villkor | Värde | Utfall | Källa | Öppen fråga |
|---|---|---|---|---|
| Sökande är privatperson | Ja | Vanlig ansökan möjlig | Verksamhetsregel | Nej |
| Sökande är ombud | Ja | Fullmakt krävs | Intern rutin | Hur kontrolleras fullmakt? |
| Obligatorisk bilaga saknas | Ja | Ansökan kan inte skickas in | Regelverk | Finns undantag? |
| Uppgift finns i register | Ja | Fält kan förifyllas | Systemprincip | Får användaren ändra värdet? |

Det viktiga är inte tabellformatet i sig. Det viktiga är att tabellen tvingar fram frågor som annars lätt kommer sent.

- Vilka villkor styr beteendet?
- Vilka utfall finns?
- Vad är huvudregel?
- Vad är undantag?
- Vilken källa stöder regeln?
- Vem kan besluta om tolkningen?
- Hur ska detta testas?

I ett agilt arbete kan beslutstabellen leva tillsammans med backloggen. En story kan länka till relevanta regler i tabellen. Acceptanskriterierna kan peka på vilka rader som gäller för just den utvecklingsbara delen.

## När ska regler stå i storyn?

Alla regler behöver inte en separat tabell. Om regeln är enkel, lokal och bara gäller en story kan den ofta skrivas direkt i acceptanskriterierna.

Exempel:

> Givet att den sökande inte har fyllt i e-postadress  
> När den sökande försöker skicka in ansökan  
> Så ska systemet visa ett felmeddelande och hindra inskick.

Det är tydligt, testbart och lagom nära funktionen.

Men Karin bör överväga en separat regelbeskrivning när regeln:

- används i flera flöden,
- har många villkor,
- påverkar behörighet, sekretess, beslut eller pengar,
- bygger på lag, förordning eller formellt beslut,
- har undantag som måste hanteras konsekvent,
- ofta misstolkas av olika intressenter,
- behöver granskas av juridik, informationssäkerhet eller förvaltning.

Då blir det riskabelt att gömma regeln i en enskild story. Regeln behöver vara synlig som egen kunskap.

## Undantag är inte störningar — de är kravinformation

I kravworkshops kan undantag ibland upplevas som störande.

Någon beskriver huvudflödet. En annan säger: “Men om personen har skyddade personuppgifter då?” eller “Vad händer om beslutet överklagas?” eller “Det gäller inte för den här ärendetypen.”

Det är lätt att sucka och tänka att gruppen fastnar i detaljer. Men i myndighetsutveckling är undantagen ofta centrala. De visar var verksamhetens ansvar, rättssäkerhet och risker finns.

Karin behöver därför hantera undantag professionellt.

Hon ska inte låta varje specialfall stoppa allt arbete. Men hon ska inte heller sopa bort dem som “edge cases” om de har juridisk, verksamhetsmässig eller användarmässig betydelse.

Ett praktiskt sätt är att sortera undantag i fyra grupper:

| Typ av undantag | Fråga | Möjlig hantering |
|---|---|---|
| Måste hanteras nu | Är funktionen fel eller olaglig utan detta? | In i aktuell story eller närliggande story |
| Måste förstås nu men kan byggas senare | Påverkar det design, data eller flöde? | Dokumentera beslut och skapa backloggpost |
| Kan vänta | Är det ovanligt och utan större konsekvens? | Lägg i bevakad lista |
| Ska inte hanteras | Är det utanför avgränsningen? | Dokumentera avgränsning |

Denna sortering hjälper teamet att fortsätta framåt utan att tappa viktiga krav.

## Exempel: skyddade personuppgifter

Under workshopen om digital ansökan frågar en handläggare:

> Vad händer om den sökande har skyddade personuppgifter?

Teamet blir tyst. Frågan fanns inte i storyn. Produktägaren säger först:

> Det kanske är ett senare specialfall.

Karin ställer några följdfrågor:

- Får sådana personer använda den digitala tjänsten?
- Får deras uppgifter visas för alla handläggare?
- Behöver ärendet märkas särskilt?
- Finns det regler för aviseringar?
- Vad händer om bekräftelsen skickas till fel kanal?
- Är detta en fråga för juridik eller informationssäkerhet?

Efter diskussionen blir slutsatsen att funktionen inte kan produktionssättas utan åtminstone en miniminivå för detta fall. Undantaget påverkar både behörighet, visning och avisering. Det är alltså inte ett litet specialfall. Det är kravinformation som ändrar vad “klar” betyder.

Karin dokumenterar det som en verksamhetsregel:

> Uppgifter för personer med skyddade personuppgifter får endast visas för behöriga roller och får inte användas i standardiserade aviseringar utan särskild kontroll.

Sedan skapar hon tillsammans med teamet två acceptanskriterier för aktuell story och en separat backloggpost för vidare fördjupning.

## Frågor som hittar dold verksamhetslogik

När Karin misstänker att en funktion styrs av regler kan hon använda återkommande frågor.

### Frågor om villkor

- När gäller detta?
- När gäller det inte?
- Vem omfattas?
- Vilka roller eller aktörer påverkas?
- Finns det olika ärendetyper?
- Finns det tidsgränser?
- Finns det beloppsgränser, statusar eller nivåer?
- Finns det kombinationer av villkor som ger annat utfall?

### Frågor om källa

- Varifrån kommer regeln?
- Är regeln juridisk, verksamhetsmässig, teknisk eller historisk?
- Är den dokumenterad?
- Vem kan tolka regeln?
- Vem får ändra den?
- Finns det tidigare beslut som påverkar tolkningen?

### Frågor om utfall

- Vad ska systemet göra när regeln gäller?
- Vad ska systemet hindra?
- Vad ska användaren se?
- Vad ska loggas?
- Vem ska informeras?
- Ska ett ärende skapas, stoppas, märkas eller skickas vidare?

### Frågor om undantag

- Vilka situationer är vanligast att missa?
- Vilka specialfall är juridiskt eller verksamhetsmässigt känsliga?
- Vilka undantag har orsakat problem tidigare?
- Finns det manuella rutiner som behöver ersättas eller stödjas?
- Finns det undantag som bara vissa erfarna handläggare känner till?

Dessa frågor gör Karin till en aktiv kravledare, inte bara en dokumentatör.

## Dokumentera regler utan att skapa ett nytt tungt kravdokument

Risken med regelstyrd funktionalitet är att kravunderlaget blir stort snabbt. Karin kan känna igen mönstret från fasbaserat arbete: varje ny regel läggs in i en växande kravspecifikation. Dokumentet blir mer komplett, men också svårare att läsa, ändra och använda i teamets vardag.

I agilt kravarbete behöver regler dokumenteras så att de är:

- tillräckligt tydliga,
- lätta att hitta,
- kopplade till aktuella stories,
- möjliga att testa,
- möjliga att ändra när tolkningen förändras.

Det kan göras med en kombination av artefakter.

| Artefakt | När den passar | Exempel |
|---|---|---|
| Acceptanskriterium | Regeln gäller bara en liten funktionell del | “Ansökan kan inte skickas om obligatorisk bilaga saknas.” |
| Beslutstabell | Flera villkor ger olika utfall | Ärendetyp + roll + status styr obligatoriska fält |
| Regelkatalog | Samma regler används i flera flöden | Behörighetsregler, tidsfrister, beslutsregler |
| Beslutslogg | Regeln bygger på tolkning eller vägval | “Vi tolkar komplett ansökan som…” |
| Processflöde | Regeln påverkar ordningen mellan steg | Komplettering före beslut |
| Exempel | Regeln blir tydligast genom konkreta fall | “Anna ansöker som ombud utan fullmakt…” |

Poängen är att välja minsta användbara dokumentationsform, inte största möjliga.

## Regler behöver ägarskap

En viktig skillnad mellan vanliga krav och verksamhetsregler är att regler ofta behöver tydligt ägarskap.

En user story kan ägas och prioriteras av produktägaren. Men en regel kan komma från lag, förordning, intern policy, juridisk tolkning, informationssäkerhet, arkitekturprincip eller förvaltningsbeslut. Då räcker det inte alltid att produktägaren “tycker” något.

Karin behöver hjälpa teamet att se:

- vem som kan förklara regeln,
- vem som kan godkänna tolkningen,
- vem som påverkas om regeln ändras,
- var regeln ska förvaltas efter leverans.

Ett enkelt fält i regelkatalogen kan räcka:

| Regel | Källa | Tolkning beslutad av | Ägare | Senast granskad |
|---|---|---|---|---|
| Fullmakt krävs för ombud | Intern rutin + juridisk tolkning | Juridik och verksamhetsansvarig | Verksamhetsområde Ansökan | 2026-05-15 |

Detta kan verka administrativt, men det minskar risken för att teamet bygger på en otydlig eller inofficiell tolkning.

## När regelstyrning påverkar nedbrytningen

I kapitel 6 såg vi att funktionella krav behöver bli små nog att utvecklas. Regelstyrd komplexitet påverkar hur Karin bör bryta ned arbete.

Ett vanligt misstag är att försöka bygga alla regler för ett flöde innan något kan visas. Då blir första leveransen stor och långsam. Ett annat misstag är att bygga ett för enkelt huvudflöde utan att se att senare regler kommer kräva omtag i design, data eller användargränssnitt.

Karin behöver hitta en mellanväg.

Hon kan fråga:

- Vilka regler behövs för att huvudflödet ska vara meningsfullt?
- Vilka regler påverkar informationsmodell, behörighet eller integration?
- Vilka regler kan läggas till senare utan större ombyggnad?
- Vilka undantag behöver vi förstå nu även om vi inte bygger dem nu?
- Vilket regelpaket ger oss bäst lärande tidigt?

Det leder ofta till en nedbrytning där första versionen inte är “allt eller inget”, utan ett medvetet avgränsat regelpaket.

Exempel:

1. Första utvecklingsbara del: ansökan för privatperson med standardärende och obligatoriska fält.
2. Nästa del: ansökan via ombud och fullmaktskontroll.
3. Nästa del: skyddade personuppgifter och begränsad visning.
4. Nästa del: kompletteringsflöde och tidsfrister.

Det är fortfarande agilt. Men det är inte naivt. Teamet känner till viktiga regler och kan välja ordning medvetet.

## Regler som inte ska byggas in för hårt

En annan fallgrop är att regler byggs in på ett sätt som gör dem svåra att ändra.

Kravanalytikern behöver inte designa teknisk lösning. Men Karin behöver vara uppmärksam när verksamheten säger:

> Den här regeln ändras ofta.

eller:

> Det finns olika tolkningar beroende på ärendetyp.

eller:

> Vi vet att regelverket är på väg att ändras nästa år.

Då bör hon lyfta frågan tillsammans med arkitekt, utvecklare och produktägare. Det funktionella kravet handlar inte bara om dagens utfall, utan även om förändringsbarhet.

Exempel på kravfråga:

> Behöver verksamheten kunna ändra gränsvärden, tidsfrister eller textmallar utan ny systemrelease?

Det är inte alltid svaret är ja. Men frågan behöver ställas. Annars riskerar teamet att bygga in verksamhetslogik så hårt att varje regeländring blir dyr.

## Vanliga misstag

### Misstag 1: Att skriva “enligt gällande regelverk” och tro att kravet är tydligt

**Varför det händer:**  
Formuleringen känns formell och korrekt. Den signalerar att systemet ska följa reglerna.

**Hur man undviker det:**  
Identifiera vilka regler som faktiskt påverkar systemets beteende. Dokumentera villkor, utfall, källa och ansvarig tolkning där det behövs.

### Misstag 2: Att behandla undantag som störningar

**Varför det händer:**  
Teamet vill komma framåt och undantag gör arbetet mer komplext.

**Hur man undviker det:**  
Sortera undantag efter konsekvens: måste byggas nu, måste förstås nu, kan vänta eller ska inte hanteras.

### Misstag 3: Att lägga all regelinformation i user stories

**Varför det händer:**  
Backloggen blir den naturliga platsen för allt kravarbete.

**Hur man undviker det:**  
Lägg enkla, lokala regler i acceptanskriterier. Lägg återanvända, komplexa eller formellt styrda regler i regelkatalog, beslutstabell eller annan gemensam artefakt.

### Misstag 4: Att bygga huvudflödet utan att se regelkonsekvenser

**Varför det händer:**  
Huvudflödet är lättare att förstå och prioriteras ofta först.

**Hur man undviker det:**  
Identifiera tidigt vilka regler som påverkar data, behörighet, integrationer, beslut och användargränssnitt. De behöver inte alltid byggas först, men de måste förstås tillräckligt tidigt.

### Misstag 5: Att inte veta vem som äger regeln

**Varför det händer:**  
Regler förs vidare muntligt eller finns i gamla dokument utan tydlig ägare.

**Hur man undviker det:**  
Dokumentera källa, tolkning och ägare för regler som är viktiga, känsliga eller återanvänds i flera flöden.

## Övningar

### Övning 1: Hitta dold regelstyrning

Välj ett funktionellt krav från ett pågående eller tidigare arbete. Stryk under ord som kan dölja regler, till exempel:

- behörig,
- komplett,
- giltig,
- korrekt,
- relevant,
- enligt regelverk,
- vid behov,
- särskilda fall.

Skriv sedan minst fem frågor som behöver besvaras innan kravet kan bli testbart.

### Övning 2: Skapa en enkel beslutstabell

Utgå från följande krav:

> Systemet ska avgöra om en digital ansökan kan skickas in.

Skapa en beslutstabell med minst fyra villkor och tre möjliga utfall. Exempel på villkor kan vara ärendetyp, sökanderoll, obligatorisk bilaga, befintligt ärende eller skyddade personuppgifter.

### Övning 3: Sortera undantag

Lista fem undantag från ett kravområde du känner till. Sortera dem i fyra grupper:

1. Måste hanteras nu.
2. Måste förstås nu men kan byggas senare.
3. Kan vänta.
4. Ska inte hanteras.

Motivera varje placering med en mening.

### Fördjupning

Skapa en liten regelkatalog för ett kravområde. För varje regel, ange:

- regel,
- källa,
- vem som kan tolka regeln,
- vem som äger regeln,
- vilka stories eller funktioner regeln påverkar,
- hur regeln kan testas.

Reflektera sedan över vilka regler som är stabila och vilka som troligen kommer förändras.

## Snabb sammanfattning

- Regelstyrd funktionalitet ser ofta enkel ut i huvudflödet men innehåller många villkor och undantag.
- Ett funktionellt krav beskriver vad systemet ska göra; en verksamhetsregel beskriver vad som styr beteendet.
- Undantag är inte störningar. De är kravinformation som behöver sorteras och hanteras medvetet.
- Beslutstabeller gör kombinationer av villkor och utfall synliga.
- Enkla regler kan ligga i acceptanskriterier; komplexa eller återanvända regler behöver ofta en separat regelbeskrivning.
- Regler behöver källa, tolkning och ägarskap, särskilt i myndighetsmiljö.
- Agilt kravarbete betyder inte att regler ignoreras. Det betyder att regler görs synliga, prioriteras och utvecklas stegvis.

## Quiz/reflektionsfrågor

1. Vad är skillnaden mellan ett funktionellt krav och en verksamhetsregel?
2. Varför kan formuleringen “enligt gällande regelverk” vara problematisk i kravarbete?
3. När räcker det att beskriva en regel som acceptanskriterium?
4. När bör en regel dokumenteras separat från en user story?
5. Hur kan en beslutstabell hjälpa teamet att hitta otydligheter?
6. Varför behöver undantag sorteras i stället för att bara samlas i en lång lista?
7. Vilka roller kan behöva delta när en regel ska tolkas?
8. Hur kan regelstyrning påverka nedbrytningen av funktionella krav?

## Nästa steg

I detta kapitel har vi sett hur Karin kan hantera regler, undantag och verksamhetslogik utan att gå tillbaka till ett tungt, låst kravdokument. Hon använder i stället tydliga artefakter: acceptanskriterier, beslutstabeller, regelkataloger, exempel och beslutsloggar.

Nästa kapitel går vidare till en närliggande utmaning: **spårbarhet utan att skapa dokumentationsbörda**. När kravunderlaget består av flera levande delar behöver Karin kunna visa sambanden mellan behov, krav, regler, beslut, test och levererad funktion. Frågan är hur det kan göras tillräckligt bra utan att skapa ett parallellt administrativt system som ingen använder.
