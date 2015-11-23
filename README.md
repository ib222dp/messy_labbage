## Problem - Messy Labbage
Denna laboration består av en undersökning av en befintlig webbapplikation och framställandet av en rapport. Du kommer få en webbapplikation som kanske inte riktigt är uppbyggd på det sätt du skulle vilja. Tanken med denna uppgift är att du med din kunskap ska analysera och förbättra denna applikation **både ur ett prestanda- och ett säkerhetsperspektiv.** Applikationen är ganska liten så vi kanske inte kommer se jättestora förändringar i prestandan men vi får i alla fall ett tillfälle att ta upp de teorier som kursen tar upp.

Senariot är följande: Du har fått i uppdrag att som arbetsprov för ett förtag gå igenom en av deras klienters applikationer och försöka identifiera säkerhetshål och prestandabovar och på ett tydligt och snyggt sätt sammanställa detta i en proffsig rapport. Applikationen är som klienten säger "skriven av chefens son" och kan därför ha lite brister rent implementationsmässigt. Applikationen är skriven i node.js men det spelar ingen roll om du är ny inför denna plattform för din uppgift är att testa den mot eventuella attackvektorer och analysera den front-end optimering som kan göras. De saker du vill kontroller ai arkitekturen kommer du nog kunna lista ut hur de hittas och fungerar.

Datalagringen sköts av en filbaserad [databashanterare som heter SQLite3](https://www.sqlite.org/)

Applikationen är en enkel meddelande-applikatione som klienten tänkt ha som en enklare form av intern todo-list. Klienten är dock noga att påpeka att denna lista måste vara oåtkomlig för användare/konkurrenter som inte har inloggningsuppgifter.

Applikationen är endast testad och avsedd för chrome.

### Inloggningsuppgifter

Följande inloggningsuppgifter finns till applikationen:
* user@user.se:pass1user!
* user2@user.se:!pass@user!
* admin@user.se:!admin@40  ( detta är inloggning för admin)

### Kör igång applikationen
Klona ner följande repo: <REPOLINK HERE>

Använd terminalen och bege dig in i repots mapp.
1. Skapa en virtuell maskin med ```vagrant up```
2. Logga in på maskinen med ```vagrant ssh```
3. Be dig till rätt mapp på ubuntu-maskinen med ```cd \vagrant```
4. Kör kommandot ```npm install``` OBS! Det verkar som detta kan ge lite röda felmeddelande för Windowsanvändare. Det bör dock gå att starta applikationen ändå.
5. Starta applikationen med ```node app.js```
6. Öppna en webbläsare och bege dig till adressen "http://localhost:8080" för att komma till inloggningsrutan och börja analysera applikationen.

**OBS! Varje gång man startar om applikationen töms databasen. Detta är endast för denna utvecklingsversion och alltså inget som ska tas upp i rapporten.** Det kan dock vara smidigt när man håller på att testa att då och då starta om servern för att tömma databasen. Inloggningsuppgifterna kommer dock skrivas in på nytt vid varje omstart.


### Rapporten
Examinationen av denna uppgift går till genom att skriva en tydlig och väl uppbyggd rapport. Rapporten ska vara skriven i md-format och tydligt publiceras på det repo du har delat med användaren "1dv449" på GitHub.

Följande krav finns på innehållet rapporten

* Rapporten ska vara tydligt uppmärkt med namn (och användarnamn).
* Rapporten ska vara tydligt uppdelad i tre delar
  * Säkerhetsproblem
  * Prestandaproblem (främst front-end - vi fokuserar inte på kodoptimeringar i back-end)
  * Egna övergripande reflektioner
* Varje säkerhetsproblem/prestandaproblem du hittar med applikationen ska tydligt redovisas enligt följande
  * Bra och tydlig rubrik på problemet
  * Vad problemet innebär, teori om problemet (referens till teori fodras)
  * Vilka eventuella följder problemet kan skapa (gäller främst säkerhetshål)
  * Hur man åtgärdar problemet (referens till teori fodras)

Förutom själva innehållet kommer vi ha följande krav på rapporten
* Rapporten ska vara skriven på svenska eller engelska
* Rapporten ska ha bra språk, mycket felstavning, särskrivningar och gramatikfel gör att rapporten får kompletteras. Låt en kompis (utanför kursen) läsa igenom den eller ta hjälp av vår [studeiverkstad](http://lnu.se/ub/studieverkstaden)
* Det ska också finnas tydliga [referenser](http://lnu.se/ub/sok-och-skrivhjalp/skriva-referenser) till den teori du använder dig av. Referenssystemet vi använder oss av (och kommer använda oss av i B-uppsatsen) är ieee-systemet. Läs mer hur du använder detta på: [http://hj.se/bibl/sok---skrivhjalp/litteraturreferenser---sa-skriver-du/ieee-systemet.html](http://hj.se/bibl/sok---skrivhjalp/litteraturreferenser---sa-skriver-du/ieee-systemet.html)

##Redovisning
Rapporten lämnas in genom att den finns tydligt tillgänglig på ditt delade repo (glöm inte att dela repo med användaren "1dv449") innan den deadline som finns på webbplatsen kursplanering.

### Bedömning
Vi kommer ställa krav både på din rapport och att du i den tydligt visar att du tagit del av den teori som tagits upp under detta moment. Följer du inte heller de krav som finns på det språkliga, referenshantering eller helt saknar referenser kommer du får komplettering. Vi nämner inga siffror på hur många problem man ska hitta och redovisa utan vi utgår självklart från att alla försöker hitta så många som möjligt. Missar man uppenbara delar eller helt enkelt inte ansträngt sig tillräckligt och har korta beskrivningar av problemen visar det att man inte har tillräklig kunskap för godkänd och får därmed komplettera.

Bedmöningen kommer meddelas inom en arbetsvecka via issues i ert Github-repo.

## Tips
* **Utgå ifrån kurslitteraturen kapitel 1-12 för att hitta optimeringar för front-end**
* Använd verktyg för att undersöka applikationen och hur den reagerar på olika anrop.
  * Chrome inspector
  * [POSTMAN](https://chrome.google.com/webstore/detail/postman/fhbjgbiflinjbdggehcddcbncdddomop) - chrome-plugin för att enklare kunns skicka request till en server. Väl värt att undersöka!

Lycka till!
