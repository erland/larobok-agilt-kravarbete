# Kapitel 1: När XLPM inte längre räcker som kravlogik

## Varför detta kapitel finns

Du som har arbetat länge med krav i en myndighetskontext känner sannolikt igen värdet av en tydlig kravfas. Innan utveckling startar vill man förstå verksamhetens behov, berörda användargrupper, regler, processer, undantag, integrationer, informationsflöden och beslutspunkter. Det är inte konstigt. I en statlig myndighet kan otydliga krav snabbt få konsekvenser: felaktiga beslut, svag spårbarhet, bristande regelefterlevnad, dyra omtag eller lösningar som blir svåra att förvalta.

Ett fasbaserat arbetssätt kan därför kännas tryggt. Först utreder vi. Sedan dokumenterar vi. Därefter granskar vi. När kraven är accepterade kan utveckling påbörjas. Den logiken har hjälpt många organisationer att skapa ordning, särskilt när uppdraget är stort, finansieringen är beslutad i etapper och flera ansvariga funktioner behöver kunna följa vad som händer.

Samtidigt förändras förutsättningarna när organisationen vill arbeta mer agilt. Då räcker det inte alltid att först beskriva hela kravbilden och därefter lämna över den till utveckling. Behov kan visa sig vara annorlunda än man trodde. Användare kan reagera oväntat. Regler kan tolkas på nya sätt när de konkretiseras i en digital tjänst. Tekniska beroenden kan visa sig enklare eller svårare än analysen antydde. Prioriteringar kan förändras när organisationen lär sig mer.

Det här kapitlet handlar om det första skiftet i boken: från att se kravarbete som en fas där kravbilden ska göras färdig, till att se kravarbete som en kontinuerlig förmåga som hjälper organisationen att fatta bättre beslut över tid.

Målet är inte att ställa XLPM eller fasorienterade arbetssätt mot agila arbetssätt som om det ena vore rätt och det andra fel. Poängen är snarare att de bygger på olika kravlogik. När kravlogiken förändras behöver även kravanalytikerns sätt att skapa trygghet, tydlighet och kvalitet förändras.

## Lärandemål

Efter kapitlet ska du kunna:

- förklara skillnaden mellan fasbaserad kravlogik och agil kravlogik,
- känna igen när ett kravarbete försöker skapa för mycket säkerhet för tidigt,
- skilja mellan krav som behöver vara stabila tidigt och krav som kan utvecklas stegvis,
- använda begreppet *tillräckligt kravunderlag* som alternativ till helt färdig kravbild,
- reflektera över hur din egen kravpraktik påverkas när organisationen går från fas till flöde.

## Innan vi börjar

I den här boken använder vi ordet **kravlogik** för att beskriva de underliggande antaganden som styr hur organisationen tänker om krav. En kravlogik svarar på frågor som:

- När behöver krav vara tydliga?
- Hur detaljerade behöver krav vara?
- Vem får ändra ett krav?
- Vad räknas som ett godkänt kravunderlag?
- När är det säkert att utveckling får börja?
- Hur hanteras ny kunskap som uppstår under arbetets gång?

I en fasbaserad kravlogik är svaret ofta: så mycket som möjligt ska vara utrett, dokumenterat och accepterat innan utveckling startar. I en agil kravlogik är svaret snarare: tillräckligt ska vara förstått för att ta nästa ansvarsfulla steg, och resten behöver kunna förtydligas när vi lär oss mer.

Det senare betyder inte att man chansar. Det betyder att man behandlar vissa delar av kravbilden som stabila beslut och andra delar som hypoteser, frågor eller ännu inte färdiga detaljer.

## Situationen: Karin känner igen mönstret

Myndigheten för samhällstjänster ska modernisera ett äldre handläggningssystem. Systemet används av handläggare varje dag och har under många år byggts ut med nya funktioner, specialregler och manuella rutiner. Det finns integrationer till andra myndigheter, flera ärendetyper, behörighetsregler och historiska undantag som få personer längre har full överblick över.

Karin, erfaren kravanalytiker, blir inbjuden till ett tidigt uppstartsmöte. Hon har gjort liknande arbeten förr. Hennes första tanke är att projektet behöver en ordentlig kravanalys innan utvecklingsteamet börjar bygga.

Hon börjar skissa på en plan:

1. genomföra intervjuer med handläggare, chefer och systemförvaltning,
2. kartlägga nuvarande processer,
3. samla in kända problem,
4. dokumentera funktionella krav,
5. beskriva undantag och verksamhetsregler,
6. låta verksamheten granska kravspecifikationen,
7. lämna över ett godkänt kravunderlag till utveckling.

Planen är rimlig. Den är inte slarvig. Den bygger på erfarenhet.

Men på mötet säger produktägaren:

> Vi behöver komma igång tidigare den här gången. Vi vet att allt inte är utrett, men vi vill börja med ett första flöde för digital ansökan och lära oss under tiden.

En utvecklare fyller i:

> Om vi får vänta på hela kravspecifikationen kommer vi ändå behöva ställa om när vi ser hur reglerna fungerar i praktiken.

En testare säger:

> Jag behöver inte alla krav nu, men jag behöver förstå vilka exempel och acceptanskriterier som gäller för första flödet.

Karin märker att frågan inte bara är hur snabbt hon kan skriva krav. Frågan är vilken typ av kravunderlag som faktiskt hjälper arbetet framåt.

## Det invanda sättet: skapa trygghet genom fullständighet

I ett fasbaserat arbetssätt skapas trygghet ofta genom fullständighet. Ju mer som är utrett och dokumenterat, desto bättre känns det att gå vidare. Kravspecifikationen blir ett sätt att minska osäkerhet innan kostnaderna för utveckling uppstår.

Det finns goda skäl till detta. En myndighet behöver kunna visa varför en funktion finns, vilka regler den bygger på och vilka behov den ska möta. Beslut behöver kunna granskas i efterhand. Förvaltningen behöver förstå vad som har byggts. Test behöver veta vad som ska verifieras. Uppföljning behöver veta om lösningen faktiskt svarar mot uppdraget.

Problemet uppstår när fullständighet blir det enda sättet att skapa trygghet.

Då kan kravarbete börja sträva efter en nivå av säkerhet som inte är möjlig i början. Kravanalytikern pressas att formulera detaljer innan verksamheten förstår konsekvenserna. Intressenter får ta ställning till dokument som är svåra att föreställa sig i användning. Teamet får krav som ser färdiga ut men som innehåller antaganden. När verkligheten sedan visar sig vara mer komplex upplevs förändringar som avvikelser, trots att de egentligen är ny kunskap.

Det invanda arbetssättet kan alltså vara professionellt och ändå otillräckligt för den situation organisationen befinner sig i.

## Varför det skaver i agil utveckling

Agil utveckling bygger på att kunskap kan uppstå under arbetets gång. Det gäller inte bara teknisk kunskap, utan också verksamhetskunskap.

När ett team börjar konkretisera ett flöde kan frågor bli synliga som inte kom fram i intervjuerna. När användare ser en tidig version kan de upptäcka att deras egentliga problem låg någon annanstans. När testare börjar formulera exempel kan de hitta undantag som verksamheten inte tänkte på. När arkitekten tittar på integrationer kan vissa krav behöva delas upp eller prioriteras om.

Om kravunderlaget behandlas som färdigt för tidigt blir den nya kunskapen störande. Den ses som ändringsbegäran, scope creep eller bristande kravkvalitet.

Om kravunderlaget däremot behandlas som levande kan samma kunskap bli värdefull. Den hjälper organisationen att fatta bättre beslut innan för mycket har byggts.

Det är här kravanalytikerns arbete förändras. Rollen handlar inte längre bara om att minska osäkerhet före utveckling. Den handlar också om att hjälpa organisationen hantera osäkerhet på ett kontrollerat sätt under utveckling.

## Ett användbart skifte: från komplett till tillräckligt

Ett centralt begrepp i boken är **tillräckligt kravunderlag**.

Ett tillräckligt kravunderlag är inte ett slarvigt kravunderlag. Det är ett kravunderlag som är tillräckligt tydligt för nästa beslut, nästa prioritering eller nästa utvecklingssteg.

Det betyder att frågan ändras från:

> Är alla krav färdiga?

till:

> Vad behöver vara tydligt för att vi ansvarsfullt ska kunna ta nästa steg?

Det kan låta som en liten skillnad, men i praktiken förändrar det mycket.

För ett första utvecklingssteg kanske teamet behöver:

- förstå vilket användarflöde som är viktigast,
- veta vilka målgrupper som ingår,
- känna till de viktigaste verksamhetsreglerna,
- ha några konkreta exempel på godkända och avslagna ärenden,
- veta vilka undantag som ska hanteras nu och vilka som kan vänta,
- ha acceptanskriterier för första versionen,
- känna till öppna frågor och risker.

Det är inte samma sak som att hela kravbilden är klar. Men det kan vara tillräckligt för att börja skapa värde, testa antaganden och upptäcka oklarheter tidigt.

## Vad behöver vara stabilt tidigt?

Agilt kravarbete betyder inte att allt kan vara öppet. Vissa delar behöver vara stabila tidigt, särskilt i myndighetsmiljö.

Exempel på sådant som ofta behöver vara tydligt tidigt är:

- uppdragets syfte,
- vilka lagar, regler eller styrande dokument som påverkar området,
- vilka användargrupper och verksamhetsprocesser som berörs,
- vilka risker som är oacceptabla,
- vilka beslut som kräver formell förankring,
- vilka beroenden som kan påverka tid, kostnad eller lösningsval,
- vilka delar av lösningen som måste vara spårbara i efterhand.

Om dessa delar är otydliga kan teamet röra sig snabbt men åt fel håll. Då hjälper det inte att arbetssättet är agilt.

Karin behöver därför inte släppa sin vana att skapa struktur. Hon behöver snarare använda den mer selektivt. Hon behöver lägga mest kraft på de delar där tidig tydlighet minskar verklig risk.

## Vad kan växa fram stegvis?

Andra delar av kravbilden kan ofta utvecklas stegvis.

Exempel:

- exakt utformning av vissa användarsteg,
- detaljer i skärmflöden,
- ordning mellan mindre funktioner,
- vissa undantag som sällan inträffar,
- formuleringar i användargränssnitt,
- hur mycket stöd användaren behöver i varje steg,
- detaljer i rapporter eller interna vyer.

Det betyder inte att dessa delar är oviktiga. Det betyder att det kan vara mer effektivt att förtydliga dem när teamet arbetar med just den delen av lösningen.

Kravanalytikerns uppgift blir då att hålla isär två sorters oklarhet:

1. **Farlig oklarhet** — sådant som kan leda till fel riktning, fel beslut, regelbrott, stora omtag eller bristande ansvar.
2. **Hanterbar oklarhet** — sådant som kan förtydligas senare utan att arbetet riskerar att gå fel.

Ett moget agilt kravarbete försöker inte ta bort all oklarhet. Det försöker synliggöra vilken oklarhet som är acceptabel just nu.

## Karin ändrar sin plan

Efter uppstartsmötet gör Karin inte om allt. Hon kastar inte bort sin erfarenhet. Men hon ändrar ordningen och syftet med sitt kravarbete.

I stället för att planera för en komplett kravspecifikation före utveckling skapar hon tre spår.

Det första spåret är **tidig stabilitet**. Där samlar hon det som behöver förstås innan teamet kan börja: uppdrag, målgrupper, centrala regler, risker, beroenden och beslut som kräver förankring.

Det andra spåret är **första utvecklingsbara flödet**. Där arbetar hon tillsammans med produktägaren, teamet och testaren för att beskriva ett första begränsat användarflöde: digital ansökan för en vanlig ärendetyp. Hon tar fram exempel, acceptanskriterier och öppna frågor.

Det tredje spåret är **levande frågor**. Där dokumenterar hon sådant som behöver utredas, men som inte måste vara klart innan teamet börjar med första flödet. Det kan handla om mer ovanliga undantag, senare ärendetyper eller rapportbehov.

Hon säger till gruppen:

> Jag tror inte att vi ska försöka göra hela kravbilden färdig innan ni börjar. Men vi behöver vara tydliga med vad som är beslutat, vad som är antaganden och vad som fortfarande är öppet.

Det är ett annat sätt att skapa trygghet. Inte genom att allt är färdigt, utan genom att alla vet vad som är stabilt, vad som är pågående och vad som är osäkert.

## Från överlämning till samarbete

En annan förändring är att kravarbete inte längre kan ses som något som avslutas med en överlämning.

I fasbaserade upplägg är överlämningen ofta central. Kravanalytikern tar fram underlag, verksamheten godkänner och teamet tar emot. Om teamet senare har frågor kan det kännas som att kraven var ofullständiga.

I agilt kravarbete är frågor inte ett tecken på misslyckande. De är en del av arbetet. Men de behöver hanteras strukturerat.

Karin behöver därför vara närvarande när kraven förtydligas. Hon behöver delta i dialoger där teamet ställer frågor, testaren formulerar exempel, produktägaren prioriterar och verksamheten förklarar undantag. Hennes dokumentation blir inte slutpunkten för kravarbete. Den blir ett stöd för samtal, beslut och spårbarhet.

Detta kan vara ovant. För en erfaren kravanalytiker kan det kännas som att arbetet aldrig blir klart. Men poängen är inte att allt ska vara öppet hela tiden. Poängen är att kraven blir klara i rätt tid, på rätt nivå och för rätt syfte.

## Vad händer med kravspecifikationen?

En vanlig fråga är om kravspecifikationen försvinner.

Svaret i den här boken är: inte nödvändigtvis. Men dess roll förändras.

I vissa situationer behövs fortfarande sammanhållna dokument. Det kan gälla för upphandling, formell förankring, regelstyrda områden, säkerhetsbedömningar eller långsiktig förvaltning. Men kravspecifikationen är inte alltid den bästa platsen för all kravinformation.

Ett mer agilt kravarbete kan i stället använda flera kompletterande artefakter:

- målbild och effektbeskrivning,
- backloggposter,
- user stories eller användningsfall,
- acceptanskriterier,
- verksamhetsregler,
- process- eller flödesbeskrivningar,
- begreppslista,
- beslutslogg,
- risk- och frågelista,
- testexempel,
- länkar till styrande dokument.

Det viktiga är inte vilken mall som används. Det viktiga är att kravinformationen är begriplig, användbar, spårbar och uppdateringsbar.

## Vanliga misstag

### Misstag 1: Att tolka agilt som att krav inte behöver analyseras

Ibland uppfattas agil utveckling som att teamet kan börja bygga utan ordentligt kravarbete. Det leder ofta till otydlighet, omtag och frustration.

**Varför det händer:**  
Organisationen vill undvika långa förstudier och drar slutsatsen att all föranalys är slöseri.

**Hur man undviker det:**  
Skilj mellan tung förhandsdetaljering och nödvändig tidig analys. Vissa frågor måste förstås innan utveckling startar, särskilt regler, risker, målgrupper och syfte.

### Misstag 2: Att försöka göra hela kravbilden färdig ändå

Ett annat misstag är att behålla samma kravambition som tidigare, men pressa in den i ett kortare agilt upplägg. Då får kravanalytikern för lite tid att göra ett arbete som egentligen fortfarande bygger på fullständighet.

**Varför det händer:**  
Organisationen säger att den arbetar agilt, men fortsätter förvänta sig samma typ av kravleverabler som i fasbaserade projekt.

**Hur man undviker det:**  
Gör tydligt vad som behöver vara klart inför nästa steg och vad som kan utvecklas senare. Dokumentera öppna frågor i stället för att dölja dem i skenbart färdiga krav.

### Misstag 3: Att blanda beslut, antaganden och frågor

Kravunderlag blir svåra att använda när beslutade krav, preliminära antaganden och öppna frågor skrivs på samma sätt.

**Varför det händer:**  
Man vill skapa ordning och råkar formulera allt som krav.

**Hur man undviker det:**  
Märk tydligt vad som är beslutat, vad som är antagande och vad som är fråga. Det gör underlaget mer ärligt och mer användbart.

### Misstag 4: Att se förändring som kravmisslyckande

När nya insikter uppstår kan de uppfattas som bevis på att kravanalysen var dålig.

**Varför det händer:**  
Fasbaserad kravlogik premierar tidig stabilitet och kan göra sena förändringar laddade.

**Hur man undviker det:**  
Skilj mellan slarv och lärande. Vissa förändringar beror på bristande analys, men andra beror på att organisationen nu vet mer än den gjorde tidigare.

## Praktiskt arbetssätt: tre listor i stället för en kravmassa

Ett enkelt sätt att börja arbeta annorlunda är att dela upp kravunderlaget i tre listor.

### 1. Stabilt nu

Här lägger Karin sådant som är beslutat eller måste betraktas som styrande.

Exempel:

- berörda målgrupper,
- centrala lag- eller regelkrav,
- beslutade effektmål,
- kritiska verksamhetsregler,
- risker som måste hanteras tidigt.

### 2. Behöver förtydligas inför nästa steg

Här lägger hon sådant som teamet behöver förstå för kommande utvecklingsarbete.

Exempel:

- acceptanskriterier för första flödet,
- exempel på vanliga ärenden,
- prioriterade undantag,
- frågor till verksamheten,
- testdata eller scenarier.

### 3. Kan vänta, men får inte glömmas

Här lägger hon sådant som är relevant men inte behöver lösas direkt.

Exempel:

- ovanliga specialfall,
- framtida rapportbehov,
- alternativa användarflöden,
- förbättringsidéer,
- frågor som kräver senare beslut.

Den här uppdelningen gör två saker. Den hjälper teamet att komma vidare utan att tappa kontrollen, och den hjälper verksamheten att se att allt inte ignoreras bara för att allt inte görs nu.

## Övningar

### Övning 1: Sortera kravbilden

Tänk på ett kravarbete du själv har deltagit i. Välj ett område där kraven var omfattande eller svåra att få klara.

Sortera informationen i tre grupper:

1. Vad behövde vara stabilt tidigt?
2. Vad behövde vara tydligt inför nästa utvecklingssteg?
3. Vad hade kunnat vänta utan att skapa stor risk?

Reflektera sedan:

- Vilken information försökte ni kanske göra färdig för tidigt?
- Vilken information borde ha varit tydligare tidigare?
- Vilka öppna frågor hade behövt synliggöras bättre?

### Övning 2: Skriv om frågan

Skriv om frågan:

> Är kravspecifikationen klar?

till tre mer användbara frågor för ett agilt kravarbete.

Exempel:

- Vad behöver teamet förstå för att börja med nästa prioriterade flöde?
- Vilka beslut är redan fattade och vilka är fortfarande öppna?
- Vilka risker uppstår om vi väntar med den här kravdetaljen?

Formulera gärna egna frågor som passar din organisation.

### Fördjupning: hitta din egen kravlogik

Beskriv kort hur din organisation brukar tänka kring krav:

- När anses krav vara klara?
- Vem får ändra eller förtydliga krav?
- Hur dokumenteras osäkerhet?
- Hur hanteras nya insikter under utveckling?
- Är förändringar välkomna, neutrala eller misstänkliggjorda?

Det du beskriver är organisationens kravlogik i praktiken.

## Snabb sammanfattning

- XLPM- och fasbaserat kravarbete kan skapa tydlighet, ansvar och spårbarhet.
- I agil utveckling uppstår ofta viktig kunskap under arbetets gång.
- Kravanalytikerns uppgift förändras från att göra allt färdigt i förväg till att skapa tillräcklig tydlighet för nästa ansvarsfulla steg.
- Ett tillräckligt kravunderlag är inte slarvigt. Det är anpassat till beslutet, risken och utvecklingssteget.
- All oklarhet är inte lika farlig. Vissa frågor måste lösas tidigt, andra kan växa fram stegvis.
- Kravdokumentation försvinner inte, men den behöver bli mer levande, uppdateringsbar och användbar i dialog.
- Ett praktiskt första steg är att skilja mellan det som är stabilt nu, det som behöver förtydligas inför nästa steg och det som kan vänta men inte får glömmas.

## Quiz/reflektionsfrågor

1. Vad menas med kravlogik?
2. Varför kan ett kravunderlag se färdigt ut men ändå bygga på osäkra antaganden?
3. Vad är skillnaden mellan fullständigt kravunderlag och tillräckligt kravunderlag?
4. Ge två exempel på kravrelaterad information som ofta behöver vara stabil tidigt i en myndighetskontext.
5. Ge två exempel på kravdetaljer som ofta kan växa fram stegvis.
6. Hur kan en kravanalytiker dokumentera osäkerhet utan att skapa oordning?
7. Vad riskerar att hända om alla öppna frågor skrivs som färdiga krav?

## Nästa steg

I det här kapitlet har vi sett att kravarbete förändras när organisationen går från fasbaserad kravlogik till mer kontinuerligt kravarbete. Karin behöver fortfarande skapa tydlighet, men hon behöver inte skapa all tydlighet på samma gång.

Nästa kapitel handlar om rollen. Om kraven inte längre skrivs färdigt av kravanalytikern och sedan lämnas över, vad händer då med kravanalytikerns ansvar? Försvinner rollen, eller blir den ännu viktigare på ett annat sätt?
